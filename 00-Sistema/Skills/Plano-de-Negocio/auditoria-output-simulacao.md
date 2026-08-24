# Auditoria de Output — Simulação Plano de Negócio

**Data:** 2026-08-21
**Pasta auditada:** `10-Obra/Plano-de-Negocio/`
**Simulação:** Plano completo (Blocos 1-7) para builder intermediário "Lorenzi"

---

## Score Geral: 6.5 / 10

| Dimensão | Score | Peso | Justificativa |
|----------|-------|------|---------------|
| Estrutura de pastas | 7/10 | 15% | Presente mas com 2 arquivos faltando e 1 pasta renomeada |
| Conteúdo dos `_dados.yaml` | 6/10 | 35% | Dados reais e concretos, mas schema diverge do esperado em vários blocos |
| Conteúdo dos `README.md` | 8/10 | 15% | Bem escritos, legíveis, complementam os YAML |
| `perfil.yaml` | 8/10 | 10% | Completo e utilizável por agentes |
| `memory.yaml` | 0/10 | 10% | NÃO EXISTE |
| `tarefas.md` | 0/10 | 5% | NÃO EXISTE |
| Usabilidade por agente | 5/10 | 10% | Suficiente para entender, insuficiente para executar |

**Veredicto:** O output é um bom rascunho de plano de negócios para leitura humana. Mas como **base de dados para agentes de IA**, tem lacunas críticas que impedem execução autônoma em vários cenários.

---

## 1. Estrutura

### O que está correto

```
10-Obra/Plano-de-Negocio/
├── README.md                        ✅
├── .builder/
│   └── perfil.yaml                  ✅
├── fundacao/
│   ├── cliente-ideal/
│   │   ├── README.md + _dados.yaml  ✅
│   ├── dor/                         ⚠️ (deveria ser "comunicacao")
│   │   ├── README.md + _dados.yaml  ✅
│   ├── diferencial/
│   │   ├── README.md + _dados.yaml  ✅
│   ├── pacotes/
│   │   ├── README.md + _dados.yaml  ✅
│   ├── posicionamento/
│   │   ├── README.md + _dados.yaml  ✅
│   └── meta/
│       ├── README.md + _dados.yaml  ✅
```

### Problemas encontrados

| # | Problema | Severidade | Impacto |
|---|----------|------------|---------|
| E1 | `memory.yaml` não existe | **CRÍTICO** | Agente não consegue retomar sessão, não sabe estado do fluxo, não tem snapshot de decisões |
| E2 | `tarefas.md` não existe | **ALTO** | Não há checklist acionável para o builder; ações ficam dispersas no README raiz |
| E3 | Pasta `dor/` em vez de `comunicacao/` | **MÉDIO** | O schema do pedido de auditoria esperava `comunicacao/`, mas o SKILL.md define como `dor/` — **a skill está correta**, o pedido de auditoria é que diverge. Score não penalizado. |
| E4 | Pasta nomeada `10-Obra/Plano-de-Negocio` (sem acento) vs `meu-negócio` | **BAIXO** | Funcional, mas inconsistente com documentação. Pode causar problemas em paths com acento. A skill define sem acento — correto. |

### Veredito Estrutura

A skill define claramente que `memory.yaml` deve ser criado no checkpoint da Parede 1 e que `tarefas.md` faz parte do output. Ambos foram omitidos. Isso indica que o system prompt não está forçando a criação desses arquivos com firmeza suficiente.

---

## 2. Análise por Arquivo — `_dados.yaml`

### 2.1 `fundacao/cliente-ideal/_dados.yaml` (Bloco 2)

**Schema esperado (knowledge-base-v2.md, seção 2.9):**
`area_setor`, `porte_empresa{faturamento, equipe, investimento_marketing}`, `comportamento_digital`, `momento_empresa`, `filtros_exclusao[]`

**Schema esperado (pedido de auditoria):**
`modo`, `descricao`, `perfil`, `sinais_de_bom_cliente`, `filtros_exclusao`, `onde_encontrar`

| Campo esperado (KB v2) | Presente? | Qualidade |
|------------------------|-----------|-----------|
| `area_setor` | ✅ | Bom — concreto e transversal |
| `porte_empresa` (objeto) | ❌ | Desestruturado — dados existem mas espalhados em campos avulsos (`faturamento_estimado`, `equipe`, `investimento_marketing`) |
| `comportamento_digital` | ❌ | Ausente como campo — conteúdo parcial em `investimento_marketing` |
| `momento_empresa` | ✅ | Bom — array com 3 itens concretos |
| `filtros_exclusao[]` | ✅ | Bom — 5 filtros claros e acionáveis |

**Campos ausentes críticos:**
- `sinais_de_bom_cliente` — **CRÍTICO** para agentes. Como um agente de atendimento sabe se o lead é bom?
- `onde_encontrar` — **ALTO**. Onde prospectar? Google Maps? Instagram? Indicação? Não registrado.
- `cliente_a_clonar` — Existe no README mas **não** no YAML. Agentes leem YAML, não README.

**Campos extras presentes:**
- `tipo_produto` — útil, pode ficar
- `nivel_consciencia` — útil, pode ficar
- `evolucao` — repetitivo (presente em TODOS os blocos com texto quase idêntico)

**Score Bloco 2: 6/10** — Dados reais e concretos, mas schema mal estruturado e campos-chave ausentes.

---

### 2.2 `fundacao/dor/_dados.yaml` (Bloco 3)

**Schema esperado (KB v2, seção 3.9):**
`dor_primaria`, `frustracoes[]`, `desejos[]`, `problema_traduzido`, `regra_80_20`

**Schema esperado (pedido de auditoria):**
`problema_central`, `dores[{frase,contexto}]`, `desejos[{frase,contexto}]`, `vocabulario_icp`, `tom`

| Campo esperado (KB v2) | Presente? | Qualidade |
|------------------------|-----------|-----------|
| `dor_primaria` | ✅ | Bom — frase concreta e na linguagem do cliente |
| `frustracoes[]` | ✅ | Bom — 4 itens concretos. Mas formato é flat string, não `{frase, contexto}` |
| `desejos[]` | ✅ | OK — 3 itens, mas genéricos comparado às frustrações |
| `problema_traduzido` | ✅ | Bom — frase na linguagem do cliente |
| `regra_80_20` | ✅ | Bom — clara e acionável |

**Campos ausentes críticos:**
- `vocabulario_icp` — **CRÍTICO**. Sem vocabulário, um agente de conteúdo não sabe que palavras usar. "Clique", "desperdício", "conversão" aparecem dispersos mas não como lista estruturada.
- `tom` — **CRÍTICO**. Direto? Técnico? Empático? Casual? Nenhuma indicação.
- `cadeia_causal` — Presente no YAML (bom!), mas não no schema esperado. Dado valioso que DEVE ser mantido.

**Problemas de estrutura:**
- `frustracoes[]` e `desejos[]` são arrays de strings simples. O schema do pedido espera `{frase, contexto}`. A versão com contexto é muito mais útil para agentes — exemplo: `{frase: "Investir em anúncio sem saber se a página está ajudando", contexto: "Dono de negócio que paga tráfego e não vê resultado na página"}`.

**Score Bloco 3: 6/10** — Dados reais, mas falta vocabulário e tom (insumos críticos para comunicação).

---

### 2.3 `fundacao/diferencial/_dados.yaml` (Bloco 4)

**Schema esperado (KB v2, seção 4.9):**
`formula_diferencial`, `postura`, `hard_skills[]`, `soft_skills[]`, `mecanismo_unico`

| Campo esperado | Presente? | Qualidade |
|----------------|-----------|-----------|
| `formula_diferencial` | ✅ | Bom — segue o formato "Através de [X], resolve [Y] e entrega [Z]" |
| `postura` | ✅ | Bom — "Parceiro de trincheira" é concreto e memorável |
| `hard_skills[]` | ✅ | OK — 4 itens, nível intermediário declarado coerente |
| `soft_skills[]` | ✅ | Bom — 5 comportamentos concretos (não genéricos) |
| `mecanismo_unico` | ✅ | Bom — "publicação como começo da validação" é diferenciador real |

**Campos ausentes:**
- `promessa` — Ausente como campo separado. Está embutido na `formula_diferencial`.
- `como_sou_diferente` — Ausente. O conteúdo está no `mecanismo_unico` mas sem comparação explícita com mercado.
- `prova` / `cases` — **ALTO**. Nenhum case, nenhuma métrica, nenhuma evidência. O README admite: "construir cases após os primeiros projetos". Mas um agente montando proposta não tem NADA para provar o diferencial.

**Score Bloco 4: 7/10** — Schema bem aderente ao esperado. Falta prova de resultado.

---

### 2.4 `fundacao/pacotes/_dados.yaml` (Bloco 5)

**Schema esperado (KB v2, seção 5.9):**
`nome_oferta`, `escopo[]`, `entregaveis[]`, `preco`, `modelo_cobranca`, `escada_valor{entrada, principal, premium, recorrencia}`

| Campo esperado | Presente? | Qualidade |
|----------------|-----------|-----------|
| `escada_valor` | ✅ | **EXCELENTE** — todos os 4 níveis com nome, preço, para_quem, entrega[] e funcao |
| `modelo_cobranca` | ✅ | Bom — "50% entrada + 50% entrega" |
| `big_idea` | ✅ | Bom — "Cada clique tem um custo" é memorável |
| `receita_recorrente_imediata` | ✅ | Bom — projeção concreta |
| `projecao_com_escada` | ✅ | Bom — matemática clara |
| `nota_comercial` | ✅ | Útil para calibrar confiança do builder |

**Campos ausentes:**
- `servico_carro_chefe` — Implícito (é o principal), mas não marcado como campo.
- `como_apresentar` — **ALTO**. Não há script de apresentação. Um agente de vendas não sabe em que ORDEM apresentar, como ancorar, como fazer down-sell.
- `servicos_individuais[]` separados — Ausente. Todos estão dentro da escada.

**Observação positiva:** Este é o melhor `_dados.yaml` do conjunto. Estrutura da `escada_valor` é rica, com `entrega[]` detalhado para cada nível, `funcao` explicando o papel estratégico, e `alerta` operacional na recorrência.

**Score Bloco 5: 8/10** — O mais completo. Falta apenas script de apresentação.

---

### 2.5 `fundacao/posicionamento/_dados.yaml` (Bloco 6)

**Schema esperado (KB v2, seção 6.9):**
`bio`, `promessa`, `elemento_autoridade`, `filtro_cta`, `linguagem_icp`

| Campo esperado | Presente? | Qualidade |
|----------------|-----------|-----------|
| `bio` | ✅ | Bom — 3 linhas claras |
| `promessa` | ✅ | Bom — concreta |
| `elemento_autoridade` | ⚠️ | FRACO — diz "a incorporar quando cases estiverem consolidados". Efetivamente vazio. |
| `filtro_cta` | ✅ | OK — mas não é um CTA que filtra (qualquer pessoa mandaria mensagem para "ver portfólio") |
| `linguagem_icp` | ✅ | Bom — lista concreta de palavras: "clique, desperdício, conversão, tráfego" |
| `frase_posicionamento` | ✅ | Bom — alicerce claro |

**Campos ausentes CRÍTICOS:**
- `bio_camadas` — A bio existe mas não está decomposta em camadas (dor/autoridade/CTA). Um agente reescrevendo a bio não sabe qual parte é qual.
- `kit_presenca_digital` — **CRÍTICO**. Não há:
  - Config de Instagram (pilares de conteúdo, frequência, formato de posts, hashtags)
  - Script de WhatsApp (mensagem de primeiro contato, qualificação, proposta)
  - Behance/portfólio (organização, projetos destaque)
  - Estratégia de conteúdo (temas, tom, cadência)

**Problema grave:** O `elemento_autoridade` ser "a incorporar" torna a bio incompleta. A Camada 2 (autoridade) está vazia na prática. A bio atual funciona como 2 camadas (dor + serviço), não 3.

**Score Bloco 6: 5/10** — Bio funcional, mas posicionamento incompleto para operação multi-canal.

---

### 2.6 `fundacao/meta/_dados.yaml` (Bloco 7)

**Schema esperado (KB v2, seção 7.9):**
`ticket_medio`, `clientes_mes`, `faturamento_alvo`, `criterio_subir_preco`, `capacidade_entrega`

| Campo esperado | Presente? | Qualidade |
|----------------|-----------|-----------|
| `ticket_medio_atual` | ✅ | Bom |
| `ticket_novo` | ✅ | Bom — R$2.800 |
| `faturamento_alvo` (meta_90_dias) | ✅ | Bom — R$15.000 |
| `criterio_subir_preco` | ✅ | **EXCELENTE** — gatilho comportamental concreto |
| `capacidade_entrega` | ✅ | Bom — "4 LPs/semana com Easy Builder" |
| `projecao_cenarios` | ✅ | Bom — 3 cenários concretos |

**Campos ausentes:**
- `clientes_necessarios` (por mês) — **ALTO**. A conta `meta / ticket = clientes_mes` não está feita explicitamente. Um agente de planejamento não consegue verificar viabilidade sem esse número.
- `viavel` (boolean + justificativa) — Ausente. Não há veredito: "a meta é viável dado capacidade e pipeline?"
- `decomposicao_matematica` — Projeções existem como texto, mas não como cálculo estruturado. Ideal: `{meta: 15000, ticket: 2800, clientes: ceil(15000/2800)=6, recorrencia_esperada: 1500, projetos_necessarios: ceil((15000-1500)/2800)=5}`.
- `checklist_acao_imediata` — `acoes_imediatas` tem apenas 2 itens, sem checkbox, prazo ou responsável.

**Score Bloco 7: 7/10** — Dados sólidos, falta estruturação matemática.

---

## 3. Análise dos README.md

| Arquivo | Legível? | Complementa YAML? | Contexto suficiente? | Nota |
|---------|----------|--------------------|----------------------|------|
| `README.md` (raiz) | ✅ Excelente | ✅ Visão panorâmica única | ✅ | 9/10 — Tabela resumo + frase + ações. Modelo a seguir. |
| `cliente-ideal/README.md` | ✅ Bom | ⚠️ Tem `cliente_a_clonar` que falta no YAML | ✅ | 7/10 |
| `dor/README.md` | ✅ Bom | ✅ Complementa bem | ✅ | 8/10 |
| `diferencial/README.md` | ✅ Bom | ⚠️ Duplica formula, pouco valor extra | OK | 7/10 |
| `pacotes/README.md` | ✅ Bom | ✅ Boa visão de escada | ✅ | 8/10 |
| `posicionamento/README.md` | ✅ Bom | ✅ Estrutura de 3 linhas | ✅ | 7/10 |
| `meta/README.md` | ✅ Bom | ✅ Cenários e critério de subida | ✅ | 8/10 |

**Padrão observado:** Os READMEs são consistentes, usam tabelas, blockquotes para frases-chave, e terminam com nota de "em construção". Bom template.

**Problema:** Alguns dados existem APENAS no README e não no YAML (ex: `cliente_a_clonar` no Bloco 2). Agentes leem YAML, não Markdown. Tudo que é dado acionável DEVE estar no YAML.

---

## 4. Análise do `perfil.yaml`

| Campo | Presente? | Qualidade | Útil para agente? |
|-------|-----------|-----------|-------------------|
| `nome` | ✅ | — | ✅ Personalização |
| `serie_atual` | ✅ | Coerente com dados | ✅ Calibração de profundidade |
| `faturamento_3_meses` | ✅ | R$5.200 (concreto) | ✅ |
| `ticket_medio` | ✅ | R$1.300 | ✅ |
| `ticket_range` | ✅ | "R$900 – R$1.800" | ✅ Contexto de variação |
| `projetos_entregues_total` | ✅ | 11 | ✅ |
| `tempo_disponivel_horas_semana` | ✅ | 25h | ✅ |
| `confianca_cliente_100k` | ✅ | 6/10 | ✅ Excelente — calibra sugestões |
| `competencias[]` | ✅ | 3 itens com nível | ✅ |
| `ferramentas[]` | ✅ | 10 ferramentas | ✅ |
| `canal_aquisicao` | ✅ | Indicação + Instagram | ✅ |
| `maior_gargalo` | ✅ | Posicionamento/confiança | ✅ |
| `precifica_por` | ✅ | "Medo de perder" | ✅ Excelente — diagnóstico comportamental |
| `evolucao` | ✅ | Pontos de melhoria | ✅ |

**Score: 8/10** — O `perfil.yaml` é o arquivo mais completo e bem estruturado do conjunto. Um agente consegue calibrar comportamento lendo apenas este arquivo.

**O que falta para ser 10:**
- `comunicacao_preferida` — O builder prefere WhatsApp? Email? Chamada? Essencial para agentes de atendimento.
- `horario_disponivel` — Quando trabalha? Manhã? Noite? Final de semana?
- `clientes_ativos[]` — Lista (mesmo anônima) dos clientes ativos com tipo de projeto. Hoje é apenas "6" como número.

---

## 5. Análise do `memory.yaml`

**Status: NÃO EXISTE** ❌

A `memory-spec.md` define um schema completo e detalhado para o `memory.yaml`. O arquivo deveria ter sido criado no checkpoint da Parede 1 (Bloco 1), conforme seção 6.3 da spec.

**Impacto:**
- Agente não sabe em que ponto do fluxo o builder está
- Não há snapshot de decisões para acesso rápido
- Não há histórico de preços ou evolução
- Não há tarefas pendentes rastreadas
- Retomada de sessão é impossível sem re-ler todos os arquivos
- Perguntas de acompanhamento ("conseguiu fechar no novo ticket?") ficam sem contexto

**Causa provável:** O system prompt não inclui a seção de memória persistente (seção 5 da spec). A spec foi escrita como documento separado mas não foi integrada ao `SKILL.md`.

---

## 6. Análise do `tarefas.md`

**Status: NÃO EXISTE** ❌

Ações existem dispersas:
- No `README.md` raiz: "Próximas Ações (esta semana)" com 3 itens numerados (sem checkbox)
- Nos `_dados.yaml`: campo `evolucao.pontos_de_melhoria` em cada bloco (sem prazo, sem prioridade)
- Na `memory-spec.md`: campo `tarefas_pendentes` com 3 tarefas (com prioridade e prazo)

**Impacto:**
- Builder não tem um lugar único para ver "o que fazer agora"
- Agentes de acompanhamento não conseguem verificar progresso
- Não há diferenciação entre tarefas imediatas e melhoria contínua

**O que deveria conter (`tarefas.md`):**
```markdown
# Tarefas — Plano de Negócio v1

## Esta Semana
- [ ] Converter 3 clientes existentes para Parceiro de Tráfego (R$1.500/mês)
- [ ] Fechar próximo projeto em R$2.800
- [ ] Atualizar bio do Instagram com novo posicionamento

## Próximos 30 Dias
- [ ] Validar ticket de R$2.800 em 2-3 projetos
- [ ] Monitorar tamanho real dos ajustes na recorrência
- [ ] Construir primeiro case com números (antes/depois)

## Melhoria Contínua
- [ ] Criar canal de aquisição além de indicação
- [ ] Quantificar impacto financeiro da dor com dados reais
- [ ] Incorporar métrica verificável na bio quando cases consolidarem
```

---

## 7. Teste de Uso por Outro Agente

### Teste 1: "Crie uma proposta comercial para o cliente X"

**Insumos disponíveis:**
- ✅ Pacotes com nomes, preços e entregáveis detalhados
- ✅ ICP para validar se o cliente se encaixa
- ✅ Frase de posicionamento para abertura
- ✅ Dor primária para contextualizar o problema
- ✅ Modelo de cobrança (50/50)
- ✅ Big Idea para hook

**Insumos FALTANDO:**
- ❌ **Cases / prova social** — Proposta sem case é genérica. O agente não tem NENHUM número para provar resultado.
- ❌ **Script de apresentação** — Em que ordem apresentar? Como ancorar? Como fazer down-sell?
- ❌ **Tom de comunicação** — A proposta deve ser formal? Direta? Empática? O agente não sabe.
- ❌ **Vocabulário do ICP** — Existe no Bloco 6 (`linguagem_icp`) mas não no Bloco 3. Agente teria que cruzar arquivos.
- ❌ **Template de proposta** — Não há estrutura de proposta (abertura → diagnóstico → solução → prova → investimento → CTA).

**Veredito: 6/10** — Agente monta proposta funcional mas genérica no tom. Sem case de prova, a proposta fica fraca na etapa de convencimento. O processo de 7 passos da proposta comercial (KB v2, seção 5.3.5) não tem correspondência nos dados gerados.

---

### Teste 2: "Crie um post para Instagram"

**Insumos disponíveis:**
- ✅ Frase de posicionamento
- ✅ Bio (3 linhas)
- ✅ Dor primária e frustrações do ICP
- ✅ `linguagem_icp` no Bloco 6 ("clique, desperdício, conversão, tráfego")
- ✅ Diferencial / mecanismo único

**Insumos FALTANDO:**
- ❌ **Pilares de conteúdo** — Sobre o quê postar? Educação? Bastidores? Cases? Portfolio?
- ❌ **Tom definido** — Técnico? Casual? Provocativo? Educativo?
- ❌ **Formatos preferidos** — Carrossel? Reels? Texto? Stories?
- ❌ **Cadência** — Quantos posts/semana?
- ❌ **Hashtags** — Nenhuma indicação
- ❌ **Exemplo de post** — Nenhum modelo de referência
- ❌ **Kit de presença digital** — Não existe como estrutura

**Veredito: 3/10** — Agente consegue escrever UM post usando a frase de posicionamento e a dor. Mas não tem nenhuma estratégia de conteúdo. Não sabe o tom, não sabe os temas, não sabe o formato. A cada post pedido, teria que improvisar do zero.

---

### Teste 3: "Atenda um lead que mandou mensagem no WhatsApp"

**Insumos disponíveis:**
- ✅ Filtros de exclusão para qualificar/desqualificar
- ✅ ICP para validar perfil
- ✅ Pacotes e preços para apresentar
- ✅ Dor primária para gerar rapport

**Insumos FALTANDO:**
- ❌ **Script de qualificação** — Quais perguntas fazer? Em que ordem?
- ❌ **Tom de atendimento** — Formal ou informal?
- ❌ **Mensagem de primeiro contato** — Não há template
- ❌ **Objeções comuns + respostas** — "Tá caro", "Preciso pensar", etc.
- ❌ **Processo de down-sell** — Quando e como oferecer o Diagnóstico em vez da Estrutura

**Veredito: 4/10** — Agente sabe o que vender e para quem, mas não sabe COMO vender. Falta todo o processo comercial.

---

## 8. Gaps Críticos Consolidados

### Tier 1 — Bloqueiam execução por agentes

| # | Gap | Afeta | Onde deveria estar |
|---|-----|-------|--------------------|
| G1 | `memory.yaml` inexistente | Retomada de sessão, rastreamento de estado | `.builder/memory.yaml` |
| G2 | `vocabulario_icp` ausente | Criação de conteúdo, propostas, atendimento | `dor/_dados.yaml` ou campo global |
| G3 | `tom` de comunicação ausente | TUDO que envolve escrever | `dor/_dados.yaml` ou `posicionamento/_dados.yaml` |
| G4 | `kit_presenca_digital` ausente | Posts, bio, WhatsApp, portfólio | `posicionamento/_dados.yaml` |
| G5 | `tarefas.md` inexistente | Acompanhamento e accountability | `10-Obra/Plano-de-Negocio/tarefas.md` |

### Tier 2 — Degradam qualidade do output de agentes

| # | Gap | Afeta | Onde deveria estar |
|---|-----|-------|--------------------|
| G6 | `prova` / cases com números ausentes | Propostas, autoridade, conteúdo | `diferencial/_dados.yaml` |
| G7 | `como_apresentar` ausente (script de proposta) | Processo comercial | `pacotes/_dados.yaml` |
| G8 | `sinais_de_bom_cliente` ausentes | Qualificação de leads | `cliente-ideal/_dados.yaml` |
| G9 | `onde_encontrar` ausente | Prospecção | `cliente-ideal/_dados.yaml` |
| G10 | `clientes_necessarios` (cálculo) ausente | Planejamento | `meta/_dados.yaml` |
| G11 | `decomposicao_matematica` desestruturada | Viabilidade | `meta/_dados.yaml` |
| G12 | `bio_camadas` (dor/autoridade/CTA decompostas) | Reescrita de bio | `posicionamento/_dados.yaml` |

### Tier 3 — Melhorias desejáveis

| # | Gap | Afeta |
|---|-----|-------|
| G13 | `frustracoes[]` e `desejos[]` sem estrutura `{frase, contexto}` | Conteúdo contextual |
| G14 | `cliente_a_clonar` no YAML (existe só no README) | Agentes de prospecção |
| G15 | Bloco `evolucao` repetido em todos os YAML com texto quase idêntico | Poluição de dados |

---

## 9. Recomendações para o System Prompt

### R1 — Forçar criação de `memory.yaml` e `tarefas.md`

**No checkpoint de cada parede**, o system prompt deve incluir:

```
REGRA: Ao salvar uma parede, SEMPRE:
1. Grave os _dados.yaml e README.md dos blocos da parede
2. Grave/atualize .builder/memory.yaml conforme schema
3. Grave/atualize tarefas.md com checklist atualizado
Se memory.yaml não existir, crie-o. Se tarefas.md não existir, crie-o.
```

Atualmente a regra 8 ("Salva nos checkpoints") não menciona memory.yaml nem tarefas.md.

### R2 — Adicionar campos obrigatórios faltantes ao schema de output

Para cada bloco, adicionar na seção "Output esperado" da knowledge base:

**Bloco 2:**
```yaml
# Adicionar
sinais_de_bom_cliente: []    # 3-5 indicadores observáveis
onde_encontrar: []            # canais de prospecção
cliente_a_clonar: ""          # perfil do melhor cliente passado
```

**Bloco 3:**
```yaml
# Adicionar
vocabulario_icp: []           # 10-20 palavras/expressões que o ICP usa
tom: ""                       # ex: "direto, técnico mas acessível, sem jargão de design"
# Mudar estrutura
frustracoes:
  - frase: ""
    contexto: ""
desejos:
  - frase: ""
    contexto: ""
```

**Bloco 4:**
```yaml
# Adicionar
prova: []                     # cases, métricas, evidências (mesmo que "a construir")
```

**Bloco 5:**
```yaml
# Adicionar
servico_carro_chefe: ""       # qual é o popstar marcado explicitamente
como_apresentar:              # script de apresentação
  ordem: []                   # ex: ["premium primeiro", "ancorar", "downsell"]
  objecoes_comuns: []          # com respostas preparadas
```

**Bloco 6:**
```yaml
# Adicionar
bio_camadas:
  camada_1_dor: ""
  camada_2_autoridade: ""
  camada_3_cta: ""
kit_presenca_digital:
  instagram:
    pilares_conteudo: []
    formatos: []
    cadencia: ""
  whatsapp:
    mensagem_boas_vindas: ""
    perguntas_qualificacao: []
  portfolio:
    url: ""
    projetos_destaque: []
```

**Bloco 7:**
```yaml
# Adicionar
clientes_necessarios: 0       # cálculo: meta / ticket
viavel: true                  # com justificativa
decomposicao:
  meta: 15000
  recorrencia_esperada: 1500
  restante_projetos: 13500
  ticket: 2800
  projetos_necessarios: 5
  projetos_por_mes: 2
  horas_por_projeto: 8
  horas_necessarias_mes: 16
  horas_disponiveis_mes: 100
```

### R3 — Eliminar bloco `evolucao` repetitivo

O campo `evolucao` é copiado identicamente em TODOS os `_dados.yaml` com variações mínimas. Isso polui os dados e confunde agentes.

**Solução:** Mover `evolucao` para o `perfil.yaml` (único lugar) e remover dos `_dados.yaml` dos blocos. Cada bloco pode ter um `revisar_quando` simples, mas não precisa de `serie_atual`, `como_evolui` e `pontos_de_melhoria` repetidos.

### R4 — Integrar memory-spec no SKILL.md

A seção 5 da `memory-spec.md` tem instruções prontas para o system prompt. Inserir no `SKILL.md` entre as seções 3 (Fluxo de Construção) e 4 (Profundidade Adaptativa), conforme a própria spec sugere.

### R5 — Adicionar validação de output pós-checkpoint

Após gravar cada parede, o agente deve fazer uma auto-verificação:

```
REGRA: Após salvar uma parede, verifique:
1. Todos os campos do schema de output estão preenchidos?
2. Algum campo tem valor genérico/placeholder?
3. Os dados seriam suficientes para outro agente executar uma tarefa?
Se falhar qualquer checagem, corrija ANTES de avançar.
```

### R6 — Separar dados de posicionamento tático

O Bloco 6 tenta cobrir posicionamento (estratégico) e presença digital (tática) no mesmo arquivo. Considerar criar `fundacao/presenca-digital/_dados.yaml` para kit Instagram, WhatsApp, conteúdo — ou adicionar sub-estrutura clara no YAML existente.

---

## 10. Resumo Executivo

### O que está BOM

1. **Dados são reais, não placeholder** — o builder respondeu perguntas reais e o agente registrou dados concretos (R$1.300 ticket, R$5.200 em 3 meses, 11 projetos)
2. **Escada de valor é excelente** — pacotes/_dados.yaml é o melhor arquivo do conjunto, com entregáveis detalhados por nível
3. **README.md raiz é modelo** — tabela resumo + frase + ações imediatas + critério de evolução
4. **perfil.yaml é sólido** — agente consegue calibrar comportamento lendo apenas este arquivo
5. **Consistência visual** — todos os READMEs seguem mesmo padrão (tabelas, blockquotes, nota de "em construção")
6. **Frase de posicionamento é forte** — "Você já paga pelo clique. Eu trabalho para ele não virar desperdício." Concreta, filtrada, memorável.

### O que PRECISA mudar (por prioridade)

1. **Criar `memory.yaml`** — sem memória, a skill é stateless e toda retomada perde contexto
2. **Criar `tarefas.md`** — sem checklist, ações ficam dispersas e sem rastreamento
3. **Adicionar `vocabulario_icp` e `tom`** — sem isso, qualquer agente de comunicação opera no escuro
4. **Adicionar `kit_presenca_digital`** — Instagram, WhatsApp, portfólio sem estrutura = agente de conteúdo inútil
5. **Estruturar campos ausentes** — `sinais_de_bom_cliente`, `onde_encontrar`, `como_apresentar`, `bio_camadas`
6. **Integrar memory-spec no SKILL.md** — a spec existe mas não foi integrada ao prompt
7. **Eliminar `evolucao` duplicado** — poluição que confunde agentes sem agregar valor

### Prognóstico

Com as correções dos itens 1-6, o score sobe de **6.5 → 8.5/10**. O output passaria a ser uma base de dados genuinamente operacional — não apenas um documento bonito, mas um insumo que permite a outros agentes de IA executarem tarefas (propostas, conteúdo, atendimento) com qualidade e consistência.
