# Knowledge Base v2 — Plano 10K (Metodo Antiprospecao)

Base de conhecimento do agente conversacional que guia web designers/builders na construcao do plano de negocio. O agente opera em ciclo: **FUNDAMENTAR -> GUIAR -> VALIDAR -> REGISTRAR** para cada bloco.

**v2 — Consolidacao:** Este arquivo unifica a `knowledge-base.md` (fundamentos, heuristicas, cases, anti-padroes, perguntas, criterios) com o `reforco-operacional.md` (processos passo-a-passo, definicoes operacionais, mapeamento de frameworks). Conteudo do reforco esta marcado com `[VALIDAR]` quando pode estar generico/sintetizado (nao extraido diretamente das aulas) e com `[GEMINI]` quando a sessao anterior nao conseguiu preencher por falta de acesso aos stores de conteudo.

---

## Bloco 1 — Contexto do Builder (Quem Sou Eu)

Frameworks aplicaveis: FM3 (Senior que Toca o Setor), FM4 (Hard + Soft = Escassez), FM5 (Metafora do Balde)

### 1.1 Objetivo

Mapear a realidade atual do builder — faturamento, competencias, tempo, ferramentas e nivel — para calibrar todo o restante do plano.

### 1.2 Fundamentos

O equilibrio ideal do builder e **produtividade + posicionamento**: cobrar preco justo e entregar rapido gera o melhor retorno por tempo investido.

> "Esse aqui e o 80/20 do conteudo. Nao subestimem isso."

Mentalidade e comportamento representam 80% do que determina resultado; tecnica e apenas 20%.

A evolucao de preco acontece **naturalmente** quando se entrega mais do que cobra. Nao e uma decisao arbitraria — e consequencia de competencia demonstrada.

> "Nao e sobre quanto teu trampo cobra, e sobre quanto teu trampo vale."

Ser builder significa usar ferramentas (e quando necessario criar as suas) para resolver problemas de alto valor no menor tempo possivel.

### 1.3 Processo de Construcao

`[GEMINI]` Processo de construcao do diagnostico de contexto pessoal nao foi extraido das aulas na sessao anterior. Buscar no GEMINI_STORE_CURSO_MB: "diagnostico contexto builder faturamento competencias nivel" para extrair o exercicio original do Lorenzi.

**Sequencia minima sugerida:** `[VALIDAR]`

1. **Levantar numeros reais:** Faturamento dos ultimos 3 meses, numero de projetos entregues, horas disponiveis por semana
2. **Inventario de competencias:** Listar TODAS as ferramentas e habilidades, classificando cada uma como basico/intermediario/avancado
3. **Auto-classificacao de serie:** Cruzar faturamento + portfolio + confianca para definir se e iniciante, intermediario ou avancado
4. **Validacao cruzada:** A serie declarada e coerente com os numeros? Se diz avancado mas fatura 2K, ha incongruencia — ajustar

### 1.4 Heuristicas

- **H1.1** Se esta no inicio (horizontal), foque no meio-termo entre volume e qualidade. Se ja esta no meio-termo, foque na escala vertical — especializacao + ticket mais alto.
- **H1.2** Iniciante deve cobrar barato, fechar clientes reais, adquirir experiencia e montar portfolio. Preco sobe conforme competencia sobe.
- **H1.3** Trabalhar de graca e valido **SE** for com intencionalidade — para clientes que geram portfolio forte, indicacoes ou contratos futuros.
- **H1.4** Aprenda por engenharia reversa: Ads Library + `sitemap.xml` de lancamentos reais para mapear funis completos.

### 1.5 Cases e Exemplos

- Builder iniciante que cobrava R$500 e achou "desrespeito" — nao fechou nenhum cliente por 3 meses. Ao ajustar para preco compativel com seu nivel, fechou 4 clientes no mes seguinte e montou portfolio real.
- Lorenzi: comecou cobrando barato, entregou acima do esperado sistematicamente, e a evolucao de preco veio como consequencia natural da demanda crescente.

### 1.6 Anti-padroes

- **ERRO:** Iniciante se recusar a cobrar barato por achar "desrespeito" — resultado: nao fecha nenhum cliente.
  **CORRECAO:** No inicio, experiencia e portfolio valem mais que ticket alto. O preco sobe quando a competencia justifica.

- **ERRO:** Adicionar servicos novos (ex: copywriting via ChatGPT) sem competencia consolidada no servico principal.
  **CORRECAO:** Foco no que domina primeiro. So expandir quando o core estiver solido.

- **ERRO:** Nao saber quanto fatura ou quanto tempo tem disponivel — operar no escuro.
  **CORRECAO:** Numeros reais antes de qualquer plano. Sem diagnostico, qualquer meta e chute.

### 1.7 Perguntas-guia

1. Quanto voce faturou nos ultimos 3 meses com servicos de web design/builder?
2. Quais sao suas 3 competencias mais fortes hoje — as que entrega com mais velocidade e qualidade?
3. Quantas horas por semana voce tem disponiveis para trabalhar em projetos de clientes?
4. Quais ferramentas voce domina? (Elementor, Webflow, Framer, Easy Builder, Figma, etc.)
5. Quantos projetos ja entregou no total? E nos ultimos 6 meses?
6. Voce se considera iniciante, intermediario ou avancado? Por que?
7. De 0 a 10, quanto voce se sente confiante para atender um cliente que fatura R$100k/mes?

### 1.8 Criterios de Validacao

- [ ] `meta_faturamento` preenchido com valor numerico real (nao estimativa vaga)
- [ ] Pelo menos 3 competencias listadas com nivel de dominio (basico/intermediario/avancado)
- [ ] `tempo_disponivel` definido em horas/semana — compativel com meta de faturamento desejada
- [ ] `serie_atual` classificada coerentemente com faturamento e portfolio declarados
- [ ] Ferramentas listadas correspondem as competencias declaradas

### 1.9 Output esperado (campos do JSON)

`meta_faturamento`, `competencias[]`, `tempo_disponivel`, `ferramentas[]`, `serie_atual` (iniciante / intermediario / avancado)

---

## Bloco 2 — ICP / Publico-Alvo (Pra Quem)

Frameworks aplicaveis: FM6 (Lateralizacao de Nicho), FM7 (Efeito Ima)

### 2.1 Objetivo

Definir com precisao o perfil de cliente ideal usando comportamento, porte e momento — nao nicho vertical.

### 2.2 Fundamentos

Publico-alvo se define por **padroes de comportamento, porte e momento** — NAO pelo segmento vertical (nicho).

> "O mercado, o nicho, nao e tao importante quanto o porte do cliente."

Nicho pode ajudar a delimitar comunicacao, mas nao e obrigatorio nem limitante. Visao lateralizada: varios nichos compartilham o mesmo padrao de comportamento e necessidade.

> "Nao se apeguem ao nicho."

Quando se tenta falar com todo mundo, nao se conecta com ninguem. Funciona como um ima — a frequencia certa atrai o compativel e repele o incompativel.

> "Quem e atraido e so quem ta compativel com aquilo que eu to comunicando."

O momento da empresa, capacidade de investimento e dores determinam o publico. A definicao de publico-alvo **NAO e fixa** — deve ser ajustada frequentemente conforme o builder evolui.

> "Isso aqui tem que ser ajustado frequentemente."

Numero de seguidores nao e metrica confiavel. Metricas solidas: investimento em marketing, faturamento, tamanho da equipe.

O ICP e definido por **momento de vida e nivel de consciencia** — o cliente ideal ja se frustrou, ja contratou errado, esta disposto a pagar mais por seguranca.

### 2.3 Processo de Construcao

Fonte primaria: Easy Sales, Funil Anti Prospecao, Aula 06. `[VALIDAR]`

**Processo operacional — 9 passos sequenciais:**

> "Em que area ou setor quem precisa do seu trampo atua? Lembrando, nao precisa ser nicho."
> — *Easy Sales, Funil Anti Prospecao, Aula 06*

**Passo 1 — Definir a area ou setor**
- Responder por escrito: "Em que area ou setor quem precisa do seu trampo atua?"
- Nao se prender a um nicho unico — pode ser conjunto de setores semelhantes (ex: "marketing digital com foco em infoprodutos atraves de lancamentos")
- Se nao tiver clientes, pesquisar no LinkedIn e Google Maps empresas do possivel segmento

**Passo 2 — Definir o momento do cliente**
- Quanto esse cliente ja investe em marketing/trafego pago?
- Quantas pessoas tem na equipe?
- Quanto ja faturou?
- Posta ou nao no Instagram?
- Ja fez lancamento ou e o primeiro?
- Se nao souber: pesquisar no ChatGPT, comentarios YouTube, seguir pessoas do segmento

> "Qual o momento desse cliente? [...] Aqui como referencia, investe aproximadamente 50 mil reais por lancamento apenas em trafego pago."
> — *Easy Sales, Funil Anti Prospecao, Aula 06*

**Passo 3 — Definir se vende produtos ou servicos**
- Anotar o formato (infoprodutos, cursos, mentorias, servico local, e-commerce, SaaS)

**Passo 4 — Definir faturamento medio**
- Estimar faturamento medio do setor (ex: "~R$300k por lancamento ou R$100k/mes")
- Isso determina o porte da empresa e o ticket que pode pagar

> "Com base na estimativa voce consegue determinar o porte da empresa."
> — *Easy Sales, Funil Anti Prospecao, Aula 06*

**Passo 5 — Definir tamanho da equipe**
- Estimar quantas pessoas trabalham (ex: "3 pessoas, uma atendente e dois vendedores")

**Passo 6 — Definir nivel de consciencia**
- O publico sabe que tem um problema a ser resolvido?
- Se NAO sabe: voce vai precisar educa-lo (mais esforco, funil mais longo)
- Se JA sabe: esta disposto a pagar por solucao (venda mais direta)

**Passo 7 — Listar frustracoes do publico**
- Dores especificas e recorrentes (ex: "leads caros, comparecimento caindo, conversao caindo, freelancer que atrasa")

> "Quais sao as principais frustracoes desse publico no dia a dia?"
> — *Easy Sales, Funil Anti Prospecao, Aula 06*

**Passo 8 — Listar desejos do publico**
- O que esse publico quer alcancar (ex: "melhorar CPL, aumentar CTR, aumentar connect rate, diminuir CAC")

**Passo 9 — Definir como VOCE garante a solucao (ponte pro Bloco 4)**
- Descrever como resolve a dor e a frustracao identificadas — isso ja e o diferencial

> "Como voce garante essa solucao? Que agora vai entrar o teu diferencial."
> — *Easy Sales, Funil Anti Prospecao, Aula 06*

**Validacao pos-processo:** Apos os 9 passos, aplicar o filtro de exclusao triplo (H2.2): sem consciencia de marketing + sem dinheiro + vai dar dor de cabeca = NAO e publico-alvo. O builder deve conseguir descrever o ICP em 2 frases sem usar a palavra "qualquer".

### 2.4 Heuristicas

- **H2.1** 5 dimensoes do ICP: (1) Area/setor, (2) Momento do cliente, (3) Tipo de produto/servico que vendem, (4) Faturamento estimado, (5) Tamanho da equipe.
- **H2.2** Filtro de exclusao triplo: sem consciencia de marketing **+** sem dinheiro **+** vai dar dor de cabeca -> NAO e publico-alvo.
- **H2.3** Google Maps para prospeccao local: buscar empresas do setor, verificar se sites tem problemas que voce resolve.
- **H2.4** Usar GPT para estimar dados de mercado (faturamento medio, porte tipico) quando nao tem informacao direta.
- **H2.5** Se aparecer cliente fora do nicho mas sua solucao resolve o problema dele, **ATENDA**. Nicho e farol, nao barreira.
- **H2.6** Fontes de pesquisa: GPT, comentarios YouTube, seguir pessoas do segmento, LinkedIn, Google Maps.
- **H2.7** Usar perguntas de onboarding/briefing para investigar investimento real e faturamento — dados que o cliente nem sempre voluntaria.

### 2.5 Cases e Exemplos

- **ICP infoprodutos:** Marketing digital, foco em lancamentos. Investe ~R$50k por lancamento em trafego. Fatura ~R$300k por lancamento ou R$100k/mes recorrente.
- **ICP negocio local:** 4-8 funcionarios, faturamento minimo R$70k/mes, vendem pela internet, investem em trafego pago.
- **ICP do Dinis:** Pai de familia, casado, empresario digital, quer escalar mas contrata incompetentes. Motivacao profunda: tempo e seguranca para a familia. Fechou com Junior porque se identificou com os valores — nao pelo preco.
- **Prospeccao via Google Maps:** Dezenas de empresas de energia solar encontradas, muitas sem site ou com site amador — oportunidade clara.

### 2.6 Anti-padroes

- **ERRO:** Definir publico apenas pelo nicho ("meu nicho e advocacia").
  **CORRECAO:** Definir por porte, momento e investimento. Advocacia e setor, nao publico-alvo.

- **ERRO:** Ser generico ("atendo qualquer empresa que precise de site").
  **CORRECAO:** Aplicar filtro triplo de exclusao. Nem toda empresa que "precisa de site" e cliente.

- **ERRO:** Usar seguidores como criterio principal de porte.
  **CORRECAO:** Metricas solidas — trafego real, faturamento declarado, tamanho da equipe, investimento em ads.

- **ERRO:** Querer atender todos os tipos de servico ao mesmo tempo.
  **CORRECAO:** Focar onde resolve com mais facilidade e maior retorno por tempo.

- **ERRO:** Tratar nicho como limitacao rigida e recusar clientes fora dele.
  **CORRECAO:** Nicho direciona comunicacao, nao impede negocios. Se resolve a dor, atenda.

### 2.7 Perguntas-guia

1. Quais foram seus 3 melhores clientes ate hoje? O que eles tinham em comum?
2. Qual o faturamento minimo que seu cliente ideal precisa ter para pagar seu servico sem pestanejar?
3. Quantas pessoas tem na equipe do seu cliente tipico?
4. Seu cliente ideal ja investe em marketing digital ou voce teria que convence-lo?
5. Que tipo de produto ou servico seu cliente vende? (infoproduto, servico local, SaaS, e-commerce?)
6. Em que momento da jornada esta o cliente ideal? (comecando, escalando, reestruturando?)
7. Quais tipos de cliente voce NAO quer atender — e por que?
8. Se pudesse clonar um cliente que ja teve, quem seria e por que?

### 2.8 Criterios de Validacao

- [ ] `area_setor` definido com pelo menos 1 segmento — mas ICP descrito por comportamento, nao so por setor
- [ ] `porte_empresa` com pelo menos 2 das 3 metricas preenchidas (faturamento, equipe, investimento)
- [ ] `filtros_exclusao[]` com pelo menos 2 criterios claros de "quem NAO atendo"
- [ ] `momento_empresa` descrito — o agente verifica se e coerente com a oferta do builder
- [ ] Builder consegue descrever seu ICP em 2 frases sem usar a palavra "qualquer"

### 2.9 Output esperado (campos do JSON)

`area_setor`, `porte_empresa{faturamento, equipe, investimento_marketing}`, `comportamento_digital`, `momento_empresa`, `filtros_exclusao[]`

---

## Bloco 3 — Dor e Problema (O Que Resolver)

Frameworks aplicaveis: FM1 (80/20 do Funil), FM10 (Frustracao Inversa), FM11 (Jardineiro vs Cortador de Grama)

### 3.1 Objetivo

Identificar a dor real do cliente ideal — a raiz emocional e operacional, nao o sintoma tecnico.

### 3.2 Fundamentos

Nem todo cliente sabe que tem problema. O empreendedor que nao investe em marketing pode nao ter consciencia de que perde oportunidades todos os dias.

Frustracao com freelancers e dor **recorrente e estrutural**: atrasos, erros, falta de comprometimento.

> "Chega no dia do lancamento a pagina ta sem link no botao."

A dor primaria do cliente ideal (maduro) **NAO** e falta de design — e **perda de tempo com retrabalho**.

A dor se desdobra em **cadeia causal**: contrata errado -> retrabalho -> para de focar no 80/20 -> menos dinheiro -> menos tempo com familia -> ansiedade.

> "Seja uma ponte entre a dor e o problema."

Existem dois mercados paralelos: prestacao de servico ("faco LP por X") vs resolucao de problemas (a "mina de ouro"). Quem opera no segundo, ganha exponencialmente mais.

> "Eu nao quero saber se voce edita no Cap Cut ou no Premiere. Eu quero o meu problema resolvido."

A percepcao de valor funciona como reciprocidade — entregar mais do que cobra faz o cliente sentir que o servico vale mais. O cliente ideal ja se frustrou com promessas genericas de "alta conversao". Nao cai mais nesse discurso.

### 3.3 Processo de Construcao

`[GEMINI]` Processo de construcao para mapeamento de dor e problema nao foi extraido das aulas na sessao anterior. Buscar no GEMINI_STORE_CURSO_MB: "mapeamento dor problema cadeia causal 5 porques exercicio" para extrair o exercicio original.

**Sequencia minima sugerida:** `[VALIDAR]`

1. **Pesquisa de campo:** Investigar dores reais em comentarios YouTube do nicho, GPT, canais de referencia do segmento, e clientes atuais
2. **Tecnica dos 5 Porques:** Para cada dor identificada, perguntar "por que?" repetidamente ate chegar na raiz emocional (seguranca, tempo, familia)
3. **Mapeamento da cadeia causal:** Desenhar a sequencia completa: sintoma -> consequencia operacional -> consequencia financeira -> consequencia emocional
4. **Traducao para linguagem do cliente:** Reescrever a dor usando as palavras que o CLIENTE usaria, nao termos tecnicos do builder
5. **Identificacao do 80/20:** Qual ponto do funil/operacao do cliente gera maior impacto com menor esforco? Esse e o ponto de entrada
6. **Exercicio de empatia:** "Quanto tempo/esforco o cliente precisa investir para me pagar X? Estou recompensando na mesma medida?"

### 3.4 Heuristicas

- **H3.1** Para descobrir dor real: pergunte "por que?" repetidamente ate a raiz emocional (seguranca, tempo, familia). Tecnica dos 5 porques.
- **H3.2** Venda para quem esta preparado para comprar — o nivel de consciencia do cliente determina se ele vai valorizar seu trabalho.
- **H3.3** Pesquise dores em: comentarios de YouTube do nicho, GPT, canais de referencia do segmento.
- **H3.4** Escuta ativa do cliente atual: "me conta como posso te ajudar" — e genuinamente ouvir.
- **H3.5** Exercicio imaginativo de empatia: "quanto tempo/esforco o cliente precisa investir para me pagar X? Estou recompensando na mesma medida?"

### 3.5 Cases e Exemplos

- **CPLs encarecendo:** CPLs cada vez mais caros, comparecimento nas CPLs caindo, conversao caindo — dor crescente para quem faz lancamentos.
- **Link quebrado no lancamento:** Freelancer entregou pagina com botao sem link no dia do lancamento ao vivo — dor de confianca irreparavel.
- **Advogado de Brasilia:** Concorrente cobrou R$700. Quando ouviu R$3.500, respondeu: "ta certissimo" — ele ja havia se frustrado com o barato.
- **Easy Optimize:** 12% de aumento no connect rate gerou **R$600.000 a mais** num unico lancamento — demonstracao matematica de impacto.
- **Hamburgueria:** Pedidos atrasados por processo manual -> oportunidade de sistema de agendamento. A dor nao era "site feio", era operacao ineficiente.
- **Advogado de 38 anos:** Fechou com Junior porque se identificou com os valores, nao pelo portfolio. Queria mudar de vida.

### 3.6 Anti-padroes

- **ERRO:** Achar que problema do cliente e tecnico (design bonito) quando e operacional (retrabalho, tempo perdido).
  **CORRECAO:** Mapear cadeia de dor completa — do sintoma a raiz emocional.

- **ERRO:** Vender servico em vez de solucao.
  **CORRECAO:** Entender que o cliente compra resultado, nao entregavel.

> "Se voce for esse designer orcamenteiro, acabou."

- **ERRO:** Focar na pagina em vez do resultado.
  **CORRECAO:** A pagina e meio, nao fim.

> "O grande problema do web designer e esse. Ele quer fazer a pagina. A pagina e o de menos."

### 3.7 Perguntas-guia

1. Qual e a maior reclamacao que seus clientes atuais tinham do profissional anterior?
2. Quando seu cliente perde dinheiro, qual e a causa raiz — falta de trafego, pagina ruim, processo quebrado?
3. Se seu cliente pudesse resolver UM problema hoje, qual seria?
4. O que seu cliente ideal deseja que vai alem do entregavel tecnico? (tempo? seguranca? paz?)
5. Qual frustracao faz seu cliente perder o sono — literalmente?
6. Se voce parasse de atender seu melhor cliente amanha, qual seria o impacto real na vida dele?
7. Seu cliente sabe que tem o problema que voce resolve, ou voce precisa educa-lo primeiro?

### 3.8 Criterios de Validacao

- [ ] `dor_primaria` descrita em termos emocionais/operacionais, nao tecnicos
- [ ] `frustracoes[]` com pelo menos 3 itens — vindos de pesquisa real ou experiencia direta
- [ ] `problema_traduzido` e algo que o CLIENTE diria, nao o builder — linguagem do ICP
- [ ] `regra_80_20` identificada: qual ponto do funil/operacao gera maior impacto com menor esforco
- [ ] Builder consegue explicar a cadeia de dor em pelo menos 3 niveis de profundidade

### 3.9 Output esperado (campos do JSON)

`dor_primaria`, `frustracoes[]`, `desejos[]`, `problema_traduzido`, `regra_80_20`

---

## Bloco 4 — Diferencial (Como EU Resolvo)

Frameworks aplicaveis: FM3 (Senior que Toca o Setor), FM4 (Hard + Soft = Escassez), FM8 (Eu + Cliente vs Problema), FM10 (Frustracao Inversa), FM11 (Jardineiro vs Cortador de Grama)

### 4.1 Objetivo

Articular o mecanismo unico do builder — a combinacao de postura, competencias e metodo que o torna dificil de substituir.

### 4.2 Fundamentos

Diferencial nasce de **COMO** voce resolve a dor especifica — nao do que voce faz.

> "Quais sao as frustracoes, como voce ajuda resolver — esse e seu diferencial."

A postura correta e "Eu + cliente **contra** o problema" — parceiro, nao prestador.

> "Isso muda muita coisa."

Confianca vem de **carater**: honra, honestidade, coerencia, servir ativamente — nao de resultado passado ou identificacao superficial.

> "Nao seja um resolvedor de problemas, seja um ANIQUILADOR de problemas. Resolve + previne."

Presenca no trabalho e o diferencial mais subestimado — a maioria faz a entrega "por entregar", le mensagens superficialmente, nao se envolve com o resultado.

Saber servir: ajudar alem do escopo sem cobrar (redirect automatico, dica de lancamento, alerta sobre erro de trafego) gera microtransformacoes que constroem fidelidade.

Design bonito e **REGRA** (table stakes), nao proposta de valor. O diferencial esta na infraestrutura invisivel — server-side, GTM, pixel, otimizacao, dados.

A intersecao **Hard Skills + Soft Skills** explica a escassez: poucos tem tecnica (design, otimizacao, GTM) **E** postura (comunicacao, proatividade, presenca). Quem tem ambos, e raro.

Intimidade com o cliente e vantagem competitiva — conhecer as fragilidades da operacao dele permite atuar onde realmente importa.

### 4.3 Processo de Construcao

Exercicio guiado para preencher a formula do diferencial: "Atraves de [X], resolvo [Y] e entrego [Z]". `[VALIDAR]`

`[GEMINI]` Buscar no GEMINI_STORE_CURSO_MB: "diferencial exercicio hard skill soft skill intersecao escassez" para extrair o exercicio original de construcao do diferencial.

**Processo operacional — 5 passos:**

**Passo 1 — Resgatar hard skills (do Bloco 1)**
- Pegar a lista de `competencias[]` do Bloco 1
- Separar em: Hard Skills (tecnicas: Elementor, Figma, CSS, otimizacao, GTM, trafego) e Soft Skills (postura: comunicacao, proatividade, presenca, honestidade)

**Passo 2 — Resgatar a dor do ICP (do Bloco 3)**
- Pegar `dor_primaria` e `frustracoes[]` do Bloco 3
- Identificar a dor que aparece com mais frequencia nos seus clientes reais

**Passo 3 — Cruzar e encontrar a intersecao rara (FM4)**
- Pergunta-chave: "Qual combinacao de hard skill + soft skill eu tenho que e DIFICIL de encontrar no mercado?"
- Framework FM4 (Hard+Soft=Escassez): Poucos tem tecnica E postura. Quem tem ambos e raro e caro.
- Exemplos de intersecao rara: design de alta qualidade + monitoramento ao vivo de lancamento / otimizacao de performance + comunicacao direta com equipe de trafego / construcao de pagina + consultoria de funil

**Passo 4 — Listar comportamentos concretos de presenca**
- O diferencial nao pode ficar em conceito ("sou comprometido"). Deve virar comportamentos:
  - Conferir todos os links 24h antes do lancamento
  - Enviar relatorio pos-projeto sem ser pedido
  - Participar do debriefing do lancamento
  - Migrar pagina quando ha problema no servidor, mesmo fora do escopo
  - Alertar o cliente sobre erro de trafego que voce notou
- Pergunta: "Qual ACAO concreta eu faco que 95% dos designers NAO fazem?"

**Passo 5 — Preencher a formula**
- [X] = A intersecao rara do Passo 3 (seu metodo / sua combinacao unica)
- [Y] = A dor especifica do Passo 2 (o que o cliente mais sofre)
- [Z] = O resultado mensuravel que voce gera (com numero quando possivel)

**Exemplo preenchido (derivado da KB):**
- "Atraves de [infraestrutura invisivel — server-side, GTM, pixel, otimizacao], resolvo [a dor de lancamentos que quebram por falha tecnica] e entrego [+12% de connect rate que equivale a R$600k a mais no faturamento do cliente]."

**Anti-padrao do processo:** `[VALIDAR]`
- **ERRO:** Preencher com genericos: "Atraves de [design profissional], resolvo [necessidade de site] e entrego [uma LP bonita]"
- **CORRECAO:** Se qualquer designer poderia dizer a mesma coisa, nao e diferencial. Volte ao Passo 3 e busque a intersecao rara.

### 4.4 Heuristicas

- **H4.1** Formula do diferencial: "Atraves de [metodo], resolvo [dor especifica] e entrego [resultado mensuravel]."
- **H4.2** "A forma que voce faz uma coisa e a forma que faz todas" — se relaxa o processo para clientes menores, vai falhar com os ideais.
- **H4.3** Melhor cliente = paga + indica + da autoridade. Conquista-se impressionando — entregando mais do que espera.
- **H4.4** Nao se prender a limitacao do material — usar todos os recursos disponiveis para fazer o melhor possivel com o que tem.
- **H4.5** Cobre pelo RESULTADO, nao pelo servico.

> "Eu to cobrando pelo resultado que eu posso gerar."

### 4.5 Cases e Exemplos

- **Mateus Werner:** 4M seguidores, +20M faturamento, cliente recorrente desde o primeiro lancamento. +40 paginas entregues. Relacionamento construido por entrega consistente acima do esperado.
- **Monitoramento ao vivo:** Lorenzi monitora CPLs ao vivo, participa de debriefings, migra paginas quando ha problemas — tudo sem cobrar a mais. Isso gera confianca e recorrencia.
- **Case Apple:** Mandou celular com dobro da memoria apos defeito -> fidelidade irracional. Over delivery na resolucao de problema.
- **Reposicionamento do Lorenzi:** Calculo matematico de R$186k de diferenca com otimizacao de connect rate — demonstracao concreta de que o diferencial e mensuravel.

### 4.6 Anti-padroes

- **ERRO:** Agir como "prestador de servico" — entrega e acabou, sem envolvimento com resultado.
  **CORRECAO:** Parceiro de trincheira. Acompanhar o resultado, nao so o entregavel.

> "Esse e o cara que sempre vai ganhar pouco."

- **ERRO:** Corpo mole no suporte: nao conferir botoes, nao colocar favicon, nao configurar titulo/descricao.
  **CORRECAO:** Essas sao obrigacoes minimas — "corte de grama basico."

- **ERRO:** Nao estar presente: ler briefing superficialmente, nao buscar entender a intencao real.
  **CORRECAO:** Presenca ativa = diferenciar-se de 95% do mercado.

- **ERRO:** Iniciante achar que precisa de diferencial claro desde o dia 1.
  **CORRECAO:** No inicio, o diferencial e construido no processo. Ele emerge da pratica.

### 4.7 Perguntas-guia

1. Se um cliente seu ligasse para um amigo e dissesse "contrata esse cara porque...", como completaria a frase?
2. O que voce faz que outros web designers/builders NAO fazem?
3. Depois de entregar o projeto, voce acompanha o resultado? Como?
4. Liste suas hard skills (tecnicas) e soft skills (postura/comunicacao). Onde e mais forte?
5. Qual foi a ultima vez que voce entregou algo alem do escopo — sem cobrar — e qual foi a reacao do cliente?
6. Se eu tirasse voce do seu melhor cliente hoje, o que ele perderia alem da pagina?
7. Qual e o seu "metodo" — como voce trabalha diferente?

### 4.8 Criterios de Validacao

- [ ] `formula_diferencial` articulada no formato [metodo] -> [dor] -> [resultado]
- [ ] `hard_skills[]` e `soft_skills[]` com pelo menos 3 itens cada
- [ ] `postura` descrita vai alem de "sou comprometido" — tem comportamentos concretos
- [ ] `mecanismo_unico` e algo que o concorrente nao pode copiar facilmente
- [ ] Builder consegue explicar seu diferencial em 30 segundos sem mencionar "design bonito"

### 4.9 Output esperado (campos do JSON)

`formula_diferencial`, `postura`, `hard_skills[]`, `soft_skills[]`, `mecanismo_unico`

---

## Bloco 5 — Oferta (O Que Vendo)

Frameworks aplicaveis: FM1 (80/20 do Funil), FM5 (Metafora do Balde), FM9 (Precificacao Condicional), FM11 (Jardineiro vs Cortador de Grama), FM12 (Converter e Obrigacao)

### 5.1 Objetivo

Transformar competencias e diferenciais em pacotes de solucao nomeados, precificados e posicionados numa esteira de valor.

### 5.2 Fundamentos

A solucao NAO e o entregavel.

> "Voce vai oferecer jardinagem ou um ambiente acolhedor?"

Vender a solucao completa e superior a vender servico isolado. Cliente compra **resultado**, nao entregavel tecnico.

Empacotar reduz negociacoes, boardings e gestoes de tarefa. E mais eficiente e mais lucrativo.

> "E mais facil chegar no 5000 vendendo um pacote ou vendendo 5 identidade visual?"

A solucao deve ser construida a partir dos **desejos e dores do cliente**, nao do que o designer gosta de entregar.

> "Converter e obrigacao. Te faco ser lembrado."

A Big Idea deve ser curta, memoravel e tocar no emocional.

Entregaveis devem virar **"produtos nomeados"** (pacotes) — criam ancoragem, posicao de autoridade e facilitam upsell.

**Ancoragem:** Apresente o pacote completo primeiro (valor maior), mesmo que feche so parte. A percepcao fica ancorada no todo.

**Popstar = 80/20:** Alta demanda, bom lucro, menos tempo, mais resultado. Para Junior: pacote de lancamento.

Over delivery e entregar mais **DENTRO** do produto, nao algo avulso.

> "A qualidade do corte, nao uma flor extra."

Aprenda com cada cliente para melhorar o produto padrao: se um pediu LGPD, coloque em todos.

Preco sobe quando o balde vaza — demanda excede capacidade.

> "E neste momento que voce sobe o preco."

### 5.3 Processo de Construcao

O Bloco 5 tem 7 sub-processos operacionais que detalham cada aspecto da construcao da oferta.

#### 5.3.1 Popstar — Identificar o servico de maior retorno/tempo `[VALIDAR]`

> "Eu recomendo produtizar. Inclusive tem uma aula incrivel sobre produtizacao de oferta."
> — *Live "O plano e as ferramentas certas pra fazer R$10.000 todo MES em 2027" (2:04:37)*

**Processo operacional — Identificar o Popstar:**

1. **Listar TODOS os servicos** que ja prestou ou pode prestar (landing page, identidade visual, criativos, membros, checkout, slides, carrossel, consultoria, otimizacao, manutencao)
2. **Para cada servico, anotar 3 numeros:**
   - Tempo medio de execucao (em horas)
   - Preco medio cobrado (em R$)
   - Retorno por hora (preco / horas)
3. **Marcar a demanda:** Qual desses servicos os clientes pedem com mais frequencia? Qual gera mais indicacoes?
4. **Cruzar retorno/hora com demanda:** O servico que tem ALTO retorno/hora E ALTA demanda e o Popstar
5. **Testar a escala:** Esse servico pode ser replicado para outros clientes sem reinventar? Se sim, e produtizavel
6. **Validar:** O Popstar e o pacote que voce oferece PRIMEIRO em toda negociacao

**Exemplo concreto (extraido da KB):**
- LP 2 dobras com Easy Builder: 3 horas, R$2.000 = **R$630/hora** — candidato a Popstar
- Carrossel para Instagram: 1 hora, R$500 = **R$500/hora** — alto retorno mas baixo ticket
- Pacote de lancamento completo: 40 horas, R$25.000 = **R$625/hora** — alto ticket, alto retorno, Popstar do Lorenzi na epoca de agencia

**Anti-padrao do processo:**
- **ERRO:** Manter servicos de baixo retorno/hora por costume ("sempre fiz identidade visual avulsa")
- **CORRECAO:** Aplique o 80/20 — pare de oferecer ativamente os servicos que estao abaixo da media de retorno/hora. Empacote-os dentro do Popstar como componentes, nao como produto separado.

`[GEMINI]` Buscar no GEMINI_STORE_CURSO_MB: "aula de produtizacao de oferta" para extrair o exercicio original do Lorenzi sobre a matriz retorno x tempo.

#### 5.3.2 Big Idea — Construir a frase emocional `[VALIDAR]`

> "O posicionamento ele nao serve somente para captar clientes, ele serve para filtrar os clientes e atrair os clientes. Ele qualifica ao mesmo tempo que ele atrai. E e meio contraintuitivo, mas quanto mais ele filtra, mais ele atrai."
> — *Live "O plano e as ferramentas certas pra fazer R$10.000 todo MES em 2027" (1:23:13)*

**Processo operacional — Construir a Big Idea:**

1. **Resgatar do Bloco 3:** Qual e a `dor_primaria` do seu ICP? (ex: "perdi dinheiro contratando freelancer que entregou pagina com botao sem link no dia do lancamento")
2. **Resgatar do Bloco 4:** Qual e o `mecanismo_unico` que diferencia voce? (ex: "monitoro o lancamento ao vivo e garanto que nada quebra")
3. **Traduzir a transformacao em UMA frase:** O que muda na vida do cliente DEPOIS de trabalhar com voce? Nao o que voce FAZ — o que ele SENTE/GANHA.
4. **Testar 3 criterios da Big Idea:**
   - **Curta:** Cabe em 1 linha de bio? Se nao, encurte.
   - **Memoravel:** Se o cliente ouvir uma vez, lembra amanha? Se nao, simplifique.
   - **Emocional:** Toca na dor OU no desejo profundo do ICP? Se nao, reescreva.
5. **Brainstorm iterativo:** Escreva pelo menos 10 versoes. Teste com alguem do ICP. A Big Idea certa gera reacao imediata ("e exatamente isso que eu preciso").

**Exemplos de Big Ideas (extraidas da KB e lives):**
- "Converter e obrigacao. Te faco ser lembrado." — toca no medo de ser mais um
- "Seu ultimo web designer." — promessa de fidelidade e competencia
- "Nao faco site. Resolvo o problema que o site deveria resolver." — reposiciona a categoria

**Estrutura-template:**
```
[Resultado emocional] + [Diferencial implicito] + [Filtro]
```
Exemplo: "Paginas que vendem sozinhas — pra quem ja cansou de pagar por promessa."

**Anti-padrao do processo:**
- **ERRO:** Big Idea generica: "alta conversao", "LP otimizada", "design profissional"
- **CORRECAO:** Se qualquer outro designer poderia usar a mesma frase, NAO e Big Idea. Deve ser impossivel de copiar porque nasce da sua dor resolvida + seu mecanismo unico.

`[GEMINI]` Buscar no GEMINI_STORE_CURSO_MB: "Big Idea construcao frase emocional" para extrair o exercicio original com mais exemplos de brainstorm.

#### 5.3.3 Escada de Valor — Os 4 niveis com criterios `[VALIDAR]`

> "Agreguem valor, vendam a solucao e nao um trampo isolado."
> — *Easy Sales, Planejamento, Aula 03*

**Definicao operacional dos 4 niveis:**

| Nivel | Nome | Funcao | Criterios | Exemplo (KB) |
|-------|------|--------|-----------|--------------|
| 1 | **Entrada / Down-sell** | Primeira transacao. Reduz risco. Prova competencia. | Ticket baixo (10-30% do principal). Escopo reduzido mas entrega COMPLETA dentro do escopo. NUNCA baixar preco — reduzir entregaveis. | Pacote "Minimalista": so venda + captura = R$3.500 (down-sell de R$6.797) |
| 2 | **Principal** | Carro-chefe. O Popstar produtizado. Resolve a dor do ICP de ponta a ponta. | Ticket compativel com serie do builder. Pacote nomeado. Inclui o 80/20 dos entregaveis. | Pacote "Lancamento Semente" = R$4.500 (soma avulsa R$5.300) |
| 3 | **Premium / Upsell** | Expansao para quem quer mais. Regra dos 20%: 20% dos compradores pagam ate 8x mais. | Ticket 2-8x o principal. Inclui acompanhamento, consultoria, ou entrega ampliada. Sempre PRONTO antes do cliente pedir. | Pacote "Lancamento Completo" (agencia) = R$25.000 |
| 4 | **Recorrencia / Cross-sell** | Receita previsivel. Reter custa menos que adquirir. | Cobranca mensal. Baixo esforco do builder. Alto valor percebido. Vinculado a resultado continuo. | Suporte R$100/mes ou Teste AB R$250/mes. 4 clientes = R$1.000 extra em ~4h |

**Processo operacional — Montar a escada:**

1. **Comece pelo Principal:** Qual e o seu Popstar produtizado? (vem do exercicio 5.3.1)
2. **Defina o Down-sell:** Retire entregaveis do Principal ate chegar num escopo minimo que ainda resolve algo. Preco = 30-50% do Principal.
3. **Defina o Premium:** Adicione ao Principal: acompanhamento pos-entrega, consultoria de resultado, segundo projeto, otimizacao. Preco = 2-5x o Principal.
4. **Defina a Recorrencia:** O que voce pode oferecer todo mes com pouco esforco? (suporte, teste AB, manutencao, relatorio mensal, monitoramento)
5. **Ancoragem obrigatoria:** Sempre apresente do Premium para baixo. Cliente ve o pacote maior primeiro — o Principal parece bom negocio.

**Anti-padroes do processo:**
- **ERRO:** Ter so o Principal e nada mais — viver de one-shot.
  **CORRECAO:** Minimo 2 degraus (entrada + principal) no dia 1. Ideal: 3+ degraus antes de escalar captacao.
- **ERRO:** Oferecer desconto quando cliente pede.
  **CORRECAO:** "Posso ajustar o escopo. Vamos ver o que e essencial pra voce agora." -> down-sell, nao desconto.

#### 5.3.4 Nomeacao de Pacotes — Como nomear pelo contexto do CLIENTE `[VALIDAR]`

**Processo operacional — Dar nome ao pacote:**

1. **NAO nomeie pelo servico:** "Pacote LP + Identidade" descreve o que VOCE faz, nao o que o CLIENTE precisa. Isso iguala voce ao concorrente.
2. **Nomeie pelo CONTEXTO do cliente:**
   - Qual metodologia ele usa? (lancamento, perpetuo, high ticket, posicionamento)
   - Qual momento ele esta? (comecando, escalando, reestruturando)
   - Qual resultado ele busca? (captacao, conversao, retencao, percepcao)
3. **Use a linguagem do ICP (Bloco 2):** O nome deve ser compreensivel pelo cliente sem explicacao.
4. **Teste de unicidade:** Pesquise o nome no Google/Instagram. Se muita gente usa, mude.
5. **Crie ancoragem com o nome:** Nome premium deve SOAR premium. Nome de entrada deve ser acessivel.

**Exemplos de nomes BEM construidos (da KB):**

| Contexto do cliente | Nome do pacote | Por que funciona |
|---------------------|---------------|------------------|
| Lancamento de infoproduto, primeiro | "Lancamento Semente" | Fala o metodo do cliente (semente), nao "LP + membros + checkout" |
| Posicionamento digital, comecando | "Posicionamento Digital" | Fala o resultado (posicionar), nao "bio + posts + links" |
| High ticket, sessao estrategica | "High Ticket" | Fala o modelo de venda do cliente, nao "formulario + captura + anuncio" |
| Oferta com down-sell | "Premium" / "Minimalista" | Hierarquia clara sem desvalorizar o menor |

**Exemplos de nomes que NAO funcionam:**
- "Pacote Basico / Intermediario / Avancado" — generico, sem vinculo com o cliente
- "Pacote LP Responsiva" — descreve entregavel, nao transformacao
- "Pacote Completo" — vago, impossivel de ancorar

**Anti-padrao do processo:**
- **ERRO:** Dar nomes internos/tecnicos para os pacotes ("Pack Web Design 3.0")
- **CORRECAO:** O nome do pacote e parte do posicionamento. Ele comunica pra QUEM e e QUAL resultado entrega.

#### 5.3.5 Proposta Comercial — Como apresentar pacotes ao cliente `[VALIDAR]`

> "Tem proposta comercial, proposta que eu usava aqui. Voce pega e edita isso daqui. Voce edita e manda pro teu cliente do teu jeito. Tem varios tipos diferentes de propostas que voce simplesmente replica e usa."
> — *Live "Re-abertura Teste Gratis" (4:44:10)*

**Processo operacional — Estrutura da proposta:**

1. **Abertura com contexto:** Resumo do problema do cliente (mostra que voce ouviu). 2-3 frases. Linguagem DELE, nao sua.
2. **Diagnostico:** O que voce identificou como raiz do problema. Demonstra competencia sem ser arrogante.
3. **Solucao proposta:** Nome do pacote + entregaveis listados com beneficio de cada um. Cada item responde "por que isso importa pra voce?"
4. **Mockup / referencia visual:** Se possivel, uma previa do resultado. Aumenta valor percebido drasticamente.
5. **Prova social:** 1-2 cases relevantes para o contexto do cliente. Com numeros.
6. **Investimento (ancoragem):** Apresentar valor total dos avulsos PRIMEIRO -> depois preco do pacote. Desconto implicito.
7. **CTA claro:** Proximo passo concreto ("me responde com OK que eu monto o briefing" ou "agenda uma call de 15min").

**Anti-padroes do processo:**
- **ERRO:** Mandar preco solto por WhatsApp ("a LP fica 1.750")
  **CORRECAO:** Sempre contextualizar. Preco sem proposta = commodity. Proposta com copy = posicionamento.

> "Mandando 1.750, voce perdeu a chance de vender 5.300."

- **ERRO:** Proposta em PDF generico sem personalizacao
  **CORRECAO:** Cada proposta deve ter o nome do cliente, a dor DELE e pelo menos 1 mockup/referencia especifica.

`[GEMINI]` Buscar no GEMINI_STORE_CURSO_MB e GEMINI_STORE_SOPS: "proposta comercial estrutura template" para extrair o template editavel que o Lorenzi disponibiliza no Arsenal.

#### 5.3.6 Valor Percebido vs Custo Real `[VALIDAR]`

> "Nao e sobre quanto teu trampo cobra, e sobre quanto teu trampo vale."

> "Tudo para aumentar o meu valor percebido. Naturalmente eu cobrava muito mais que a maioria."
> — *Live "O plano e as ferramentas certas pra fazer R$10.000 todo MES em 2027" (2:19:20)*

**Definicao operacional:**

- **Custo real** = tempo + ferramentas + esforco que o builder investe na entrega
- **Valor percebido** = quanto o CLIENTE acha que aquilo vale, baseado em: (1) dor que resolve, (2) confianca no profissional, (3) qualidade visivel, (4) escassez do servico, (5) posicionamento do builder

**A equacao fundamental:**
```
Valor percebido > Preco cobrado > Custo real
```
Se `valor percebido < preco` -> cliente acha caro, nao fecha.
Se `preco < custo real` -> builder perde dinheiro.
Se `valor percebido >> preco` -> cliente sente que fez um bom negocio. Indica. Volta.

**Como aumentar valor percebido sem aumentar custo:**

1. **Posicionamento (Bloco 6):** Bio, autoridade, linguagem — mudam a percepcao ANTES do cliente falar com voce
2. **Over delivery interno:** Melhorar o que ja entrega (qualidade do design, favicon, redirect, meta tags, LGPD, loading) — sem adicionar servico novo. "A qualidade do corte, nao uma flor extra."
3. **Proposta com copy (5.3.5):** A forma de apresentar muda a percepcao de valor
4. **Prova social com numeros:** Cases com metricas (R$600k de diferenca, 90% connect rate) tornam o valor concreto
5. **Escassez real:** Demanda > capacidade -> preco sobe naturalmente. "E neste momento que voce sobe o preco."

**Exemplo concreto (KB + lives):**
- Easy Optimize: 12% de aumento no connect rate = R$600.000 a mais num lancamento. Custo real para o Lorenzi: algumas horas de consultoria. Valor percebido: incalculavel. Ticket cobrado: R$10.000+ por consultoria.
- Carrossel na epoca de agencia: R$500 por peca. Custo real: ~1h de trabalho. Valor percebido alto porque entregava qualidade que o cliente nao encontrava em outros designers.

**Anti-padroes do processo:**
- **ERRO:** Precificar pelo custo ("gastei 3h, cobro R$150/hora = R$450")
  **CORRECAO:** Precifique pelo VALOR que gera. "Quanto o cliente ganha/economiza com isso?" E o ponto de partida.
- **ERRO:** Achar que aumentar valor = aumentar entregaveis
  **CORRECAO:** Aumentar valor = melhorar a percepcao. Posicionamento, prova social, qualidade interna e proposta bem feita fazem mais que adicionar servicos novos.

#### 5.3.7 Modelo Condicional — Precificacao por resultado `[VALIDAR]`

**Definicao operacional:**

O modelo condicional divide o preco em duas camadas:
- **Base fixa:** Cobre o custo real + margem minima. O builder recebe independente do resultado.
- **Bonus por resultado:** Atrelado a uma metrica mensuravel e acordada previamente. So cobra se o resultado acontecer.

**Quando aplicar:**

| Situacao | Aplicar? | Por que |
|----------|----------|---------|
| Cliente com alto potencial mas receoso com ticket | SIM | Reduz objecao: "se nao funcionar, paga menos" |
| Metrica de resultado e claramente mensuravel (CPL, connect rate, conversao, vendas) | SIM | Alinha incentivos: builder e cliente querem o mesmo |
| Builder tem controle direto sobre o resultado | SIM | Faz sentido apostar porque voce influencia |
| Resultado depende de fatores fora do controle (mercado, trafego do cliente) | COM CUIDADO | Defina a metrica sobre algo que VOCE controla (ex: taxa de conversao da pagina, nao faturamento total) |
| Cliente desorganizado, sem dados, sem trafego | NAO | Sem baseline, sem como medir. Primeiro organize, depois condicione. |

**Como estruturar:**

1. **Definir a metrica-base:** O que sera medido? (ex: connect rate da pagina de captura)
2. **Definir o baseline:** Qual e o numero ATUAL? (ex: connect rate atual = 25%)
3. **Definir o alvo:** Qual melhoria e realista? (ex: connect rate > 35%)
4. **Definir o preco base:** Valor que cobre seu trabalho independente do resultado (ex: R$3.000)
5. **Definir o bonus:** Valor adicional se atingir o alvo (ex: +R$5.000 se connect rate > 35%)
6. **Colocar em contrato:** Metrica, baseline, alvo, prazo de medicao, forma de comprovacao

**Exemplo numerico (derivado da KB):**
- Baseline: connect rate 25%
- Preco base: R$3.000 (cobre custo + margem)
- Se connect rate > 35%: +R$5.000 (ticket total R$8.000)
- Se connect rate > 40%: +R$8.000 (ticket total R$11.000)
- Resultado real do Lorenzi em case similar: 12% de aumento = R$600.000 a mais pro cliente. Ticket de R$10.000+ justificado.

**Anti-padroes do processo:**
- **ERRO:** Condicionar 100% do pagamento ao resultado (trabalhar "de graca" primeiro)
  **CORRECAO:** Sempre ter base fixa. Bonus e adicional, nao o pagamento inteiro.
- **ERRO:** Usar metrica vaga ("se o cliente gostar")
  **CORRECAO:** Metrica numerica, mensuravel, com baseline documentado antes de comecar.

`[GEMINI]` Buscar no GEMINI_STORE_CURSO_MB: "precificacao condicional por resultado como estruturar contrato" para extrair exemplos adicionais das aulas.

### 5.4 Heuristicas

- **H5.1** Retorno / Tempo: o servico com maior resultado por hora investida e o carro-chefe.
- **H5.2** Produtizacao em 4 passos: (1) listar TODOS os servicos -> (2) precificar cada avulso -> (3) marcar os de melhor retorno/tempo -> (4) empacotar como solucao nomeada.
- **H5.3** Agrupe por **metodologia do cliente** (lancamento semente, MVP, posicionamento), nao por tipo de pagina.
- **H5.4** Desconto no pacote vs soma dos avulsos cria percepcao de economia e parceria.
- **H5.5** Esteira obrigatoria: apos projeto entregue, sugira o proximo passo (down-sell, upsell, mentoria, teste AB, manutencao).
- **H5.6** Down-sell = reduzir entregaveis, NUNCA baixar preco. "Vamos reduzir um entregavel, focar no essencial."
- **H5.7** Regra dos 20%: 20% dos compradores estao dispostos a pagar ate 8x mais. Sempre tenha upsell pronto.
- **H5.8** Cross-sell recorrente: suporte (R$100/mes) ou teste AB (R$250/mes). 4 clientes = R$1.000 extra em ~4h.
- **H5.9** Mais eficiente criar multiplos entregaveis para o MESMO cliente (paleta, KV, PSD sao reaproveitados).
- **H5.10** Crie pacotes por contexto: lancamento, perpetuo, high ticket, posicionamento, rede social.
- **H5.11** Precificacao condicional por resultado: "Se nao melhorar X, custa Y. Se melhorar, custa Z."

### 5.5 Cases e Exemplos

- **Pacote "Lancamento Semente":** Identidade (R$1.000) + Criativos (R$50/un) + Membros (R$500) + Checkout (R$400) + Slides CPL (R$600) + Captura (R$1.000) + Venda+Obrigado (R$1.750) = R$5.300 -> vendido por R$4.500.
- **Pacote lancamento completo (agencia):** R$25.000.
- **LP 2 dobras com Easy Builder:** 3 horas, R$2.000 = R$630/hora.
- **Down-sell real:** Pacote completo R$6.797 -> down-sell para R$3.500 (so venda + captura). Sem baixar preco por item.
- **Premium vs Minimalista:** Estrategia de down-sell no inicio — oferece Premium, fecha Minimalista se necessario.
- **Pacote "Posicionamento Digital":** Link bio + 6 postagens + pagina links + identidade + pagina de vendas.
- **Pacote "High Ticket":** Postagens + anuncios + membros + captacao + formulario sessao estrategica.

### 5.6 Anti-padroes

- **ERRO:** Vender avulsos isolados em vez de solucoes empacotadas.
  **CORRECAO:** Empacotar como solucao que resolve as dores mapeadas no Bloco 3.

- **ERRO:** Responder preco avulso imediato quando cliente pergunta "quanto custa uma LP?".
  **CORRECAO:** Apresentar pacote completo primeiro. Ancoragem no todo.

> "Mandando 1.750, voce perdeu a chance de vender 5.300."

- **ERRO:** Ficar preso ao entregavel na comunicacao ("faco LP responsiva otimizada em 48h").
  **CORRECAO:** Comunicar a transformacao e o resultado que o pacote gera.

- **ERRO:** Nao ter recorrencia na esteira — viver de projetos one-shot.
  **CORRECAO:** Incluir cross-sell recorrente (suporte, teste AB, manutencao).

- **ERRO:** Achar que transformacao exige mentoria cara ou programa elaborado.
  **CORRECAO:** Transformacao acontece na entrega + atendimento + postura diaria.

- **ERRO:** Manter servicos de baixo retorno/hora por costume ("sempre fiz identidade visual avulsa"). `[VALIDAR]`
  **CORRECAO:** Aplique o 80/20 — pare de oferecer ativamente os servicos abaixo da media de retorno/hora. Empacote-os dentro do Popstar como componentes.

- **ERRO:** Dar nomes internos/tecnicos para os pacotes ("Pack Web Design 3.0"). `[VALIDAR]`
  **CORRECAO:** O nome do pacote e parte do posicionamento. Comunica pra QUEM e e QUAL resultado entrega.

- **ERRO:** Precificar pelo custo ("gastei 3h, cobro R$150/hora = R$450"). `[VALIDAR]`
  **CORRECAO:** Precifique pelo VALOR que gera. "Quanto o cliente ganha/economiza com isso?" e o ponto de partida.

### 5.7 Perguntas-guia

1. Liste todos os servicos que voce oferece hoje — todos, mesmo os que cobra pouco.
2. Qual desses servicos tem o melhor retorno por hora investida?
3. Seus clientes costumam precisar de mais de um servico ao mesmo tempo? Quais combinacoes sao frequentes?
4. Voce ja tem pacotes nomeados ou vende tudo avulso?
5. Quando um cliente pede desconto, como voce reage hoje?
6. Apos entregar um projeto, o que acontece? O cliente volta? Voce sugere proximo passo?
7. Qual e o servico que voce entrega que seu cliente NAO sabe que precisa — mas quando recebe, fica impressionado?
8. Se pudesse vender apenas 1 pacote para todos os clientes, o que teria dentro?

### 5.8 Criterios de Validacao

- [ ] Pelo menos 1 pacote nomeado com escopo claro e preco definido
- [ ] `escada_valor` com pelo menos 2 degraus (entrada + principal OU principal + premium)
- [ ] Recorrencia presente na esteira (suporte, teste AB, manutencao ou similar)
- [ ] Preco do pacote e inferior a soma dos avulsos — ancoragem funcional
- [ ] Builder consegue explicar o que esta FORA do escopo — exclusoes sao tao claras quanto inclusoes

### 5.9 Output esperado (campos do JSON)

`nome_oferta`, `escopo[]`, `entregaveis[]`, `preco`, `modelo_cobranca`, `escada_valor{entrada, principal, premium, recorrencia}`

---

## Bloco 6 — Posicionamento (Como Comunico)

Frameworks aplicaveis: FM7 (Efeito Ima), FM12 (Converter e Obrigacao)

### 6.1 Objetivo

Traduzir o diferencial e a oferta em comunicacao magnetica que atrai o ICP e repele o restante.

### 6.2 Fundamentos

Bio em 3 camadas: (1) abracar a dor -> (2) tocar vaidade -> (3) gerar escassez.

> "Converter e obrigacao. Te faco ser lembrado."
> "Seu ultimo web designer."

Posicionamento funciona como **filtro**: atrai o bom e repele o ruim.

> "Se atrai todo mundo, teu posicionamento e ruim."

Autoridade se comunica pela **capacidade de entrega**, nao por ostentacao.

> "Eu nao preciso ficar arrotando salsicha."

Quando todos copiam a mesma bio, o cliente iguala todos. Diferenciacao e sobrevivencia.

> "Se le algo que ta na bio de outro designer, iria me equiparar."

Cada palavra precisa justificar sua existencia.

> "O negocio aqui e falar mais com menos."

Autoridade por **proxy de investimento**: "quanto de investimento ja passou pelas minhas paginas" e mais crivel e diferenciado do que "fiz X projetos."

O cliente quer **tranquilidade e seguranca**, nao so metrica.

> "O projeto vai ser entregue no prazo, com compromisso."

Para publico feminino, comunicacao mais emocional/acolhedora. Sensacoes e autoestima superam metricas.

### 6.3 Processo de Construcao

Como construir a bio camada por camada + CTA/filtro. `[VALIDAR]`

> "A sua foto precisa comunicar que voce e confiavel por causa da percepcao de valor. O seu perfil inteiro precisa demonstrar isso ao mesmo tempo que mostra pro publico especifico a solucao que voce entrega, o resultado que voce gera."
> — *Live "O plano e as ferramentas certas pra fazer R$10.000 todo MES em 2027" (1:22:11)*

`[GEMINI]` Buscar no GEMINI_STORE_CURSO_MB: "bio posicionamento brainstorm iterativo camadas" para extrair o exercicio original com exemplos antes/depois.

**Processo operacional — Construir a bio em 5 passos:**

**Passo 1 — Camada 1: Abracar a dor (Transformacao)**
- Resgatar `dor_primaria` do Bloco 3
- Escrever uma linha que ABRACA a dor do ICP — mostra que voce entende o problema antes de oferecer solucao
- Deve usar a linguagem do CLIENTE (H6.1), nao jargao de designer
- Exemplo: "Cansei de ver lancamento quebrar por pagina mal feita"

**Passo 2 — Camada 2: Tocar vaidade (Autoridade)**
- Resgatar `mecanismo_unico` do Bloco 4 e `elemento_autoridade`
- Escolher UMA metrica de autoridade que e:
  - Verificavel (pode provar)
  - Dificil de copiar (nao e generico)
  - Especifica (com numero)
- Evitar: "especialista em X" (todo mundo diz). Preferir: proxy de investimento ("R$30M investidos nas paginas que criei") ou resultado mensuravel ("1M de leads captados com 90% connect rate")
- Exemplo: "+R$30M em investimento passaram pelas minhas paginas"

**Passo 3 — Camada 3: Gerar escassez (CTA/Filtro)**
- O CTA deve FILTRAR quem entra em contato (H6.3)
- Mensagem pre-formatada no WhatsApp que ja usa linguagem tecnica do ICP
- Se o cara nao entende o CTA, ele nao e seu publico — e isso e BOM
- Exemplo: "Se voce investe em trafego e quer connect rate acima de 90%, me chama" — quem nao sabe o que e connect rate, nao e ICP

**Passo 4 — Brainstorm iterativo (Caminho Neural passo 8)**
- Escrever no minimo 10 versoes da bio completa
- Para cada versao, testar: "Se eu fosse meu ICP e lesse isso, eu mandaria mensagem?"
- Pedir feedback de 2-3 pessoas que sao do perfil do ICP
- NAO aceitar a primeira versao

**Passo 5 — Validar com os criterios do Bloco 6**
- [ ] Bio tem as 3 camadas? (dor + autoridade + escassez/CTA)
- [ ] Promessa e diferente de "alta conversao" ou "LP otimizada"?
- [ ] Autoridade e verificavel e dificil de copiar?
- [ ] CTA filtra — ou qualquer pessoa mandaria mensagem?
- [ ] Linguagem usa termos que o CLIENTE entende?

**Exemplos lado a lado:**

| Bio RUIM | Bio BOA |
|----------|---------|
| Web designer \| Sites profissionais \| Entrega rapida \| DM aberta | Paginas que vendem sozinhas. +R$30M investidos nas minhas entregas. Se voce investe em trafego e quer parar de perder lead, me chama. |
| Designer especialista em LP de alta conversao. Portfolio no link. | Converter e obrigacao. Te faco ser lembrado. Seu ultimo web designer. |

**Anti-padrao do processo:**
- **ERRO:** Copiar bio de outro designer
  **CORRECAO:** Se le algo que esta na bio de outro designer, seria equiparado. Cada palavra justifica existencia.

> "Se le algo que ta na bio de outro designer, iria me equiparar."

- **ERRO:** Bio que atrai todo tipo de cliente
  **CORRECAO:** "Se atrai todo mundo, teu posicionamento e ruim." Quanto mais filtra, mais atrai o certo.

### 6.4 Heuristicas

- **H6.1** Fale a linguagem do **nivel de consciencia** do cliente. Se ele entende connect rate, use. Se nao, traduza para beneficios tangiveis.
- **H6.2** Proposta comercial com copy vende melhor que proposta padrao — mockups, diferenciais e beneficios na proposta ja e posicionamento.
- **H6.3** CTA com filtro implicito: mensagem pre-formatada no WhatsApp que ja filtra. Quem nao entende a linguagem, nao entra em contato.
- **H6.4** Framework da bio: **Transformacao -> Autoridade -> CTA** — mas subvertido pelo resultado real, linguagem do cliente e filtro implicito.

### 6.5 Cases e Exemplos

- **Lorenzi e lancamentos:** Tem +R$1M em lancamentos mas NAO usa "especialista em lancamentos" na bio — seria igualado a todos que usam o mesmo rotulo.
- **Sem print de pix:** Nunca postou print de pix no Instagram mesmo com resultados expressivos. Autoridade pela competencia demonstrada.
- **"Infradesigner":** Nomenclatura propria que comunica a camada tecnica invisivel — server-side, GTM, pixel, otimizacao. Diferente de tudo que existe.
- **Metricas de autoridade:** "30 milhoes investidos nas paginas que criei" e "1 milhao de leads captados com 90% connect rate" — especifico, verificavel, diferenciado.

### 6.6 Anti-padroes

- **ERRO:** Copiar bio de outros designers (Ctrl+C / Ctrl+V).
  **CORRECAO:** Diferenciacao baseada na sua capacidade de entrega real — o que SO VOCE faz.

- **ERRO:** Usar prints de pix e conquistas como principal autoridade.
  **CORRECAO:** Autoridade pela competencia demonstrada, nao por ostentacao.

- **ERRO:** Posicionamento generico que atrai todo tipo de cliente.
  **CORRECAO:** Pergunte: "seu posicionamento atual atrai o tipo de cliente que voce QUER?"

- **ERRO:** Promessa que atrai publico errado ("conquiste o topo do mercado" pode atrair vaidosos e nao o ICP).
  **CORRECAO:** Alinhar promessa com ICP real definido no Bloco 2.

- **ERRO:** Usar promessa generica "alta conversao" ou "LP otimizada".
  **CORRECAO:** Big Idea que toque na dor especifica do seu ICP. Curta, memoravel, emocional.

### 6.7 Perguntas-guia

1. Se alguem le sua bio hoje, em 5 segundos entende o que voce faz de diferente?
2. Qual metrica de autoridade voce tem que seria dificil para um concorrente copiar?
3. Sua bio atual atrairia seu cliente ideal ou qualquer pessoa que precise de site?
4. Como seu melhor cliente te descreveria para outro empresario?
5. Se tivesse que resumir sua promessa em UMA frase, qual seria?
6. Seu CTA filtra — ou qualquer pessoa se sentiria confortavel em mandar mensagem?
7. Voce tem um "nome" para o que faz — algo que seja so seu? (ex: infradesigner, easy optimize)

### 6.8 Criterios de Validacao

- [ ] `bio` com as 3 camadas presentes: dor/transformacao + autoridade + escassez/CTA
- [ ] `promessa` e diferente de "alta conversao" e "LP otimizada" — toca na dor do ICP
- [ ] `elemento_autoridade` e verificavel e dificil de copiar (nao generico)
- [ ] `filtro_cta` presente — a mensagem/CTA filtra quem nao e ICP
- [ ] `linguagem_icp` usa termos que o cliente entende — nao jargao de designer

### 6.9 Output esperado (campos do JSON)

`bio`, `promessa`, `elemento_autoridade`, `filtro_cta`, `linguagem_icp`

---

## Bloco 7 — Meta Operacional (Quanto e Quando)

Frameworks aplicaveis: FM1 (80/20 do Funil), FM2 (Cenario Pessimista / Bom / Excelente), FM5 (Metafora do Balde)

### 7.1 Objetivo

Definir meta de faturamento realista, compativel com capacidade de entrega, e o criterio para subir preco.

### 7.2 Fundamentos

Metas irrealistas geram ciclo destrutivo: frustracao -> procrastinacao -> inacao -> "o mercado nao funciona" -> designer injusticado.

> "Sejam realistas. Se estao fazendo 2 por mes, foca nos 3K primeiro."

Crescimento e **escada**, nao elevador. Cada degrau valida o proximo.

Funil automatico de captacao **SO funciona** se os fundamentos (PA, servicos, pacotes) estiverem definidos antes.

Toda vez que o balde vaza (demanda > capacidade), e o momento de subir preco.

Recorrencia > volume de clientes novos. Reter custa menos e rende mais.

### 7.3 Processo de Construcao

`[GEMINI]` Processo de construcao para definicao de meta operacional nao foi extraido das aulas na sessao anterior. Buscar no GEMINI_STORE_CURSO_MB: "meta operacional faturamento escada preco exercicio" para extrair o exercicio original.

**Sequencia minima sugerida:** `[VALIDAR]`

1. **Diagnostico de faturamento atual:** Quanto faturou nos ultimos 3 meses? Qual e o ticket medio real?
2. **Calculo de capacidade:** Quantos projetos simultaneos consegue entregar com qualidade? (horas/semana do Bloco 1 / horas por projeto)
3. **Projecao de 3 cenarios (FM2):**
   - Pessimista: metade da capacidade, ticket atual
   - Bom: capacidade cheia, ticket atual
   - Excelente: capacidade cheia, ticket 50% maior
4. **Definicao do proximo degrau:** Nao mirar o cenario excelente — mirar o bom como meta de 90 dias
5. **Criterio de subida de preco:** Definir gatilho claro (ex: "quando recusar 2 clientes por falta de tempo no mesmo mes")
6. **Verificacao de pre-requisitos:** Blocos 2, 3 e 5 estao preenchidos? Se nao, nao avance para captacao
7. **Planejamento de recorrencia:** Quanto da meta vem de projetos novos vs recorrencia? Ideal: recorrencia cobrindo pelo menos 20% da meta

### 7.4 Heuristicas

- **H7.1** Faixas por nivel: Iniciante -> 3K/mes | Intermediario -> 5-7K/mes | Avancado -> 10K+/mes.
- **H7.2** Sequencia obrigatoria: (1) Publico-alvo -> (2) Servicos precificados -> (3) Pacotes/solucoes -> (4) Posicionamento -> (5) Funil de captacao. Sem atalhos.
- **H7.3** Acompanhamento pos-entrega (monitorar lancamento, participar de debriefing) e o que gera recorrencia e indicacao.
- **H7.4** Volume de clientes planejado deve ser compativel com capacidade de entrega ANTES de estrategias de captacao.
- **H7.5** Pouca demanda? Nao se preocupe com preco — foco em vender. Muita demanda vazando? Hora de subir preco.

### 7.5 Cases e Exemplos

- **Ana/Aurora:** Ticket medio R$2.600, 5-6 sites/mes = R$15.000/mes — operacao enxuta e consistente.
- **Agencia do Junior:** De R$500 por carrossel -> R$15-20k por pacote de lancamento. Evolucao por escada.
- **Cross-sell real:** 4 clientes pagando R$250/mes de teste AB = R$1.000 extra em ~4h de trabalho mensal.

### 7.6 Anti-padroes

- **ERRO:** Definir meta muito acima do momento atual (faz 2K e mira 10K direto).
  **CORRECAO:** Escada realista — cada degrau valida o proximo. 2K -> 3K -> 5K -> 7K -> 10K.

- **ERRO:** Frustrar-se e concluir "o mercado nao funciona."
  **CORRECAO:** Frustracao quase sempre vem de expectativas irrealistas, nao de mercado ruim.

- **ERRO:** Atrair volume sem capacidade de entrega -> contratar sem controle -> perder qualidade -> manchar reputacao.
  **CORRECAO:** Calcular capacidade maxima antes de escalar captacao.

- **ERRO:** Montar funil automatico sem ter PA, servicos e pacotes definidos.
  **CORRECAO:** Bloquear avanco se Blocos 2, 3 e 5 nao estao preenchidos. Funil sem fundamento queima dinheiro.

- **ERRO:** Baixar preco quando cliente pede desconto.
  **CORRECAO:** Reduzir escopo, nao preco. Down-sell estruturado.

### 7.7 Perguntas-guia

1. Quanto voce quer faturar nos proximos 3 meses? E em 12 meses?
2. Com base no seu ticket medio atual, quantos clientes por mes precisa para atingir essa meta?
3. Voce consegue entregar essa quantidade com qualidade? Se nao, qual e seu limite real?
4. Qual e sua capacidade maxima de projetos simultaneos sem perder qualidade?
5. Ja teve mes que recusou cliente por falta de tempo? O que fez com o preco?
6. Qual o proximo degrau realista — qual faturamento mensal seria um avanco factivel em 90 dias?
7. Voce tem fonte de recorrencia hoje ou vive 100% de projetos novos?
8. Qual e o criterio que vai usar para decidir quando e hora de subir o preco?

### 7.8 Criterios de Validacao

- [ ] `faturamento_alvo` e coerente com `serie_atual` do Bloco 1 (nao pula degrau)
- [ ] `clientes_mes` x `ticket_medio` = `faturamento_alvo` — a conta fecha
- [ ] `capacidade_entrega` e compativel com `clientes_mes` — sem sobrecarga
- [ ] `criterio_subir_preco` definido com gatilho claro (ex: "quando recusar 2 clientes por falta de tempo")
- [ ] Blocos 2, 3 e 5 estao preenchidos antes de qualquer plano de captacao

### 7.9 Output esperado (campos do JSON)

`ticket_medio`, `clientes_mes`, `faturamento_alvo`, `criterio_subir_preco`, `capacidade_entrega`

---

## Caminho Neural — 11 Passos Sequenciais

Sequencia extraida do Lorenzi aplicando o metodo **para si mesmo** no video de reposicionamento. Serve como blueprint para o agente guiar o aluno:

1. **Diagnostico de contexto pessoal** — "Preciso de renda extra, mas nao tenho tempo para projetos completos. Preciso de algo rapido e de alto valor." Mapear realidade antes de qualquer decisao.

2. **Inventario de competencias** — Listar tudo que sabe fazer e identificar onde e mais forte. Cruzar com demanda de mercado.

3. **Mapeamento do funil do cliente** — Desenhar funil completo do cliente ideal e identificar onde esta o 80/20 de impacto. Onde a alavanca e maior?

4. **Demonstracao matematica do impacto** — Calcular cenarios (base vs otimizado) e mostrar o delta financeiro. Provar com numeros que a solucao se paga.

5. **Definicao da fatia de mercado** — Quem fatura 6+ digitos, equipe estruturada, investe em trafego. Filtrar por quem pode pagar E valorizar.

6. **Definicao do escopo de servico** — O que incluir e **EXCLUIR** explicitamente. Exclusao e tao importante quanto inclusao.

7. **Prova de resultado com case real** — Dashboard de cliente mostrando melhoria apos sua entrada. Evidencia concreta supera qualquer promessa.

8. **Construcao do posicionamento/bio** — Brainstorm iterativo de dezenas de versoes, testando angulos diferentes. Nao aceitar a primeira versao.

9. **Definicao de autoridade** — Escolha de metricas especificas e verificaveis (investimento que passou pelas paginas, leads captados, connect rate).

10. **Precificacao** — Comecar em X, reconhecer que pelo resultado poderia ser 3x. Planejar testar e escalar conforme demanda.

11. **CTA e filtro** — Mensagem pre-formatada que filtra pela linguagem. Quem nao entende a linguagem, nao e ICP.

---

## Frameworks Mestres

Modelos mentais transversais que permeiam todos os blocos. O agente deve referenciar o framework relevante ao guiar cada bloco.

### FM1 — 80/20 do Funil

A pagina de captura e o 80/20 do lancamento. Pequenas melhorias percentuais geram o maior impacto financeiro absoluto. Aplicar em qualquer analise de prioridade: onde esta o 80/20 do SEU cliente?

### FM2 — Cenario Pessimista / Bom / Excelente

Projecao de 3 cenarios com metricas **antes** de comecar qualquer projeto ou mudanca. Remove ansiedade e cria referencia objetiva de sucesso.

### FM3 — Senior que Toca o Setor

Nao executor de tarefas, mas gerente de area. Faz reuniao com trafego, cobra copy, cria testes AB, monitora KPIs. Postura que justifica ticket alto.

### FM4 — Hard + Soft = Escassez

A intersecao de tecnica **E** postura e rara. Por isso pagam bem. A maioria tem um ou outro — quem tem ambos se torna dificil de substituir.

### FM5 — Metafora do Balde

Balde = operacao do builder. Agua = clientes. Furos = falhas na entrega/processo. Torneira = canais de captacao. Filtro = posicionamento. Nao adianta abrir a torneira se o balde tem furo. Nao adianta tampar furos se nao tem filtro.

### FM6 — Lateralizacao de Nicho

Corte transversal por **comportamento**, nao vertical por setor. Empresarios que faturam R$100k+, investem em trafego e se frustram com freelancers existem em TODOS os nichos.

### FM7 — Efeito Ima

Posicionamento = frequencia magnetica. Atrai o compativel, repele o incompativel. Se atrai todo mundo, a frequencia esta errada.

### FM8 — Eu + Cliente vs Problema

Parceiro de trincheira, nao fornecedor. A relacao e de alianca contra um inimigo comum (o problema), nao de comprador e vendedor.

### FM9 — Precificacao Condicional

Preco base + bonus atrelado a resultado. Alinha incentivos (builder e cliente querem o mesmo), reduz objecao ("se nao funcionar, paga menos") e abre porta para ticket alto.

### FM10 — Frustracao Inversa

O diferencial do builder vem de **resolver a dor que o proprio mercado ja causa**: atrasos, erros, falta de visao estrategica, descaso no suporte. Ser o oposto do que o cliente ja sofreu.

### FM11 — Jardineiro vs Cortador de Grama

O designer que entrega LP e manda Pix = cortador de grama. Qualquer um faz, cobra barato, e substituivel. O que cuida do "ambiente acolhedor" — resultado, experiencia, prevencao — e jardineiro. Cobra mais, fideliza, e indicado.

### FM12 — Converter e Obrigacao, Dificil e Ser Lembrado

Posicionar-se como "alta conversao" e commodity — todo designer diz isso. O diferencial e ser **memoravel**: a experiencia de trabalhar com voce, a seguranca, a presenca. Isso nao se copia.

---

## Mapa FM -> Blocos (Referencia rapida para o agente)

Tabela de mapeamento completa: Framework -> Blocos -> Gatilho de ativacao -> Como aplicar.

| FM | Nome | Blocos | Gatilho — QUANDO o agente deve acionar | Como aplicar |
|----|------|--------|---------------------------------------|--------------|
| FM1 | 80/20 do Funil | 3, 5, 7 | Aluno esta listando muitas acoes/servicos sem priorizar | "Onde esta o 80/20? Qual UNICA acao gera o maior impacto?" Forcar priorizacao. |
| FM2 | Cenario Pessimista / Bom / Excelente | 7 | Aluno esta definindo meta ou avaliando risco | "Projete 3 cenarios com metricas ANTES de comecar." Remove ansiedade e cria referencia. |
| FM3 | Senior que Toca o Setor | 1, 4 | Aluno descreve seu trabalho como executor de tarefas | "Voce e gerente de area, nao executor. Faz reuniao com trafego, cobra copy, monitora KPIs." Elevar postura. |
| FM4 | Hard + Soft = Escassez | 1, 4 | Aluno pergunta por que deveria cobrar mais / nao se sente diferente | "A intersecao de tecnica E postura e RARA. Quem tem ambos e dificil de substituir." Usar no exercicio do diferencial (4.3, Passo 3). |
| FM5 | Metafora do Balde | 1, 5, 7 | Aluno quer escalar captacao sem ter resolvido problemas de entrega | "Nao adianta abrir a torneira se o balde tem furo." Primeiro tapar furos, depois captar. |
| FM6 | Lateralizacao de Nicho | 2 | Aluno esta preso a um nicho vertical ("so atendo advocacia") | "Corte transversal por COMPORTAMENTO, nao vertical por setor." Empresarios de R$100k+ existem em todos os nichos. |
| FM7 | Efeito Ima | 2, 6 | Aluno diz que atrai todo tipo de cliente ou cliente ruim | "Posicionamento = frequencia magnetica. Se atrai todo mundo, a frequencia esta errada." Revisar bio e comunicacao. |
| FM8 | Eu + Cliente vs Problema | 4 | Aluno descreve sua relacao com cliente como comprador/vendedor | "Parceiro de trincheira, nao fornecedor. A relacao e alianca contra um inimigo comum." Reposicionar postura. |
| FM9 | Precificacao Condicional | 5 | Aluno tem servico mensuravel mas nao sabe como cobrar ticket alto | "Preco base + bonus atrelado a resultado." Usar processo 5.3.7 deste documento. |
| FM10 | Frustracao Inversa | 3, 4 | Aluno nao identifica seu diferencial ou nao ve dor do mercado | "O diferencial vem de RESOLVER a dor que o proprio mercado causa." Ser o oposto do que o cliente ja sofreu. |
| FM11 | Jardineiro vs Cortador de Grama | 3, 4, 5 | Aluno descreve sua oferta como entregavel isolado (LP, identidade) | "Cortador de grama = entrega e manda pix. Jardineiro = cuida do ambiente. Quem cuida, fideliza." Empacotar como solucao. |
| FM12 | Converter e Obrigacao | 5, 6 | Aluno usa "alta conversao" como proposta de valor | "Todo designer diz isso. O diferencial e ser MEMORAVEL." Redirecionar para Big Idea e experiencia. |

### Regra para o agente

Ao iniciar qualquer bloco, verificar na tabela acima quais FMs se aplicam. Manter em memoria ativa durante a conversa. Quando o gatilho ocorrer:

1. Nomear o framework ("isso e o FM5 — Metafora do Balde")
2. Explicar brevemente (1-2 frases)
3. Aplicar ao contexto especifico do aluno
4. Registrar no output que o FM foi utilizado

---

## Apendice — Limitacoes e proximos passos

### Fontes consultadas (local)

| Arquivo | Conteudo relevante extraido |
|---------|---------------------------|
| `knowledge-base.md` | Base completa — fundamentos, heuristicas, cases, anti-padroes de todos os 7 blocos |
| `reforco-operacional.md` | Processos passo-a-passo, definicoes operacionais, mapeamento de frameworks |
| `auditoria-insumos.md` | Diagnostico detalhado de cada lacuna |
| `fundamentos.md` (Downloads) | Passo-a-passo ICP da Aula 06 Easy Sales |
| `gestao.md` (Downloads) | Metas, precificacao, processo de venda da Aula 03 Easy Sales |
| `aula-03-raw.md` (Downloads) | Aula 03 "Como Bater Suas Metas" — precificacao por meta diaria |
| Live `e28c1cad7f88e242.txt` | "O plano e as ferramentas certas pra fazer R$10.000 todo MES em 2027" — posicionamento, produtizacao, flywheel, 8020 |
| Live `a892bef3ae8a78a5.txt` | "Re-abertura Teste Gratis" — proposta comercial, arsenal do web designer |

### Gaps que requerem Gemini (API indisponivel)

| Gap | Busca recomendada | Store |
|-----|-------------------|-------|
| Bloco 1 — Processo de diagnostico de contexto pessoal | "diagnostico contexto builder faturamento competencias nivel exercicio" | GEMINI_STORE_CURSO_MB |
| Bloco 3 — Processo de mapeamento de dor e cadeia causal | "mapeamento dor problema cadeia causal 5 porques exercicio" | GEMINI_STORE_CURSO_MB |
| Bloco 7 — Processo de definicao de meta operacional | "meta operacional faturamento escada preco exercicio" | GEMINI_STORE_CURSO_MB |
| Popstar — exercicio original da aula de produtizacao | "produtizacao oferta matriz retorno tempo exercicio" | GEMINI_STORE_CURSO_MB |
| Big Idea — processo de brainstorming com mais exemplos | "Big Idea construcao frase emocional brainstorm" | GEMINI_STORE_CURSO_MB |
| Proposta comercial — template editavel do Arsenal | "proposta comercial estrutura template editavel" | GEMINI_STORE_CURSO_MB + GEMINI_STORE_SOPS |
| Modelo condicional — exemplos de contrato e casos de uso | "precificacao condicional resultado contrato estrutura" | GEMINI_STORE_CURSO_MB |
| Exercicio diferencial — aula original de hard skill + soft skill | "diferencial exercicio hard skill soft skill intersecao escassez" | GEMINI_STORE_CURSO_MB |
| Bio — exercicio de brainstorm iterativo com exemplos antes/depois | "bio posicionamento brainstorm iterativo camadas" | GEMINI_STORE_CURSO_MB |

### Acao tecnica pendente

A API Gemini Search esta usando o modelo `gemini-2.0-flash` que foi depreciado. Para restaurar o acesso aos stores de conteudo do curso:

1. Localizar a configuracao do MCP server `gemini-search`
2. Atualizar o modelo de `models/gemini-2.0-flash` para `models/gemini-3.6-flash`
3. Re-executar as 9 buscas listadas acima
4. Enriquecer as secoes marcadas com `[GEMINI]` neste documento
5. Revisar e potencialmente remover tags `[VALIDAR]` das secoes confirmadas pelas aulas
