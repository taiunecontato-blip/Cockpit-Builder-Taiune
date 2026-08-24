# Plano de Correcoes — System Prompt vs Auditoria

**Data:** 2026-08-21
**Base:** `auditoria-output-simulacao.md` (score 6.5/10) vs `prompts/system-prompt.md`
**Objetivo:** Mapear cada gap da auditoria a uma secao exata do system prompt e propor edicao concreta.

---

## Metodologia

Para cada gap (G1-G15) e recomendacao (R1-R6) da auditoria:
1. **Gap** — descricao do problema
2. **Secao do prompt** — onde deveria estar coberto (com numero de linha)
3. **Diagnostico** — o que esta faltando ou e fraco
4. **Edicao** — texto concreto para inserir/substituir

---

## TIER 1 — Bloqueiam execucao por agentes

### G1 — `memory.yaml` inexistente

**Gap:** O arquivo `.builder/memory.yaml` nao foi criado. Sem ele, o agente nao consegue retomar sessao, rastrear estado ou manter historico.

**Secao do prompt:**
- Regra 8 (linha 41): `"Salva nos checkpoints — grava arquivos nos 4 checkpoints de parede, nunca antes."`
- Secao MEMORIA PERSISTENTE (linhas 142-290): Instrucoes completas de leitura/escrita do memory.yaml
- Secao 3.2, ETAPA 4 — REGISTRAR (linhas 94-97): `"No checkpoint de parede, grava os arquivos no workspace."`
- Checklist Final (linhas 1442-1459): NAO menciona verificacao de memory.yaml

**Diagnostico:**
A secao MEMORIA PERSISTENTE esta BEM escrita (linhas 142-290), mas:
1. A **Regra 8** (regra absoluta) nao menciona memory.yaml — fala genericamente de "grava arquivos"
2. A **ETAPA 4** (ciclo por bloco) nao menciona memory.yaml — fala genericamente de "grava os arquivos no workspace"
3. O **Checklist Final** nao inclui "memory.yaml existe e esta atualizado"
4. A regra esta dispersa — o agente encontra a instrucao generica na Regra 8 e nunca chega a ler a secao de Memoria

**Edicao 1a — Regra 8 (linha 41):**

```
ANTES:
8. **Salva nos checkpoints** — grava arquivos nos 4 checkpoints de parede, nunca antes.

DEPOIS:
8. **Salva nos checkpoints** — grava arquivos nos 4 checkpoints de parede, nunca antes. Cada checkpoint DEVE gravar: (a) _dados.yaml + README.md dos blocos da parede, (b) .builder/memory.yaml (criar se nao existe), (c) tarefas.md (criar se nao existe). Se memory.yaml ou tarefas.md nao existem, CRIE-OS. Nunca salvar parede sem esses 3 componentes.
```

**Edicao 1b — ETAPA 4 (linhas 94-97):**

```
ANTES:
**ETAPA 4 — REGISTRAR**
- Confirma e avanca pro proximo bloco.
- No checkpoint de parede, grava os arquivos no workspace.
- Mostra progresso visual da obra.

DEPOIS:
**ETAPA 4 — REGISTRAR**
- Confirma e avanca pro proximo bloco.
- No checkpoint de parede, grava os arquivos no workspace:
  - `_dados.yaml` + `README.md` dos blocos da parede
  - `.builder/memory.yaml` — atualizar progresso, decisoes, tarefas (criar se nao existe)
  - `tarefas.md` — atualizar com tarefas de execucao do bloco (criar se nao existe)
- Mostra progresso visual da obra.
- **Auto-verificacao:** Confirme que TODOS os arquivos foram gravados. Se memory.yaml ou tarefas.md nao existem apos o checkpoint, crie-os ANTES de avancar.
```

**Edicao 1c — Checklist Final (apos linha 1459):**

```
ADICIONAR:
- [ ] `.builder/memory.yaml` existe e esta atualizado com progresso, decisoes e tarefas
- [ ] `tarefas.md` existe e contem checklist de execucao para cada bloco concluido
- [ ] Nenhum dado acionavel existe APENAS em README sem correspondente no _dados.yaml
```

---

### G2 — `vocabulario_icp` ausente

**Gap:** Sem vocabulario estruturado do ICP, agentes de conteudo/proposta/atendimento nao sabem que palavras usar.

**Secao do prompt:**
- Bloco 3 — Output (linha 501): `dor_primaria`, `frustracoes[]`, `desejos[]`, `problema_traduzido`, `regra_80_20`
- Bloco 3 — Processo (linhas 466-471): passo 4 e "Traducao para linguagem do cliente" mas nao gera campo estruturado

**Diagnostico:**
O processo do Bloco 3 pede "traducao para linguagem do cliente" (passo 4, linha 469), mas o output NAO inclui um campo para armazenar esse vocabulario. O dado se perde na conversa. O Bloco 6 tem `linguagem_icp` no output, mas quem produz esse conteudo e o Bloco 3. O resultado e que o vocabulario nao e capturado em nenhum bloco.

**Edicao 2a — Bloco 3, apos o Processo (inserir apos linha 471):**

```
ADICIONAR ao processo (apos passo 6):
7. Coleta de vocabulario: durante TODA a conversa do Bloco 3, registre as palavras e expressoes que o ICP usa. Manter 10-20 termos. Ex: "clique", "desperdicio", "conversao", "nao aparece no Google", "investir em ads sem retorno".
8. Definicao de tom: perguntar ao builder "Quando voce fala com seu cliente ideal, como e o tom? Direto e tecnico? Empativo e acessivel? Provocativo? Casual?" Registrar como campo estruturado.
```

**Edicao 2b — Bloco 3, Output (linha 501):**

```
ANTES:
**Output:** `dor_primaria`, `frustracoes[]`, `desejos[]`, `problema_traduzido`, `regra_80_20`

DEPOIS:
**Output:** `dor_primaria`, `frustracoes[{frase, contexto}]`, `desejos[{frase, contexto}]`, `problema_traduzido`, `regra_80_20`, `vocabulario_icp[]`, `tom`
```

**Edicao 2c — Bloco 3, adicionar Perguntas-guia (apos linha 487):**

```
ADICIONAR:
8. Quais palavras o seu cliente usa quando reclama? (ex: "nao aparece", "ta caro o clique", "site feio")
9. Quando voce fala com esse cliente, qual e o tom? Direto e tecnico? Empativo? Provocativo?
```

---

### G3 — `tom` de comunicacao ausente

**Gap:** Sem tom definido, qualquer agente que escreva pelo builder (proposta, post, mensagem) opera no escuro.

**Secao do prompt:**
- Bloco 3 — Output (linha 501): NAO inclui `tom`
- Bloco 6 — Nenhuma referencia a tom de comunicacao

**Diagnostico:**
O conceito de "tom" nao aparece em NENHUM output spec do prompt. O Bloco 3 fala de "linguagem do cliente" mas nao estrutura como campo. O Bloco 6 define como a bio deve ser escrita mas nao captura o tom geral do builder.

**Edicao:** Ja coberta em G2 (Edicao 2b e 2c). O campo `tom` sera capturado no Bloco 3 como parte do output.

---

### G4 — `kit_presenca_digital` ausente no output

**Gap:** O Bloco 6 define extensivamente 6.1-6.7 no prompt, mas o output gerado nao incluiu os dados estruturados de Instagram, WhatsApp, Behance, etc.

**Secao do prompt:**
- Bloco 6 — Sub-itens 6.1 a 6.7 (linhas 748-878): Instrucoes detalhadas
- Bloco 6 — Output (linha 914): Schema detalhado com todos os campos

**Diagnostico:**
O prompt JA TEM o schema correto no output (linha 914). O problema e de ENFORCEMENT, nao de spec. O agente provavelmente:
1. Construiu a bio (6.1) e parou
2. Nao percorreu cada sub-item (6.2-6.7) com o builder
3. Gerou um _dados.yaml simplificado sem os campos de Instagram, WhatsApp, etc.

A causa raiz: nao ha VALIDACAO pos-bloco que verifique se TODOS os campos do schema de output foram preenchidos.

**Edicao 4a — Bloco 6, antes da secao de Heuristicas (inserir apos linha 878):**

```
ADICIONAR:
**REGRA DE COMPLETUDE DO BLOCO 6:**
O Bloco 6 NAO esta completo ate que TODOS os sub-itens (6.1 a 6.7) tenham sido trabalhados com o builder. O agente DEVE percorrer cada sub-item na ordem, gerando os entregaveis e registrando status (feito/a_fazer). Se o builder quiser pular, registrar como `a_fazer` no _dados.yaml — mas o campo DEVE existir no YAML. Um _dados.yaml do Bloco 6 que so tem `bio` e `frase_posicionamento` esta INCOMPLETO. Todos os campos do schema de output (linha 914) devem estar presentes, mesmo que com status `a_fazer`.
```

**Edicao 4b — Bloco 6, Output (substituir linha 914):**

```
ANTES:
**Output:** `instagram_perfil{foto_status, arroba, nome_display, bio{linha1_servico, linha2_dor, linha3_valor, cta}}`, `instagram_destaques[{nome, conteudo, status}]`, `instagram_posts_fixados[{numero, tipo, briefing, status}]`, `link_bio{foto_status, botao_portfolio, botao_orcamentos, mini_bio}`, `whatsapp{foto_status, descricao, wpp_business, visibilidade, catalogo[{item, status}], capa_status}`, `behance{perfil_status, projetos_count}`, `grade_conteudo_status`

DEPOIS:
**Output:** `frase_posicionamento`, `linguagem_icp[]`, `instagram_perfil{foto_status, arroba, nome_display, bio{linha1_servico, linha2_dor, linha3_valor, cta}, bio_camadas{camada_dor, camada_autoridade, camada_cta}}`, `instagram_destaques[{nome, conteudo, status}]`, `instagram_posts_fixados[{numero, tipo, briefing, status}]`, `link_bio{foto_status, botao_portfolio, botao_orcamentos, mini_bio}`, `whatsapp{foto_status, descricao, wpp_business, visibilidade, catalogo[{item, status}], capa_status}`, `behance{perfil_status, projetos_count}`, `grade_conteudo_status`

NOTA: `bio_camadas` decompoe a bio em partes funcionais (dor/autoridade/CTA) para facilitar reescrita por agentes. E complementar a `bio` que contem o texto final.
```

---

### G5 — `tarefas.md` inexistente

**Gap:** Nao ha checklist unico e centralizado de acoes para o builder executar.

**Secao do prompt:**
- Estrutura de pastas (linha 1061): `tarefas.md` aparece na arvore
- Regras de output (linha 1095): Instrucoes sobre formato e atualizacao
- Checklist Final (linha 1457): Menciona `tarefas.md` mas sem verificacao de existencia

**Diagnostico:**
Similar a G1 — o prompt TEM instrucoes sobre tarefas.md (linha 1095), mas:
1. Regra 8 nao menciona
2. ETAPA 4 nao menciona
3. Nao ha enforcement pos-checkpoint
A correcao ja esta coberta pelas edicoes de G1 (Edicoes 1a, 1b, 1c).

**Edicao adicional 5a — Regras de output (reforcar linha 1095):**

```
ANTES:
- **`tarefas.md`** e atualizado ao final de CADA bloco com tarefas de execucao imediata. Formato checkbox markdown (`- [ ] Tarefa`). Organizado por bloco. Sempre que o agente define algo, cria a tarefa correspondente. No Bloco 6 (posicionamento) especialmente: criar tarefas para executar rapido (criar/ajustar Instagram, configurar bio, montar portfolio, configurar WPP Business, etc.). Organizacao e extremamente importante — nao basta definir, tem que criar a lista de execucao.

DEPOIS:
- **`tarefas.md`** e atualizado ao final de CADA bloco com tarefas de execucao imediata. Formato checkbox markdown (`- [ ] Tarefa`). Organizado em 3 secoes: "Esta Semana" (acoes imediatas), "Proximos 30 Dias" (validacao e iteracao), "Melhoria Continua" (longo prazo). Cada tarefa deve ter: descricao acionavel, prazo relativo (quando possivel), e conexao com o bloco que a gerou. Sempre que o agente define algo, cria a tarefa correspondente. No Bloco 6 (posicionamento) especialmente: criar tarefas para executar rapido (criar/ajustar Instagram, configurar bio, montar portfolio, configurar WPP Business, etc.). Se `tarefas.md` nao existe no momento do checkpoint, CRIE-O.
```

---

## TIER 2 — Degradam qualidade do output de agentes

### G6 — `prova` / cases com numeros ausentes

**Gap:** Diferencial sem evidencia. Proposta comercial fica sem case para provar resultado.

**Secao do prompt:**
- Bloco 4 — Output (linha 548): `formula_diferencial`, `postura`, `hard_skills[]`, `soft_skills[]`, `mecanismo_unico`
- Bloco 4 — Processo (linhas 518-524): 5 passos, nenhum sobre coleta de provas

**Diagnostico:**
O processo do Bloco 4 foca em FORMULAR o diferencial, mas nunca pede ao builder para PROVAR. Nao ha passo que pergunte "tem algum numero, case ou depoimento que comprove isso?" O output nao inclui campo para provas. Para builders avancados, a calibracao (linha 323) menciona "prova + mecanismo unico", mas nao ha instrucao de como coletar.

**Edicao 6a — Bloco 4, Processo (apos passo 5, linha 524):**

```
ADICIONAR:
6. **Coletar provas:** Pergunte ao builder: "Tem algum numero, case, depoimento ou resultado mensuravel que PROVE esse diferencial?" Se SIM: registrar. Se NAO (especialmente iniciante/intermediario): registrar como `prova: a_construir` com orientacao: "Nos proximos 3 projetos, registre antes/depois com numeros." NUNCA deixar o campo ausente — provas vazias sao informacao util (indicam que o builder precisa construir cases).
```

**Edicao 6b — Bloco 4, Output (linha 548):**

```
ANTES:
**Output:** `formula_diferencial`, `postura`, `hard_skills[]`, `soft_skills[]`, `mecanismo_unico`

DEPOIS:
**Output:** `formula_diferencial`, `postura`, `hard_skills[]`, `soft_skills[]`, `mecanismo_unico`, `prova[{tipo, descricao, metricas}]`

Onde `tipo` = "case" | "depoimento" | "metrica" | "a_construir". Se nenhuma prova existe, registrar: `prova: [{tipo: a_construir, descricao: "Registrar antes/depois nos proximos 3 projetos", metricas: null}]`
```

**Edicao 6c — Bloco 4, Perguntas-guia (apos linha 541):**

```
ADICIONAR:
8. Tem algum resultado mensuravel de um projeto? Antes/depois, numeros, depoimentos?
9. Se nao tem case ainda, qual seria o primeiro resultado que voce quer documentar?
```

---

### G7 — `como_apresentar` ausente (script de proposta)

**Gap:** Sem script de apresentacao, agente de vendas nao sabe a ordem, ancoragem ou down-sell.

**Secao do prompt:**
- Bloco 5 — Sub-processos (linhas 567-652): Define Popstar, Big Idea, Escada, Composicao, Nomeacao, Precificacao
- Bloco 5 — Output (linhas 714-716): NAO inclui script de apresentacao

**Diagnostico:**
O Bloco 5 define O QUE vender com excelencia (escada de valor, composicao de pacotes), mas nao define COMO apresentar. Nao ha:
- Ordem de apresentacao (premium primeiro para ancorar? ou entrada primeiro?)
- Script de down-sell (quando e como oferecer o pacote menor)
- Lista de objecoes comuns com respostas preparadas
- Template de proposta comercial

**Edicao 7a — Bloco 5, adicionar sub-processo (inserir apos 5.10, linha 686):**

```
ADICIONAR:
**5.11 Script de Apresentacao:**

O agente DEVE definir com o builder a estrategia de apresentacao dos pacotes:

1. **Ordem de apresentacao:** Regra geral — apresentar o PRINCIPAL primeiro (nao o premium e nao o entrada). O principal e a solucao completa para a dor. Depois, se o cliente hesita, o down-sell (entrada) como alternativa.

2. **Ancoragem:** Sempre mostrar a soma dos avulsos ANTES do preco do pacote. "Se voce contratasse tudo separado, pagaria R$X. No pacote, fica R$Y."

3. **Down-sell:** NUNCA baixar preco — REDUZIR ESCOPO. "Se o investimento completo nao cabe agora, a gente comeca por [pacote entrada] que resolve [fragmento da dor]."

4. **Objecoes comuns:** O agente pergunta ao builder: "Quais sao as 3 objecoes que voce mais ouve?" e prepara respostas. Objecoes tipicas:
   - "Ta caro" → mostrar custo de NAO resolver (quanto perde por mes)
   - "Preciso pensar" → "Claro, enquanto isso me conta: qual parte te interessou mais?"
   - "Conheco alguem que faz mais barato" → "O preco do outro inclui [lista de entregaveis]?"
   - "Nao preciso de tudo isso" → down-sell para entrada

5. **Perguntas-guia especificas:**
   - Quando um cliente diz "ta caro", como voce responde hoje?
   - Voce apresenta o preco por WhatsApp, ligacao ou reuniao?
   - Ja fez down-sell (oferecer versao menor quando o completo nao fechou)?
```

**Edicao 7b — Bloco 5, Output (substituir linhas 714-716):**

```
ANTES:
**Output:**
- **Servicos individuais:** `servicos_individuais[{nome, descricao, preco_unitario}]`
- **Pacotes:** `nome_oferta`, `escopo[]`, `entregaveis[{nome, preco_individual}]` (minimo 2), `preco`, `soma_avulsos`, `economia_percentual`, `modelo_cobranca`, `escada_valor{entrada, principal, premium, recorrencia}`
- **Precificacao:** `gatilho_aumento_ticket`

DEPOIS:
**Output:**
- **Servicos individuais:** `servicos_individuais[{nome, descricao, preco_unitario}]`
- **Pacotes:** `nome_oferta`, `escopo[]`, `entregaveis[{nome, preco_individual}]` (minimo 2), `preco`, `soma_avulsos`, `economia_percentual`, `modelo_cobranca`, `escada_valor{entrada, principal, premium, recorrencia}`
- **Precificacao:** `gatilho_aumento_ticket`
- **Apresentacao:** `servico_carro_chefe`, `como_apresentar{ordem[], ancoragem, downsell_script, objecoes_comuns[{objecao, resposta}]}`
```

---

### G8 — `sinais_de_bom_cliente` ausentes

**Gap:** Agente de qualificacao nao sabe identificar se um lead e bom.

**Secao do prompt:**
- Bloco 2 — Perguntas-guia (linhas 427-435): Pergunta 1 e "Quais foram seus 3 melhores clientes?" e pergunta 8 e "Se pudesse clonar um cliente, quem seria?"
- Bloco 2 — Output (linha 446): NAO inclui `sinais_de_bom_cliente` nem `cliente_a_clonar`

**Diagnostico:**
As perguntas-guia CAPTURAM a informacao (melhores clientes, clonar cliente), mas o output nao tem campo para armazenar. O dado fica na conversa e se perde.

**Edicao 8 — Bloco 2, Output (linha 446):**

```
ANTES:
**Output:** `area_setor`, `porte_empresa{faturamento, equipe, investimento_marketing}`, `comportamento_digital`, `momento_empresa`, `filtros_exclusao[]`

DEPOIS:
**Output:** `area_setor`, `porte_empresa{faturamento, equipe, investimento_marketing}`, `comportamento_digital`, `momento_empresa`, `filtros_exclusao[]`, `sinais_de_bom_cliente[]`, `onde_encontrar[]`, `cliente_a_clonar`
```

Os campos adicionados:
- `sinais_de_bom_cliente[]` — 3 a 5 indicadores observaveis (ex: "ja investe em trafego", "tem urgencia", "responde rapido"). Derivado da pergunta-guia 1.
- `onde_encontrar[]` — canais de prospeccao concretos (ex: "Google Maps bairro X", "Instagram #hashtag", "indicacao de clientes atuais"). Derivado da heuristica H2.3.
- `cliente_a_clonar` — perfil do melhor cliente passado. Derivado da pergunta-guia 8.

---

### G9 — `onde_encontrar` ausente

**Gap:** Sem canais de prospeccao definidos, o builder nao sabe onde buscar clientes.

**Diagnostico e Edicao:** Ja coberto em G8 (campo `onde_encontrar[]` adicionado ao output do Bloco 2).

**Edicao adicional 9 — Bloco 2, Perguntas-guia (apos linha 435):**

```
ADICIONAR:
9. Onde seu ICP fica online? Instagram, LinkedIn, Google? E offline? (eventos, associacoes, rua?)
10. Se precisasse de 5 clientes novos esta semana, onde voce iria procurar?
```

---

### G10 — `clientes_necessarios` (calculo) ausente no output

**Gap:** Meta sem decomposicao matematica explicita no output.

**Secao do prompt:**
- Bloco 7 — Processo, passo 8 (linhas 943-965): Decomposicao matematica COMPLETA com exemplo concreto
- Bloco 7 — Output (linha 995): Inclui `decomposicao_meta{meta_mensal, ticket_medio, clientes_necessarios, ...}`

**Diagnostico:**
O prompt JA TEM tanto o processo (passo 8) quanto o campo no output. O problema e de ENFORCEMENT — o agente nao seguiu a instrucao. Duas possiveis causas:
1. O passo 8 e o ULTIMO do processo (facil de cortar)
2. Nao ha validacao que verifique se a decomposicao foi feita

**Edicao 10a — Bloco 7, reforcar no processo (inserir apos passo 8, linha 965):**

```
ADICIONAR:
**REGRA: A meta NAO esta completa sem decomposicao matematica.** O agente DEVE fazer o calculo COM o builder (nao pular para "defina sua meta"). Se o builder diz "quero fazer R$15.000", o agente IMEDIATAMENTE decompoe: "R$15.000 / R$2.800 (ticket) = 6 clientes/mes. Com taxa de conversao de 20%, voce precisa enviar 30 propostas/mes, ou ~7/semana. Isso significa ~14 contatos/semana, ou 3 por dia. Da pra fazer com 25h/semana?" Se a decomposicao mostra inviabilidade, CONFRONTE: "Com sua capacidade atual de 4 projetos/mes, a meta de 6 nao fecha. Vamos ajustar?"
```

**Edicao 10b — Bloco 7, Output (reforcar linha 995):**

```
ANTES:
**Output:** `ticket_medio`, `clientes_mes`, `faturamento_alvo`, `criterio_subir_preco`, `capacidade_entrega`, `decomposicao_meta{meta_mensal, ticket_medio, clientes_necessarios, taxa_conversao, propostas_semana, contatos_semana, acao_diaria}`

DEPOIS:
**Output:** `ticket_medio`, `clientes_mes`, `faturamento_alvo`, `criterio_subir_preco`, `capacidade_entrega`, `viavel{resposta, justificativa}`, `decomposicao_meta{meta_mensal, ticket_medio, clientes_necessarios, recorrencia_esperada, restante_projetos, projetos_necessarios, taxa_conversao, propostas_semana, contatos_semana, acao_diaria}`, `projecao_cenarios{pessimista, bom, excelente}`

NOTA: `viavel` e um veredito explicito — "a meta e alcancavel com a capacidade e pipeline atuais?" Resposta sim/nao com justificativa matematica. O campo `decomposicao_meta` DEVE ter TODOS os sub-campos preenchidos com numeros calculados, nao apenas o faturamento_alvo.
```

---

### G11 — `decomposicao_matematica` desestruturada

**Gap:** Projecoes existem como texto, nao como calculo estruturado verificavel.

**Diagnostico e Edicao:** Ja coberto em G10. O output atualizado inclui `decomposicao_meta` com todos os sub-campos numericos obrigatorios e `viavel` com justificativa.

---

### G12 — `bio_camadas` (dor/autoridade/CTA) decompostas

**Gap:** A bio existe mas nao esta decomposta em camadas funcionais. Agente reescrevendo bio nao sabe qual parte e qual.

**Secao do prompt:**
- Bloco 6, 6.1 — Bio (linhas 756-768): Define 3 linhas (servico + dor + valor) + CTA separada
- Bloco 6 — Output (linha 914): `bio{linha1_servico, linha2_dor, linha3_valor, cta}`

**Diagnostico:**
O prompt JA decompoe a bio em partes (`linha1_servico`, `linha2_dor`, `linha3_valor`, `cta`), mas usa nomenclatura de "linhas" (sequencia visual) em vez de "camadas" (funcao). A auditoria pede uma decomposicao FUNCIONAL (camada_dor, camada_autoridade, camada_cta) que facilite a reescrita por agentes.

**Edicao:** Ja coberta em G4 (Edicao 4b). O output atualizado inclui `bio_camadas{camada_dor, camada_autoridade, camada_cta}` como campo complementar a `bio`.

**Edicao adicional 12 — Bloco 6, 6.1, apos estrutura da bio (inserir apos linha 768):**

```
ADICIONAR:
**Decomposicao funcional (bio_camadas):**
Alem das 3 linhas + CTA, registrar a bio decomposta por FUNCAO:
- `camada_dor`: Qual pedaco da bio comunica a dor do ICP? (geralmente Linha 2)
- `camada_autoridade`: Qual pedaco comunica credibilidade/prova? (geralmente Linha 1 + Linha 3, ou elemento_autoridade se existir)
- `camada_cta`: Qual pedaco filtra e convida a acao? (CTA)
Se `camada_autoridade` esta vazia (builder sem case/metrica ainda), registrar como `a_construir` com nota: "Incorporar quando cases estiverem consolidados — priorizar metrica mensuravel."
```

---

## TIER 3 — Melhorias desejaveis

### G13 — `frustracoes[]` e `desejos[]` sem estrutura `{frase, contexto}`

**Gap:** Arrays de strings simples. O formato `{frase, contexto}` e muito mais util para agentes.

**Secao do prompt:**
- Bloco 3 — Output (linha 501): `frustracoes[]`, `desejos[]` (arrays simples)

**Diagnostico:**
O output define como array flat. A versao com contexto (`{frase: "...", contexto: "..."}`) permite que agentes usem a frustracao com contexto situacional, gerando comunicacao mais relevante.

**Edicao:** Ja coberta em G2 (Edicao 2b). O output atualizado do Bloco 3 muda para `frustracoes[{frase, contexto}]` e `desejos[{frase, contexto}]`.

**Edicao adicional 13 — Bloco 3, Perguntas-guia, ajustar fraseamento:**

```
ANTES (pergunta generica):
5. Qual frustracao faz seu cliente perder o sono?

DEPOIS (pede contexto):
5. Qual frustracao faz seu cliente perder o sono? Me da a situacao: quando acontece, o que ele estava tentando fazer?
```

Aplicar a mesma logica a TODAS as perguntas sobre frustracoes e desejos — sempre pedir a frase + o contexto situacional.

---

### G14 — `cliente_a_clonar` no YAML (existe so no README)

**Gap:** Dado acionavel que existe no README mas nao no _dados.yaml. Agentes leem YAML, nao Markdown.

**Diagnostico e Edicao:** Ja coberto em G8. O campo `cliente_a_clonar` foi adicionado ao output do Bloco 2.

**Edicao adicional 14 — Regras de output (inserir apos linha 1090):**

```
ADICIONAR:
- **REGRA: Todo dado acionavel DEVE estar no `_dados.yaml`.** O README.md e para LEITURA HUMANA e pode conter contexto narrativo, exemplos e explicacoes. Mas qualquer dado que um agente precisaria para executar uma tarefa (nomes, numeros, listas, configuracoes) DEVE estar no YAML correspondente. Se um dado aparece no README mas nao no YAML, mova-o. READMEs complementam, YAMLs sao a fonte da verdade para agentes.
```

---

### G15 — Bloco `evolucao` repetido em todos os YAML com texto quase identico

**Gap:** O campo `evolucao` e copiado identicamente em TODOS os `_dados.yaml`, poluindo dados e confundindo agentes.

**Secao do prompt:**
- Secao 11 — EVOLUCAO DO BUILDER (linhas 1424-1437): Manda incluir em cada bloco e arquivo
- Secao 7 — Formato dos _dados.yaml (linhas 1126-1139): Template com `evolucao` obrigatorio

**Diagnostico:**
A Secao 11 explicitamente manda registrar `evolucao` em "cada bloco e arquivo" com `serie_atual`, `pontos_de_melhoria`, `como_evolui`, `revisar_quando`. Isso causa:
1. Repeticao de `serie_atual` (ja esta no perfil.yaml)
2. `como_evolui` identico em todos ("Atendendo clientes e revisitando este plano")
3. Confusao para agentes: 7 campos `evolucao` com dados quase identicos

**Edicao 15a — Secao 11 (substituir linhas 1424-1437):**

```
ANTES:
## 11. EVOLUCAO DO BUILDER

Em cada bloco e arquivo, registre:

```yaml
evolucao:
  serie_atual: iniciante | intermediario | avancado
  pontos_de_melhoria:
    - "Item especifico identificado na conversa"
  como_evolui: "Atendendo clientes e revisitando este plano"
  revisar_quando: "Apos X clientes atendidos"
```

O builder melhora FAZENDO, nao estudando. Cada revisita da skill e uma chance de refinar com dados reais. Incentive o builder a voltar apos cada lote de clientes.

DEPOIS:
## 11. EVOLUCAO DO BUILDER

A evolucao do builder e registrada em UM UNICO LUGAR: `.builder/perfil.yaml`. NAO repetir `evolucao` em cada `_dados.yaml`.

```yaml
# Em perfil.yaml (unico lugar):
evolucao:
  serie_atual: iniciante | intermediario | avancado
  pontos_de_melhoria:
    - "Item especifico identificado na conversa"
  como_evolui: "Atendendo clientes e revisitando este plano"
  revisar_quando: "Apos X clientes atendidos"
```

Cada `_dados.yaml` dos blocos inclui apenas:
```yaml
revisar_quando: "Apos X clientes atendidos"  # criterio especifico DESTE bloco
```

O builder melhora FAZENDO, nao estudando. Cada revisita da skill e uma chance de refinar com dados reais. Incentive o builder a voltar apos cada lote de clientes.
```

**Edicao 15b — Formato dos _dados.yaml (substituir linhas 1126-1139):**

```
ANTES:
Cada arquivo segue o schema de output do bloco correspondente. Todos incluem:
```yaml
versao: 1
bloco: "nome_do_bloco"
data_atualizacao: "YYYY-MM-DD"
# ... campos especificos do bloco ...
evolucao:
  serie_atual: ""
  pontos_de_melhoria: []
  como_evolui: "Atendendo clientes e revisitando este plano"
  revisar_quando: ""
status: "em_construcao"
```

DEPOIS:
Cada arquivo segue o schema de output do bloco correspondente. Todos incluem:
```yaml
versao: 1
bloco: "nome_do_bloco"
data_atualizacao: "YYYY-MM-DD"
# ... campos especificos do bloco ...
revisar_quando: ""  # criterio especifico deste bloco (ex: "Apos 5 clientes com esse ICP")
status: "em_construcao"
```

NOTA: `evolucao` com serie, pontos_de_melhoria e como_evolui fica APENAS em `perfil.yaml`. Nao repetir nos _dados.yaml.
```

---

## RECOMENDACOES DA AUDITORIA (R1-R6)

### R1 — Forcar criacao de `memory.yaml` e `tarefas.md`

**Status:** Coberto por G1 e G5. Edicoes 1a, 1b, 1c e 5a.

### R2 — Adicionar campos obrigatorios faltantes ao schema de output

**Status:** Coberto por G2, G6, G7, G8 e G10. Resumo dos campos adicionados:

| Bloco | Campos adicionados |
|-------|-------------------|
| 2 (ICP) | `sinais_de_bom_cliente[]`, `onde_encontrar[]`, `cliente_a_clonar` |
| 3 (Dor) | `vocabulario_icp[]`, `tom`, `frustracoes[{frase,contexto}]`, `desejos[{frase,contexto}]` (mudanca de formato) |
| 4 (Diferencial) | `prova[{tipo, descricao, metricas}]` |
| 5 (Pacotes) | `servico_carro_chefe`, `como_apresentar{ordem[], ancoragem, downsell_script, objecoes_comuns[]}` |
| 6 (Posicionamento) | `bio_camadas{camada_dor, camada_autoridade, camada_cta}` |
| 7 (Meta) | `viavel{resposta, justificativa}`, sub-campos adicionais em `decomposicao_meta`, `projecao_cenarios` |

### R3 — Eliminar bloco `evolucao` repetitivo

**Status:** Coberto por G15. Edicoes 15a e 15b.

### R4 — Integrar memory-spec no SKILL.md

**Status:** JA FEITO. O system prompt atual (linhas 142-290) ja contem a secao "MEMORIA PERSISTENTE" com instrucoes completas. Esta recomendacao da auditoria pode ter sido baseada numa versao anterior do prompt. O problema nao e a ausencia da spec, e sim o enforcement (coberto por G1).

### R5 — Adicionar validacao de output pos-checkpoint

**Gap:** Nao ha auto-verificacao apos gravar uma parede.

**Secao do prompt:**
- ETAPA 4 — REGISTRAR (linhas 94-97): Nao inclui validacao
- Checklist Final (linhas 1442-1459): So verifica no final da sessao completa, nao a cada parede

**Edicao R5 — Inserir nova sub-secao apos ETAPA 4 (apos linha 97):**

```
ADICIONAR:
### 3.2.1 Validacao Pos-Checkpoint

Apos gravar CADA parede, o agente executa uma verificacao silenciosa (nao mostra ao builder a menos que encontre problema):

1. **Schema completo?** Todos os campos do output do bloco estao presentes no _dados.yaml?
   - Se faltar campo: preencher com `null` ou `a_definir`, mas o campo DEVE existir.
2. **Dados sao concretos?** Algum campo tem valor generico/placeholder ("qualquer", "varios", "bom")?
   - Se generico: confrontar o builder — "Voce escreveu '[valor generico]'. Me da algo mais concreto."
3. **Usavel por agente?** Os dados seriam suficientes para OUTRO agente executar uma tarefa (proposta, post, atendimento)?
   - Teste rapido: "Se eu pedisse a outro agente para criar uma proposta usando APENAS esses dados, ele conseguiria?"
4. **Arquivos auxiliares?** memory.yaml existe? tarefas.md existe? Ambos atualizados?
   - Se ausente: criar ANTES de avancar para o proximo bloco.
5. **Dados no YAML?** Algum dado acionavel esta APENAS no README sem correspondente no YAML?
   - Se sim: mover para o YAML.
```

### R6 — Separar dados de posicionamento tatico

**Gap:** O Bloco 6 mistura posicionamento (estrategico) e presenca digital (tatica) no mesmo arquivo.

**Secao do prompt:**
- Bloco 6 (linhas 720-914): Cobre tudo em um unico bloco

**Diagnostico:**
O Bloco 6 ja e o MAIOR do prompt (194 linhas). Ele mistura:
- Posicionamento estrategico: frase-mae, bio, linguagem
- Presenca digital tatica: Instagram, WhatsApp, Behance, configuracoes

A separacao em dois arquivos YAML (ex: `posicionamento/_dados.yaml` + `presenca-digital/_dados.yaml`) e desejavel mas tem custo de complexidade na estrutura.

**Edicao R6 — Alternativa mais simples (sem mudar estrutura de pastas):**

Manter em um unico `posicionamento/_dados.yaml`, mas organizar com secoes claras:

```
ADICIONAR ao Bloco 6, Regras de output (apos a REGRA DE COMPLETUDE adicionada em G4):

**Organizacao do _dados.yaml do Bloco 6:**
O YAML do posicionamento deve ser organizado em 2 secoes claras:

```yaml
# === POSICIONAMENTO (estrategico) ===
frase_posicionamento: ""
linguagem_icp: []
bio:
  linha1_servico: ""
  linha2_dor: ""
  linha3_valor: ""
  cta: ""
bio_camadas:
  camada_dor: ""
  camada_autoridade: ""
  camada_cta: ""
elemento_autoridade: ""

# === PRESENCA DIGITAL (tatico) ===
instagram_perfil: { ... }
instagram_destaques: [ ... ]
instagram_posts_fixados: [ ... ]
link_bio: { ... }
whatsapp: { ... }
behance: { ... }
grade_conteudo_status: ""
```

Isso permite que agentes acessem o posicionamento estrategico sem parsear toda a configuracao tatica, e vice-versa.
```

---

## RESUMO DE EDICOES

### Por secao do system prompt:

| Secao | Edicoes | Gaps cobertos |
|-------|---------|---------------|
| Regra 8 (linha 41) | 1a | G1, G5 |
| ETAPA 4 (linhas 94-97) | 1b | G1, G5 |
| Bloco 2 — Output (linha 446) | 8 | G8, G9, G14 |
| Bloco 2 — Perguntas-guia (linha 435) | 9 | G9 |
| Bloco 3 — Processo (linha 471) | 2a | G2, G3 |
| Bloco 3 — Output (linha 501) | 2b | G2, G3, G13 |
| Bloco 3 — Perguntas-guia (linha 487) | 2c, 13 | G2, G3, G13 |
| Bloco 4 — Processo (linha 524) | 6a | G6 |
| Bloco 4 — Output (linha 548) | 6b | G6 |
| Bloco 4 — Perguntas-guia (linha 541) | 6c | G6 |
| Bloco 5 — Novo sub-processo 5.11 (apos linha 686) | 7a | G7 |
| Bloco 5 — Output (linhas 714-716) | 7b | G7 |
| Bloco 6 — Regra de completude (apos linha 878) | 4a | G4 |
| Bloco 6 — Output (linha 914) | 4b | G4, G12 |
| Bloco 6 — Bio camadas (apos linha 768) | 12 | G12 |
| Bloco 6 — Organizacao YAML | R6 | R6 |
| Bloco 7 — Processo, enforcement (apos linha 965) | 10a | G10, G11 |
| Bloco 7 — Output (linha 995) | 10b | G10, G11 |
| Nova sub-secao 3.2.1 (apos linha 97) | R5 | R5 |
| Regras de output (linha 1090) | 14 | G14 |
| Regras de output — tarefas.md (linha 1095) | 5a | G5 |
| Secao 11 — Evolucao (linhas 1424-1437) | 15a | G15 |
| Formato _dados.yaml (linhas 1126-1139) | 15b | G15 |
| Checklist Final (apos linha 1459) | 1c | G1, G5, G14 |

### Por prioridade de implementacao:

**Lote 1 — Enforcement (resolve G1, G5, R5):**
Edicoes 1a, 1b, 1c, 5a, R5. Essas garantem que memory.yaml, tarefas.md sejam criados e que haja validacao pos-checkpoint.

**Lote 2 — Campos faltantes nos outputs (resolve G2, G3, G6, G7, G8, G9, G13, G14):**
Edicoes 2a, 2b, 2c, 6a, 6b, 6c, 7a, 7b, 8, 9, 13, 14. Adicionam todos os campos ausentes nos schemas de output.

**Lote 3 — Posicionamento e bio (resolve G4, G12, R6):**
Edicoes 4a, 4b, 12, R6. Reforcam completude do Bloco 6 e adicionam decomposicao funcional da bio.

**Lote 4 — Meta operacional (resolve G10, G11):**
Edicoes 10a, 10b. Reforcam decomposicao matematica e veredito de viabilidade.

**Lote 5 — Limpeza (resolve G15):**
Edicoes 15a, 15b. Eliminam repeticao do bloco `evolucao`.

---

## PROGNOSTICO

Com TODAS as edicoes implementadas:
- Score esperado: **6.5 → 8.5-9/10**
- memory.yaml e tarefas.md passam a ser criados obrigatoriamente
- Todos os campos ausentes passam a ter spec no output
- Validacao pos-checkpoint previne schemas incompletos
- Evolucao deixa de poluir os _dados.yaml
- Agentes downstream (proposta, conteudo, atendimento) passam a ter dados suficientes para executar
