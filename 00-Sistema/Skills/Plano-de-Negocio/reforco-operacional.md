# Reforco Operacional — knowledge-base.md

**Data:** 2026-08-20
**Objetivo:** Preencher as lacunas operacionais identificadas na auditoria (`auditoria-insumos.md`). Este arquivo COMPLEMENTA a `knowledge-base.md` — nao a substitui.
**Fontes:** Material local (transcrições de lives, aulas Easy Sales, arquivos do ecossistema). A busca nos stores Gemini (GEMINI_STORE_CURSO_MB, GEMINI_STORE_TRANSCRICOES, GEMINI_STORE_LORENZI_DNA) falhou por deprecação do modelo `gemini-2.0-flash` — gaps marcados com `[GEMINI]` precisam de enriquecimento quando a API for atualizada para `gemini-3.6-flash`.

**Como o agente deve usar:** Ao guiar um bloco, consultar PRIMEIRO a `knowledge-base.md` (fundamentos, heurísticas, cases, anti-padrões, perguntas, critérios) e DEPOIS este arquivo para processos passo-a-passo, definições operacionais e mapeamento de frameworks.

---

## PRIORIDADE 1 — Bloco 5: Oferta (7 lacunas)

---

### 1.1 Popstar — Processo operacional para identificar o serviço de maior retorno/tempo

**Conceito na KB:** "Popstar = 80/20: Alta demanda, bom lucro, menos tempo, mais resultado." (fundamentos Bloco 5) + H5.1: "Retorno / Tempo: o serviço com maior resultado por hora investida é o carro-chefe."

> "Eu recomendo produtizar. Inclusive tem uma aula incrível sobre produtização de oferta."
> — *Live "O plano e as ferramentas certas pra fazer R$10.000 todo MÊS em 2027" (2:04:37)*

**Processo operacional — Identificar o Popstar:**

1. **Listar TODOS os serviços** que já prestou ou pode prestar (landing page, identidade visual, criativos, membros, checkout, slides, carrossel, consultoria, otimização, manutenção)
2. **Para cada serviço, anotar 3 números:**
   - Tempo médio de execução (em horas)
   - Preço médio cobrado (em R$)
   - Retorno por hora (preço / horas)
3. **Marcar a demanda:** Qual desses serviços os clientes pedem com mais frequência? Qual gera mais indicações?
4. **Cruzar retorno/hora com demanda:** O serviço que tem ALTO retorno/hora E ALTA demanda é o Popstar
5. **Testar a escala:** Esse serviço pode ser replicado para outros clientes sem reinventar? Se sim, é produtizável
6. **Validar:** O Popstar é o pacote que você oferece PRIMEIRO em toda negociação

**Exemplo concreto (extraído da KB):**
- LP 2 dobras com Easy Builder: 3 horas, R$2.000 = **R$630/hora** — candidato a Popstar
- Carrossel para Instagram: 1 hora, R$500 = **R$500/hora** — alto retorno mas baixo ticket
- Pacote de lançamento completo: 40 horas, R$25.000 = **R$625/hora** — alto ticket, alto retorno, Popstar do Lorenzi na época de agência

**Anti-padrão:**
- **ERRO:** Manter serviços de baixo retorno/hora por costume ("sempre fiz identidade visual avulsa")
- **CORREÇÃO:** Aplique o 80/20 — pare de oferecer ativamente os serviços que estão abaixo da média de retorno/hora. Empacote-os dentro do Popstar como componentes, não como produto separado.

`[GEMINI]` Buscar no GEMINI_STORE_CURSO_MB: "aula de produtização de oferta" para extrair o exercício original do Lorenzi sobre a matriz retorno x tempo.

---

### 1.2 Big Idea — Processo passo-a-passo para construir a frase emocional

**Conceito na KB:** "A Big Idea deve ser curta, memorável e tocar no emocional." (fundamentos Bloco 5) + "Converter é obrigação. Te faço ser lembrado." + "Seu último web designer."

> "O posicionamento ele não serve somente para captar clientes, ele serve para filtrar os clientes e atrair os clientes. Ele qualifica ao mesmo tempo que ele atrai. E é meio contraintuitivo, mas quanto mais ele filtra, mais ele atrai."
> — *Live "O plano e as ferramentas certas pra fazer R$10.000 todo MÊS em 2027" (1:23:13)*

**Processo operacional — Construir a Big Idea:**

1. **Resgatar do Bloco 3:** Qual é a `dor_primaria` do seu ICP? (ex: "perdi dinheiro contratando freelancer que entregou página com botão sem link no dia do lançamento")
2. **Resgatar do Bloco 4:** Qual é o `mecanismo_unico` que diferencia você? (ex: "monitoro o lançamento ao vivo e garanto que nada quebra")
3. **Traduzir a transformação em UMA frase:** O que muda na vida do cliente DEPOIS de trabalhar com você? Não o que você FAZ — o que ele SENTE/GANHA.
4. **Testar 3 critérios da Big Idea:**
   - **Curta:** Cabe em 1 linha de bio? Se não, encurte.
   - **Memorável:** Se o cliente ouvir uma vez, lembra amanhã? Se não, simplifique.
   - **Emocional:** Toca na dor OU no desejo profundo do ICP? Se não, reescreva.
5. **Brainstorm iterativo:** Escreva pelo menos 10 versões. Teste com alguém do ICP. A Big Idea certa gera reação imediata ("é exatamente isso que eu preciso").

**Exemplos de Big Ideas (extraídas da KB e lives):**
- "Converter é obrigação. Te faço ser lembrado." — toca no medo de ser mais um
- "Seu último web designer." — promessa de fidelidade e competência
- "Não faço site. Resolvo o problema que o site deveria resolver." — reposiciona a categoria

**Estrutura-template:**
```
[Resultado emocional] + [Diferencial implícito] + [Filtro]
```
Exemplo: "Páginas que vendem sozinhas — pra quem já cansou de pagar por promessa."

**Anti-padrão:**
- **ERRO:** Big Idea genérica: "alta conversão", "LP otimizada", "design profissional"
- **CORREÇÃO:** Se qualquer outro designer poderia usar a mesma frase, NÃO é Big Idea. Deve ser impossível de copiar porque nasce da sua dor resolvida + seu mecanismo único.

`[GEMINI]` Buscar no GEMINI_STORE_CURSO_MB: "Big Idea construção frase emocional" para extrair o exercício original com mais exemplos de brainstorm.

---

### 1.3 Escada de Valor — Definição dos 4 níveis com critérios

**Conceito na KB:** Output field `escada_valor{entrada, principal, premium, recorrencia}` + H5.5 a H5.8 (down-sell, upsell, cross-sell).

> "Agreguem valor, vendam a solução e não um trampo isolado."
> — *Easy Sales, Planejamento, Aula 03*

**Definição operacional dos 4 níveis:**

| Nível | Nome | Função | Critérios | Exemplo (KB) |
|-------|------|--------|-----------|--------------|
| 1 | **Entrada / Down-sell** | Primeira transação. Reduz risco. Prova competência. | Ticket baixo (10-30% do principal). Escopo reduzido mas entrega COMPLETA dentro do escopo. NUNCA baixar preço — reduzir entregáveis. | Pacote "Minimalista": só venda + captura = R$3.500 (down-sell de R$6.797) |
| 2 | **Principal** | Carro-chefe. O Popstar produtizado. Resolve a dor do ICP de ponta a ponta. | Ticket compatível com série do builder. Pacote nomeado. Inclui o 80/20 dos entregáveis. | Pacote "Lançamento Semente" = R$4.500 (soma avulsa R$5.300) |
| 3 | **Premium / Upsell** | Expansão para quem quer mais. Regra dos 20%: 20% dos compradores pagam até 8x mais. | Ticket 2-8x o principal. Inclui acompanhamento, consultoria, ou entrega ampliada. Sempre PRONTO antes do cliente pedir. | Pacote "Lançamento Completo" (agência) = R$25.000 |
| 4 | **Recorrência / Cross-sell** | Receita previsível. Reter custa menos que adquirir. | Cobrança mensal. Baixo esforço do builder. Alto valor percebido. Vinculado a resultado contínuo. | Suporte R$100/mês ou Teste AB R$250/mês. 4 clientes = R$1.000 extra em ~4h |

**Processo operacional — Montar a escada:**

1. **Comece pelo Principal:** Qual é o seu Popstar produtizado? (vem do exercício 1.1)
2. **Defina o Down-sell:** Retire entregáveis do Principal até chegar num escopo mínimo que ainda resolve algo. Preço = 30-50% do Principal.
3. **Defina o Premium:** Adicione ao Principal: acompanhamento pós-entrega, consultoria de resultado, segundo projeto, otimização. Preço = 2-5x o Principal.
4. **Defina a Recorrência:** O que você pode oferecer todo mês com pouco esforço? (suporte, teste AB, manutenção, relatório mensal, monitoramento)
5. **Ancoragem obrigatória:** Sempre apresente do Premium para baixo. Cliente vê o pacote maior primeiro — o Principal parece bom negócio.

**Anti-padrão:**
- **ERRO:** Ter só o Principal e nada mais — viver de one-shot.
- **CORREÇÃO:** Mínimo 2 degraus (entrada + principal) no dia 1. Ideal: 3+ degraus antes de escalar captação.
- **ERRO:** Oferecer desconto quando cliente pede.
- **CORREÇÃO:** "Posso ajustar o escopo. Vamos ver o que é essencial pra você agora." → down-sell, não desconto.

---

### 1.4 Nomeação de Pacotes — Como nomear pelo contexto do CLIENTE

**Conceito na KB:** "Entregáveis devem virar 'produtos nomeados' (pacotes)" (fundamentos) + H5.3: "Agrupe por metodologia do cliente, não por tipo de página" + H5.10: "Crie pacotes por contexto."

**Processo operacional — Dar nome ao pacote:**

1. **NÃO nomeie pelo serviço:** "Pacote LP + Identidade" descreve o que VOCÊ faz, não o que o CLIENTE precisa. Isso iguala você ao concorrente.
2. **Nomeie pelo CONTEXTO do cliente:**
   - Qual metodologia ele usa? (lançamento, perpétuo, high ticket, posicionamento)
   - Qual momento ele está? (começando, escalando, reestruturando)
   - Qual resultado ele busca? (captação, conversão, retenção, percepção)
3. **Use a linguagem do ICP (Bloco 2):** O nome deve ser compreensível pelo cliente sem explicação.
4. **Teste de unicidade:** Pesquise o nome no Google/Instagram. Se muita gente usa, mude.
5. **Crie ancoragem com o nome:** Nome premium deve SOAR premium. Nome de entrada deve ser acessível.

**Exemplos de nomes BEM construídos (da KB):**

| Contexto do cliente | Nome do pacote | Por que funciona |
|---------------------|---------------|------------------|
| Lançamento de infoproduto, primeiro | "Lançamento Semente" | Fala o método do cliente (semente), não "LP + membros + checkout" |
| Posicionamento digital, começando | "Posicionamento Digital" | Fala o resultado (posicionar), não "bio + posts + links" |
| High ticket, sessão estratégica | "High Ticket" | Fala o modelo de venda do cliente, não "formulário + captura + anúncio" |
| Oferta com down-sell | "Premium" / "Minimalista" | Hierarquia clara sem desvalorizar o menor |

**Exemplos de nomes que NÃO funcionam:**
- "Pacote Básico / Intermediário / Avançado" — genérico, sem vínculo com o cliente
- "Pacote LP Responsiva" — descreve entregável, não transformação
- "Pacote Completo" — vago, impossível de ancorar

**Anti-padrão:**
- **ERRO:** Dar nomes internos/técnicos para os pacotes ("Pack Web Design 3.0")
- **CORREÇÃO:** O nome do pacote é parte do posicionamento. Ele comunica pra QUEM é e QUAL resultado entrega.

---

### 1.5 Proposta Comercial — Como apresentar pacotes ao cliente

**Conceito na KB:** H6.2: "Proposta comercial com copy vende melhor que proposta padrão — mockups, diferenciais e benefícios na proposta já é posicionamento."

> "Tem proposta comercial, proposta que eu usava aqui. Você pega e edita isso daqui. Você edita e manda pro teu cliente do teu jeito. Tem vários tipos diferentes de propostas que você simplesmente replica e usa."
> — *Live "Re-abertura Teste Grátis" (4:44:10)*

**Processo operacional — Estrutura da proposta:**

1. **Abertura com contexto:** Resumo do problema do cliente (mostra que você ouviu). 2-3 frases. Linguagem DELE, não sua.
2. **Diagnóstico:** O que você identificou como raiz do problema. Demonstra competência sem ser arrogante.
3. **Solução proposta:** Nome do pacote + entregáveis listados com benefício de cada um. Cada item responde "por que isso importa pra você?"
4. **Mockup / referência visual:** Se possível, uma prévia do resultado. Aumenta valor percebido drasticamente.
5. **Prova social:** 1-2 cases relevantes para o contexto do cliente. Com números.
6. **Investimento (ancoragem):** Apresentar valor total dos avulsos PRIMEIRO → depois preço do pacote. Desconto implícito.
7. **CTA claro:** Próximo passo concreto ("me responde com OK que eu monto o briefing" ou "agenda uma call de 15min").

**Anti-padrão:**
- **ERRO:** Mandar preço solto por WhatsApp ("a LP fica 1.750")
- **CORREÇÃO:** Sempre contextualizar. Preço sem proposta = commodity. Proposta com copy = posicionamento.

> "Mandando 1.750, você perdeu a chance de vender 5.300."
> — *knowledge-base.md, anti-padrão Bloco 5*

- **ERRO:** Proposta em PDF genérico sem personalização
- **CORREÇÃO:** Cada proposta deve ter o nome do cliente, a dor DELE e pelo menos 1 mockup/referência específica.

`[GEMINI]` Buscar no GEMINI_STORE_CURSO_MB e GEMINI_STORE_SOPS: "proposta comercial estrutura template" para extrair o template editável que o Lorenzi disponibiliza no Arsenal.

---

### 1.6 Valor Percebido vs Custo Real

**Conceito na KB:** "A percepção de valor funciona como reciprocidade — entregar mais do que cobra faz o cliente sentir que o serviço vale mais." (Bloco 3) + "Over delivery é entregar mais DENTRO do produto, não algo avulso." (Bloco 5)

> "Não é sobre quanto teu trampo cobra, é sobre quanto teu trampo vale."
> — *knowledge-base.md, Bloco 1*

> "Tudo para aumentar o meu valor percebido. Naturalmente eu cobrava muito mais que a maioria."
> — *Live "O plano e as ferramentas certas pra fazer R$10.000 todo MÊS em 2027" (2:19:20)*

**Definição operacional:**

- **Custo real** = tempo + ferramentas + esforço que o builder investe na entrega
- **Valor percebido** = quanto o CLIENTE acha que aquilo vale, baseado em: (1) dor que resolve, (2) confiança no profissional, (3) qualidade visível, (4) escassez do serviço, (5) posicionamento do builder

**A equação fundamental:**
```
Valor percebido > Preço cobrado > Custo real
```
Se `valor percebido < preço` → cliente acha caro, não fecha.
Se `preço < custo real` → builder perde dinheiro.
Se `valor percebido >> preço` → cliente sente que fez um bom negócio. Indica. Volta.

**Como aumentar valor percebido sem aumentar custo:**

1. **Posicionamento (Bloco 6):** Bio, autoridade, linguagem — mudam a percepção ANTES do cliente falar com você
2. **Over delivery interno:** Melhorar o que já entrega (qualidade do design, favicon, redirect, meta tags, LGPD, loading) — sem adicionar serviço novo. "A qualidade do corte, não uma flor extra."
3. **Proposta com copy (1.5):** A forma de apresentar muda a percepção de valor
4. **Prova social com números:** Cases com métricas (R$600k de diferença, 90% connect rate) tornam o valor concreto
5. **Escassez real:** Demanda > capacidade → preço sobe naturalmente. "É neste momento que você sobe o preço."

**Exemplo concreto (KB + lives):**
- Easy Optimize: 12% de aumento no connect rate = R$600.000 a mais num lançamento. Custo real para o Lorenzi: algumas horas de consultoria. Valor percebido: incalculável. Ticket cobrado: R$10.000+ por consultoria.
- Carrossel na época de agência: R$500 por peça. Custo real: ~1h de trabalho. Valor percebido alto porque entregava qualidade que o cliente não encontrava em outros designers.

**Anti-padrão:**
- **ERRO:** Precificar pelo custo ("gastei 3h, cobro R$150/hora = R$450")
- **CORREÇÃO:** Precifique pelo VALOR que gera. "Quanto o cliente ganha/economiza com isso?" É o ponto de partida.
- **ERRO:** Achar que aumentar valor = aumentar entregáveis
- **CORREÇÃO:** Aumentar valor = melhorar a percepção. Posicionamento, prova social, qualidade interna e proposta bem feita fazem mais que adicionar serviços novos.

---

### 1.7 Modelo Condicional — Precificação por resultado

**Conceito na KB:** H5.11: "Precificação condicional por resultado: 'Se não melhorar X, custa Y. Se melhorar, custa Z.'" + FM9: "Preço base + bônus atrelado a resultado. Alinha incentivos, reduz objeção, abre porta para ticket alto."

**Definição operacional:**

O modelo condicional divide o preço em duas camadas:
- **Base fixa:** Cobre o custo real + margem mínima. O builder recebe independente do resultado.
- **Bônus por resultado:** Atrelado a uma métrica mensurável e acordada previamente. Só cobra se o resultado acontecer.

**Quando aplicar:**

| Situação | Aplicar? | Por quê |
|----------|----------|---------|
| Cliente com alto potencial mas receoso com ticket | SIM | Reduz objeção: "se não funcionar, paga menos" |
| Métrica de resultado é claramente mensurável (CPL, connect rate, conversão, vendas) | SIM | Alinha incentivos: builder e cliente querem o mesmo |
| Builder tem controle direto sobre o resultado | SIM | Faz sentido apostar porque você influencia |
| Resultado depende de fatores fora do controle (mercado, tráfego do cliente) | COM CUIDADO | Defina a métrica sobre algo que VOCÊ controla (ex: taxa de conversão da página, não faturamento total) |
| Cliente desorganizado, sem dados, sem tráfego | NÃO | Sem baseline, sem como medir. Primeiro organize, depois condicione. |

**Como estruturar:**

1. **Definir a métrica-base:** O que será medido? (ex: connect rate da página de captura)
2. **Definir o baseline:** Qual é o número ATUAL? (ex: connect rate atual = 25%)
3. **Definir o alvo:** Qual melhoria é realista? (ex: connect rate > 35%)
4. **Definir o preço base:** Valor que cobre seu trabalho independente do resultado (ex: R$3.000)
5. **Definir o bônus:** Valor adicional se atingir o alvo (ex: +R$5.000 se connect rate > 35%)
6. **Colocar em contrato:** Métrica, baseline, alvo, prazo de medição, forma de comprovação

**Exemplo numérico (derivado da KB):**
- Baseline: connect rate 25%
- Preço base: R$3.000 (cobre custo + margem)
- Se connect rate > 35%: +R$5.000 (ticket total R$8.000)
- Se connect rate > 40%: +R$8.000 (ticket total R$11.000)
- Resultado real do Lorenzi em case similar: 12% de aumento = R$600.000 a mais pro cliente. Ticket de R$10.000+ justificado.

**Anti-padrão:**
- **ERRO:** Condicionar 100% do pagamento ao resultado (trabalhar "de graça" primeiro)
- **CORREÇÃO:** Sempre ter base fixa. Bônus é adicional, não o pagamento inteiro.
- **ERRO:** Usar métrica vaga ("se o cliente gostar")
- **CORREÇÃO:** Métrica numérica, mensurável, com baseline documentado antes de começar.

`[GEMINI]` Buscar no GEMINI_STORE_CURSO_MB: "precificação condicional por resultado como estruturar contrato" para extrair exemplos adicionais das aulas.

---

## PRIORIDADE 2 — Processos passo-a-passo (Blocos 2, 4, 6)

---

### 2.1 Bloco 2 (ICP) — Processo guiado para definir o cliente ideal

**Fonte primária:** Easy Sales, Funil Anti Prospecção, Aula 06 (extraído de `fundamentos.md`, arquivo local).

**Processo operacional — 9 passos sequenciais:**

> "Em que área ou setor quem precisa do seu trampo atua? Lembrando, não precisa ser nicho."
> — *Easy Sales, Funil Anti Prospecção, Aula 06*

**Passo 1 — Definir a área ou setor**
- Responder por escrito: "Em que área ou setor quem precisa do seu trampo atua?"
- Não se prender a um nicho único — pode ser conjunto de setores semelhantes (ex: "marketing digital com foco em infoprodutos através de lançamentos")
- Se não tiver clientes, pesquisar no LinkedIn e Google Maps empresas do possível segmento

**Passo 2 — Definir o momento do cliente**
- Quanto esse cliente já investe em marketing/tráfego pago?
- Quantas pessoas tem na equipe?
- Quanto já faturou?
- Posta ou não no Instagram?
- Já fez lançamento ou é o primeiro?
- Se não souber: pesquisar no ChatGPT, comentários YouTube, seguir pessoas do segmento

> "Qual o momento desse cliente? [...] Aqui como referência, investe aproximadamente 50 mil reais por lançamento apenas em tráfego pago."
> — *Easy Sales, Funil Anti Prospecção, Aula 06*

**Passo 3 — Definir se vende produtos ou serviços**
- Anotar o formato (infoprodutos, cursos, mentorias, serviço local, e-commerce, SaaS)

**Passo 4 — Definir faturamento médio**
- Estimar faturamento médio do setor (ex: "~R$300k por lançamento ou R$100k/mês")
- Isso determina o porte da empresa e o ticket que pode pagar

> "Com base na estimativa você consegue determinar o porte da empresa."
> — *Easy Sales, Funil Anti Prospecção, Aula 06*

**Passo 5 — Definir tamanho da equipe**
- Estimar quantas pessoas trabalham (ex: "3 pessoas, uma atendente e dois vendedores")

**Passo 6 — Definir nível de consciência**
- O público sabe que tem um problema a ser resolvido?
- Se NÃO sabe: você vai precisar educá-lo (mais esforço, funil mais longo)
- Se JÁ sabe: está disposto a pagar por solução (venda mais direta)

**Passo 7 — Listar frustrações do público**
- Dores específicas e recorrentes (ex: "leads caros, comparecimento caindo, conversão caindo, freelancer que atrasa")

> "Quais são as principais frustrações desse público no dia a dia?"
> — *Easy Sales, Funil Anti Prospecção, Aula 06*

**Passo 8 — Listar desejos do público**
- O que esse público quer alcançar (ex: "melhorar CPL, aumentar CTR, aumentar connect rate, diminuir CAC")

**Passo 9 — Definir como VOCÊ garante a solução (ponte pro Bloco 4)**
- Descrever como resolve a dor e a frustração identificadas — isso já é o diferencial

> "Como você garante essa solução? Que agora vai entrar o teu diferencial."
> — *Easy Sales, Funil Anti Prospecção, Aula 06*

**Validação:** Após os 9 passos, aplicar o filtro de exclusão triplo (H2.2): sem consciência de marketing + sem dinheiro + vai dar dor de cabeça = NÃO é público-alvo. O builder deve conseguir descrever o ICP em 2 frases sem usar a palavra "qualquer".

---

### 2.2 Bloco 4 (Diferencial) — Exercício guiado para preencher "Através de [X], resolvo [Y] e entrego [Z]"

**Conceito na KB:** H4.1: "Fórmula do diferencial: 'Através de [método], resolvo [dor específica] e entrego [resultado mensurável].'"

**A auditoria identificou:** O template existe, mas não há processo de como o aluno CHEGA a preenchê-lo.

**Processo operacional — 5 passos:**

**Passo 1 — Resgatar hard skills (do Bloco 1)**
- Pegar a lista de `competencias[]` do Bloco 1
- Separar em: Hard Skills (técnicas: Elementor, Figma, CSS, otimização, GTM, tráfego) e Soft Skills (postura: comunicação, proatividade, presença, honestidade)

**Passo 2 — Resgatar a dor do ICP (do Bloco 3)**
- Pegar `dor_primaria` e `frustracoes[]` do Bloco 3
- Identificar a dor que aparece com mais frequência nos seus clientes reais

**Passo 3 — Cruzar e encontrar a interseção rara (FM4)**
- Pergunta-chave: "Qual combinação de hard skill + soft skill eu tenho que é DIFÍCIL de encontrar no mercado?"
- Framework FM4 (Hard+Soft=Escassez): Poucos têm técnica E postura. Quem tem ambos é raro e caro.
- Exemplos de interseção rara: design de alta qualidade + monitoramento ao vivo de lançamento / otimização de performance + comunicação direta com equipe de tráfego / construção de página + consultoria de funil

**Passo 4 — Listar comportamentos concretos de presença**
- O diferencial não pode ficar em conceito ("sou comprometido"). Deve virar comportamentos:
  - Conferir todos os links 24h antes do lançamento
  - Enviar relatório pós-projeto sem ser pedido
  - Participar do debriefing do lançamento
  - Migrar página quando há problema no servidor, mesmo fora do escopo
  - Alertar o cliente sobre erro de tráfego que você notou
- Pergunta: "Qual AÇÃO concreta eu faço que 95% dos designers NÃO fazem?"

**Passo 5 — Preencher a fórmula**
- [X] = A interseção rara do Passo 3 (seu método / sua combinação única)
- [Y] = A dor específica do Passo 2 (o que o cliente mais sofre)
- [Z] = O resultado mensurável que você gera (com número quando possível)

**Exemplo preenchido (derivado da KB):**
- "Através de [infraestrutura invisível — server-side, GTM, pixel, otimização], resolvo [a dor de lançamentos que quebram por falha técnica] e entrego [+12% de connect rate que equivale a R$600k a mais no faturamento do cliente]."

**Anti-padrão:**
- **ERRO:** Preencher com genéricos: "Através de [design profissional], resolvo [necessidade de site] e entrego [uma LP bonita]"
- **CORREÇÃO:** Se qualquer designer poderia dizer a mesma coisa, não é diferencial. Volte ao Passo 3 e busque a interseção rara.

`[GEMINI]` Buscar no GEMINI_STORE_CURSO_MB: "diferencial exercício hard skill soft skill interseção" para extrair o exercício original de construção do diferencial.

---

### 2.3 Bloco 6 (Posicionamento) — Como construir a bio camada por camada + CTA/filtro

**Conceito na KB:** "Bio em 3 camadas: (1) abraçar a dor → (2) tocar vaidade → (3) gerar escassez." + H6.4: "Framework da bio: Transformação → Autoridade → CTA"

> "A sua foto precisa comunicar que você é confiável por causa da percepção de valor. O seu perfil inteiro precisa demonstrar isso ao mesmo tempo que mostra pro público específico a solução que você entrega, o resultado que você gera."
> — *Live "O plano e as ferramentas certas pra fazer R$10.000 todo MÊS em 2027" (1:22:11)*

**Processo operacional — Construir a bio em 5 passos:**

**Passo 1 — Camada 1: Abraçar a dor (Transformação)**
- Resgatar `dor_primaria` do Bloco 3
- Escrever uma linha que ABRAÇA a dor do ICP — mostra que você entende o problema antes de oferecer solução
- Deve usar a linguagem do CLIENTE (H6.1), não jargão de designer
- Exemplo: "Cansei de ver lançamento quebrar por página mal feita"

**Passo 2 — Camada 2: Tocar vaidade (Autoridade)**
- Resgatar `mecanismo_unico` do Bloco 4 e `elemento_autoridade`
- Escolher UMA métrica de autoridade que é:
  - Verificável (pode provar)
  - Difícil de copiar (não é genérico)
  - Específica (com número)
- Evitar: "especialista em X" (todo mundo diz). Preferir: proxy de investimento ("R$30M investidos nas páginas que criei") ou resultado mensurável ("1M de leads captados com 90% connect rate")
- Exemplo: "+R$30M em investimento passaram pelas minhas páginas"

**Passo 3 — Camada 3: Gerar escassez (CTA/Filtro)**
- O CTA deve FILTRAR quem entra em contato (H6.3)
- Mensagem pré-formatada no WhatsApp que já usa linguagem técnica do ICP
- Se o cara não entende o CTA, ele não é seu público — e isso é BOM
- Exemplo: "Se você investe em tráfego e quer connect rate acima de 90%, me chama" — quem não sabe o que é connect rate, não é ICP

**Passo 4 — Brainstorm iterativo (Caminho Neural passo 8)**
- Escrever no mínimo 10 versões da bio completa
- Para cada versão, testar: "Se eu fosse meu ICP e lesse isso, eu mandaria mensagem?"
- Pedir feedback de 2-3 pessoas que são do perfil do ICP
- NÃO aceitar a primeira versão

**Passo 5 — Validar com os critérios do Bloco 6**
- [ ] Bio tem as 3 camadas? (dor + autoridade + escassez/CTA)
- [ ] Promessa é diferente de "alta conversão" ou "LP otimizada"?
- [ ] Autoridade é verificável e difícil de copiar?
- [ ] CTA filtra — ou qualquer pessoa mandaria mensagem?
- [ ] Linguagem usa termos que o CLIENTE entende?

**Exemplos lado a lado:**

| Bio RUIM | Bio BOA |
|----------|---------|
| Web designer \| Sites profissionais \| Entrega rápida \| DM aberta | Páginas que vendem sozinhas. +R$30M investidos nas minhas entregas. Se você investe em tráfego e quer parar de perder lead, me chama. |
| Designer especialista em LP de alta conversão. Portfólio no link. | Converter é obrigação. Te faço ser lembrado. Seu último web designer. |

**Anti-padrão:**
- **ERRO:** Copiar bio de outro designer
- **CORREÇÃO:** Se lê algo que está na bio de outro designer, seria equiparado. Cada palavra justifica existência.

> "Se lê algo que tá na bio de outro designer, iria me equiparar."
> — *knowledge-base.md, Bloco 6*

- **ERRO:** Bio que atrai todo tipo de cliente
- **CORREÇÃO:** "Se atrai todo mundo, teu posicionamento é ruim." Quanto mais filtra, mais atrai o certo.

---

## PRIORIDADE 3 — Mapeamento de Frameworks (FM1-FM12)

---

### 3.1 Tabela de mapeamento: Framework → Blocos → Gatilho de ativação

O agente deve consultar esta tabela ao guiar QUALQUER bloco. Quando o contexto da conversa ativar o gatilho, referenciar o framework pelo nome e aplicar.

| FM | Nome | Blocos | Gatilho — QUANDO o agente deve acionar | Como aplicar |
|----|------|--------|---------------------------------------|--------------|
| FM1 | 80/20 do Funil | 3, 5, 7 | Aluno está listando muitas ações/serviços sem priorizar | "Onde está o 80/20? Qual ÚNICA ação gera o maior impacto?" Forçar priorização. |
| FM2 | Cenário Pessimista / Bom / Excelente | 7 | Aluno está definindo meta ou avaliando risco | "Projete 3 cenários com métricas ANTES de começar." Remove ansiedade e cria referência. |
| FM3 | Sênior que Toca o Setor | 1, 4 | Aluno descreve seu trabalho como executor de tarefas | "Você é gerente de área, não executor. Faz reunião com tráfego, cobra copy, monitora KPIs." Elevar postura. |
| FM4 | Hard + Soft = Escassez | 1, 4 | Aluno pergunta por que deveria cobrar mais / não se sente diferente | "A interseção de técnica E postura é RARA. Quem tem ambos é difícil de substituir." Usar no exercício do diferencial (2.2, Passo 3). |
| FM5 | Metáfora do Balde | 1, 5, 7 | Aluno quer escalar captação sem ter resolvido problemas de entrega | "Não adianta abrir a torneira se o balde tem furo." Primeiro tapar furos, depois captar. |
| FM6 | Lateralização de Nicho | 2 | Aluno está preso a um nicho vertical ("só atendo advocacia") | "Corte transversal por COMPORTAMENTO, não vertical por setor." Empresários de R$100k+ existem em todos os nichos. |
| FM7 | Efeito Ímã | 2, 6 | Aluno diz que atrai todo tipo de cliente ou cliente ruim | "Posicionamento = frequência magnética. Se atrai todo mundo, a frequência está errada." Revisar bio e comunicação. |
| FM8 | Eu + Cliente vs Problema | 4 | Aluno descreve sua relação com cliente como comprador/vendedor | "Parceiro de trincheira, não fornecedor. A relação é aliança contra um inimigo comum." Reposicionar postura. |
| FM9 | Precificação Condicional | 5 | Aluno tem serviço mensurável mas não sabe como cobrar ticket alto | "Preço base + bônus atrelado a resultado." Usar processo 1.7 deste documento. |
| FM10 | Frustração Inversa | 3, 4 | Aluno não identifica seu diferencial ou não vê dor do mercado | "O diferencial vem de RESOLVER a dor que o próprio mercado causa." Ser o oposto do que o cliente já sofreu. |
| FM11 | Jardineiro vs Cortador de Grama | 3, 4, 5 | Aluno descreve sua oferta como entregável isolado (LP, identidade) | "Cortador de grama = entrega e manda pix. Jardineiro = cuida do ambiente. Quem cuida, fideliza." Empacotar como solução. |
| FM12 | Converter é Obrigação | 5, 6 | Aluno usa "alta conversão" como proposta de valor | "Todo designer diz isso. O diferencial é ser MEMORÁVEL." Redirecionar para Big Idea e experiência. |

### 3.2 Regra para o agente

Ao iniciar qualquer bloco, verificar na tabela acima quais FMs se aplicam. Manter em memória ativa durante a conversa. Quando o gatilho ocorrer:

1. Nomear o framework ("isso é o FM5 — Metáfora do Balde")
2. Explicar brevemente (1-2 frases)
3. Aplicar ao contexto específico do aluno
4. Registrar no output que o FM foi utilizado

---

## Apêndice — Limitações e próximos passos

### Fontes consultadas (local)

| Arquivo | Conteúdo relevante extraído |
|---------|---------------------------|
| `knowledge-base.md` | Base completa — fundamentos, heurísticas, cases, anti-padrões de todos os 7 blocos |
| `auditoria-insumos.md` | Diagnóstico detalhado de cada lacuna |
| `fundamentos.md` (Downloads) | Passo-a-passo ICP da Aula 06 Easy Sales |
| `gestao.md` (Downloads) | Metas, precificação, processo de venda da Aula 03 Easy Sales |
| `aula-03-raw.md` (Downloads) | Aula 03 "Como Bater Suas Metas" — precificação por meta diária |
| Live `e28c1cad7f88e242.txt` | "O plano e as ferramentas certas pra fazer R$10.000 todo MÊS em 2027" — posicionamento, produtização, flywheel, 8020 |
| Live `a892bef3ae8a78a5.txt` | "Re-abertura Teste Grátis" — proposta comercial, arsenal do web designer |

### Gaps que requerem Gemini (API indisponível)

| Gap | Busca recomendada | Store |
|-----|-------------------|-------|
| Popstar — exercício original da aula de produtização | "produtização oferta matriz retorno tempo exercício" | GEMINI_STORE_CURSO_MB |
| Big Idea — processo de brainstorming com mais exemplos | "Big Idea construção frase emocional brainstorm" | GEMINI_STORE_CURSO_MB |
| Proposta comercial — template editável do Arsenal | "proposta comercial estrutura template editável" | GEMINI_STORE_CURSO_MB + GEMINI_STORE_SOPS |
| Modelo condicional — exemplos de contrato e casos de uso | "precificação condicional resultado contrato estrutura" | GEMINI_STORE_CURSO_MB |
| Exercício diferencial — aula original de hard skill + soft skill | "diferencial exercício hard skill soft skill interseção escassez" | GEMINI_STORE_CURSO_MB |
| Bio — exercício de brainstorm iterativo com exemplos antes/depois | "bio posicionamento brainstorm iterativo camadas" | GEMINI_STORE_CURSO_MB |

### Ação técnica pendente

A API Gemini Search está usando o modelo `gemini-2.0-flash` que foi depreciado. Para restaurar o acesso aos stores de conteúdo do curso:

1. Localizar a configuração do MCP server `gemini-search`
2. Atualizar o modelo de `models/gemini-2.0-flash` para `models/gemini-3.6-flash`
3. Re-executar as 6 buscas listadas acima
4. Enriquecer as seções marcadas com `[GEMINI]` neste documento
