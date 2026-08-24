# Knowledge Base — Plano 10K (Método Antiprospecção)

Base de conhecimento do agente conversacional que guia web designers/builders na construção do plano de negócio. O agente opera em ciclo: **FUNDAMENTAR → GUIAR → VALIDAR → REGISTRAR** para cada bloco.

---

## Bloco 1 — Contexto do Builder (Quem Sou Eu)

**Objetivo:** Mapear a realidade atual do builder — faturamento, competências, tempo, ferramentas e nível — para calibrar todo o restante do plano.

**Campos output:** `meta_faturamento`, `competencias[]`, `tempo_disponivel`, `ferramentas[]`, `serie_atual` (iniciante / intermediário / avançado)

### 1.1 Fundamentos

O equilíbrio ideal do builder é **produtividade + posicionamento**: cobrar preço justo e entregar rápido gera o melhor retorno por tempo investido.

> "Esse aqui é o 80/20 do conteúdo. Não subestimem isso."

Mentalidade e comportamento representam 80% do que determina resultado; técnica é apenas 20%.

A evolução de preço acontece **naturalmente** quando se entrega mais do que cobra. Não é uma decisão arbitrária — é consequência de competência demonstrada.

> "Não é sobre quanto teu trampo cobra, é sobre quanto teu trampo vale."

Ser builder significa usar ferramentas (e quando necessário criar as suas) para resolver problemas de alto valor no menor tempo possível.

### 1.2 Heurísticas

- **H1.1** Se está no início (horizontal), foque no meio-termo entre volume e qualidade. Se já está no meio-termo, foque na escala vertical — especialização + ticket mais alto.
- **H1.2** Iniciante deve cobrar barato, fechar clientes reais, adquirir experiência e montar portfólio. Preço sobe conforme competência sobe.
- **H1.3** Trabalhar de graça é válido **SE** for com intencionalidade — para clientes que geram portfólio forte, indicações ou contratos futuros.
- **H1.4** Aprenda por engenharia reversa: Ads Library + `sitemap.xml` de lançamentos reais para mapear funis completos.

### 1.3 Exemplos / Cases

- Builder iniciante que cobrava R$500 e achou "desrespeito" — não fechou nenhum cliente por 3 meses. Ao ajustar para preço compatível com seu nível, fechou 4 clientes no mês seguinte e montou portfólio real.
- Lorenzi: começou cobrando barato, entregou acima do esperado sistematicamente, e a evolução de preço veio como consequência natural da demanda crescente.

### 1.4 Anti-padrões

- **ERRO:** Iniciante se recusar a cobrar barato por achar "desrespeito" — resultado: não fecha nenhum cliente.
  **CORREÇÃO:** No início, experiência e portfólio valem mais que ticket alto. O preço sobe quando a competência justifica.

- **ERRO:** Adicionar serviços novos (ex: copywriting via ChatGPT) sem competência consolidada no serviço principal.
  **CORREÇÃO:** Foco no que domina primeiro. Só expandir quando o core estiver sólido.

- **ERRO:** Não saber quanto fatura ou quanto tempo tem disponível — operar no escuro.
  **CORREÇÃO:** Números reais antes de qualquer plano. Sem diagnóstico, qualquer meta é chute.

### 1.5 Perguntas-guia

1. Quanto você faturou nos últimos 3 meses com serviços de web design/builder?
2. Quais são suas 3 competências mais fortes hoje — as que entrega com mais velocidade e qualidade?
3. Quantas horas por semana você tem disponíveis para trabalhar em projetos de clientes?
4. Quais ferramentas você domina? (Elementor, Webflow, Framer, Easy Builder, Figma, etc.)
5. Quantos projetos já entregou no total? E nos últimos 6 meses?
6. Você se considera iniciante, intermediário ou avançado? Por quê?
7. De 0 a 10, quanto você se sente confiante para atender um cliente que fatura R$100k/mês?

### 1.6 Critérios de Validação

- [ ] `meta_faturamento` preenchido com valor numérico real (não estimativa vaga)
- [ ] Pelo menos 3 competências listadas com nível de domínio (básico/intermediário/avançado)
- [ ] `tempo_disponivel` definido em horas/semana — compatível com meta de faturamento desejada
- [ ] `serie_atual` classificada coerentemente com faturamento e portfólio declarados
- [ ] Ferramentas listadas correspondem às competências declaradas

---

## Bloco 2 — ICP / Público-Alvo (Pra Quem)

**Objetivo:** Definir com precisão o perfil de cliente ideal usando comportamento, porte e momento — não nicho vertical.

**Campos output:** `area_setor`, `porte_empresa{faturamento, equipe, investimento_marketing}`, `comportamento_digital`, `momento_empresa`, `filtros_exclusao[]`

### 2.1 Fundamentos

Público-alvo se define por **padrões de comportamento, porte e momento** — NÃO pelo segmento vertical (nicho).

> "O mercado, o nicho, não é tão importante quanto o porte do cliente."

Nicho pode ajudar a delimitar comunicação, mas não é obrigatório nem limitante. Visão lateralizada: vários nichos compartilham o mesmo padrão de comportamento e necessidade.

> "Não se apeguem ao nicho."

Quando se tenta falar com todo mundo, não se conecta com ninguém. Funciona como um ímã — a frequência certa atrai o compatível e repele o incompatível.

> "Quem é atraído é só quem tá compatível com aquilo que eu tô comunicando."

O momento da empresa, capacidade de investimento e dores determinam o público. A definição de público-alvo **NÃO é fixa** — deve ser ajustada frequentemente conforme o builder evolui.

> "Isso aqui tem que ser ajustado frequentemente."

Número de seguidores não é métrica confiável. Métricas sólidas: investimento em marketing, faturamento, tamanho da equipe.

O ICP é definido por **momento de vida e nível de consciência** — o cliente ideal já se frustrou, já contratou errado, está disposto a pagar mais por segurança.

### 2.2 Heurísticas

- **H2.1** 5 dimensões do ICP: (1) Área/setor, (2) Momento do cliente, (3) Tipo de produto/serviço que vendem, (4) Faturamento estimado, (5) Tamanho da equipe.
- **H2.2** Filtro de exclusão triplo: sem consciência de marketing **+** sem dinheiro **+** vai dar dor de cabeça → NÃO é público-alvo.
- **H2.3** Google Maps para prospecção local: buscar empresas do setor, verificar se sites têm problemas que você resolve.
- **H2.4** Usar GPT para estimar dados de mercado (faturamento médio, porte típico) quando não tem informação direta.
- **H2.5** Se aparecer cliente fora do nicho mas sua solução resolve o problema dele, **ATENDA**. Nicho é farol, não barreira.
- **H2.6** Fontes de pesquisa: GPT, comentários YouTube, seguir pessoas do segmento, LinkedIn, Google Maps.
- **H2.7** Usar perguntas de onboarding/briefing para investigar investimento real e faturamento — dados que o cliente nem sempre voluntaria.

### 2.3 Exemplos / Cases

- **ICP infoprodutos:** Marketing digital, foco em lançamentos. Investe ~R$50k por lançamento em tráfego. Fatura ~R$300k por lançamento ou R$100k/mês recorrente.
- **ICP negócio local:** 4-8 funcionários, faturamento mínimo R$70k/mês, vendem pela internet, investem em tráfego pago.
- **ICP do Dinis:** Pai de família, casado, empresário digital, quer escalar mas contrata incompetentes. Motivação profunda: tempo e segurança para a família. Fechou com Júnior porque se identificou com os valores — não pelo preço.
- **Prospecção via Google Maps:** Dezenas de empresas de energia solar encontradas, muitas sem site ou com site amador — oportunidade clara.

### 2.4 Anti-padrões

- **ERRO:** Definir público apenas pelo nicho ("meu nicho é advocacia").
  **CORREÇÃO:** Definir por porte, momento e investimento. Advocacia é setor, não público-alvo.

- **ERRO:** Ser genérico ("atendo qualquer empresa que precise de site").
  **CORREÇÃO:** Aplicar filtro triplo de exclusão. Nem toda empresa que "precisa de site" é cliente.

- **ERRO:** Usar seguidores como critério principal de porte.
  **CORREÇÃO:** Métricas sólidas — tráfego real, faturamento declarado, tamanho da equipe, investimento em ads.

- **ERRO:** Querer atender todos os tipos de serviço ao mesmo tempo.
  **CORREÇÃO:** Focar onde resolve com mais facilidade e maior retorno por tempo.

- **ERRO:** Tratar nicho como limitação rígida e recusar clientes fora dele.
  **CORREÇÃO:** Nicho direciona comunicação, não impede negócios. Se resolve a dor, atenda.

### 2.5 Perguntas-guia

1. Quais foram seus 3 melhores clientes até hoje? O que eles tinham em comum?
2. Qual o faturamento mínimo que seu cliente ideal precisa ter para pagar seu serviço sem pestanejar?
3. Quantas pessoas tem na equipe do seu cliente típico?
4. Seu cliente ideal já investe em marketing digital ou você teria que convencê-lo?
5. Que tipo de produto ou serviço seu cliente vende? (infoproduto, serviço local, SaaS, e-commerce?)
6. Em que momento da jornada está o cliente ideal? (começando, escalando, reestruturando?)
7. Quais tipos de cliente você NÃO quer atender — e por quê?
8. Se pudesse clonar um cliente que já teve, quem seria e por quê?

### 2.6 Critérios de Validação

- [ ] `area_setor` definido com pelo menos 1 segmento — mas ICP descrito por comportamento, não só por setor
- [ ] `porte_empresa` com pelo menos 2 das 3 métricas preenchidas (faturamento, equipe, investimento)
- [ ] `filtros_exclusao[]` com pelo menos 2 critérios claros de "quem NÃO atendo"
- [ ] `momento_empresa` descrito — o agente verifica se é coerente com a oferta do builder
- [ ] Builder consegue descrever seu ICP em 2 frases sem usar a palavra "qualquer"

---

## Bloco 3 — Dor e Problema (O Que Resolver)

**Objetivo:** Identificar a dor real do cliente ideal — a raiz emocional e operacional, não o sintoma técnico.

**Campos output:** `dor_primaria`, `frustracoes[]`, `desejos[]`, `problema_traduzido`, `regra_80_20`

### 3.1 Fundamentos

Nem todo cliente sabe que tem problema. O empreendedor que não investe em marketing pode não ter consciência de que perde oportunidades todos os dias.

Frustração com freelancers é dor **recorrente e estrutural**: atrasos, erros, falta de comprometimento.

> "Chega no dia do lançamento a página tá sem link no botão."

A dor primária do cliente ideal (maduro) **NÃO** é falta de design — é **perda de tempo com retrabalho**.

A dor se desdobra em **cadeia causal**: contrata errado → retrabalho → para de focar no 80/20 → menos dinheiro → menos tempo com família → ansiedade.

> "Seja uma ponte entre a dor e o problema."

Existem dois mercados paralelos: prestação de serviço ("faço LP por X") vs resolução de problemas (a "mina de ouro"). Quem opera no segundo, ganha exponencialmente mais.

> "Eu não quero saber se você edita no Cap Cut ou no Premiere. Eu quero o meu problema resolvido."

A percepção de valor funciona como reciprocidade — entregar mais do que cobra faz o cliente sentir que o serviço vale mais. O cliente ideal já se frustrou com promessas genéricas de "alta conversão". Não cai mais nesse discurso.

### 3.2 Heurísticas

- **H3.1** Para descobrir dor real: pergunte "por quê?" repetidamente até a raiz emocional (segurança, tempo, família). Técnica dos 5 porquês.
- **H3.2** Venda para quem está preparado para comprar — o nível de consciência do cliente determina se ele vai valorizar seu trabalho.
- **H3.3** Pesquise dores em: comentários de YouTube do nicho, GPT, canais de referência do segmento.
- **H3.4** Escuta ativa do cliente atual: "me conta como posso te ajudar" — e genuinamente ouvir.
- **H3.5** Exercício imaginativo de empatia: "quanto tempo/esforço o cliente precisa investir para me pagar X? Estou recompensando na mesma medida?"

### 3.3 Exemplos / Cases

- **CPLs encarecendo:** CPLs cada vez mais caros, comparecimento nas CPLs caindo, conversão caindo — dor crescente para quem faz lançamentos.
- **Link quebrado no lançamento:** Freelancer entregou página com botão sem link no dia do lançamento ao vivo — dor de confiança irreparável.
- **Advogado de Brasília:** Concorrente cobrou R$700. Quando ouviu R$3.500, respondeu: "tá certíssimo" — ele já havia se frustrado com o barato.
- **Easy Optimize:** 12% de aumento no connect rate gerou **R$600.000 a mais** num único lançamento — demonstração matemática de impacto.
- **Hamburgueria:** Pedidos atrasados por processo manual → oportunidade de sistema de agendamento. A dor não era "site feio", era operação ineficiente.
- **Advogado de 38 anos:** Fechou com Júnior porque se identificou com os valores, não pelo portfólio. Queria mudar de vida.

### 3.4 Anti-padrões

- **ERRO:** Achar que problema do cliente é técnico (design bonito) quando é operacional (retrabalho, tempo perdido).
  **CORREÇÃO:** Mapear cadeia de dor completa — do sintoma à raiz emocional.

- **ERRO:** Vender serviço em vez de solução.
  **CORREÇÃO:** Entender que o cliente compra resultado, não entregável.

> "Se você for esse designer orçamenteiro, acabou."

- **ERRO:** Focar na página em vez do resultado.
  **CORREÇÃO:** A página é meio, não fim.

> "O grande problema do web designer é esse. Ele quer fazer a página. A página é o de menos."

### 3.5 Perguntas-guia

1. Qual é a maior reclamação que seus clientes atuais tinham do profissional anterior?
2. Quando seu cliente perde dinheiro, qual é a causa raiz — falta de tráfego, página ruim, processo quebrado?
3. Se seu cliente pudesse resolver UM problema hoje, qual seria?
4. O que seu cliente ideal deseja que vai além do entregável técnico? (tempo? segurança? paz?)
5. Qual frustração faz seu cliente perder o sono — literalmente?
6. Se você parasse de atender seu melhor cliente amanhã, qual seria o impacto real na vida dele?
7. Seu cliente sabe que tem o problema que você resolve, ou você precisa educá-lo primeiro?

### 3.6 Critérios de Validação

- [ ] `dor_primaria` descrita em termos emocionais/operacionais, não técnicos
- [ ] `frustracoes[]` com pelo menos 3 itens — vindos de pesquisa real ou experiência direta
- [ ] `problema_traduzido` é algo que o CLIENTE diria, não o builder — linguagem do ICP
- [ ] `regra_80_20` identificada: qual ponto do funil/operação gera maior impacto com menor esforço
- [ ] Builder consegue explicar a cadeia de dor em pelo menos 3 níveis de profundidade

---

## Bloco 4 — Diferencial (Como EU Resolvo)

**Objetivo:** Articular o mecanismo único do builder — a combinação de postura, competências e método que o torna difícil de substituir.

**Campos output:** `formula_diferencial`, `postura`, `hard_skills[]`, `soft_skills[]`, `mecanismo_unico`

### 4.1 Fundamentos

Diferencial nasce de **COMO** você resolve a dor específica — não do quê você faz.

> "Quais são as frustrações, como você ajuda resolver — esse é seu diferencial."

A postura correta é "Eu + cliente **contra** o problema" — parceiro, não prestador.

> "Isso muda muita coisa."

Confiança vem de **caráter**: honra, honestidade, coerência, servir ativamente — não de resultado passado ou identificação superficial.

> "Não seja um resolvedor de problemas, seja um ANIQUILADOR de problemas. Resolve + previne."

Presença no trabalho é o diferencial mais subestimado — a maioria faz a entrega "por entregar", lê mensagens superficialmente, não se envolve com o resultado.

Saber servir: ajudar além do escopo sem cobrar (redirect automático, dica de lançamento, alerta sobre erro de tráfego) gera microtransformações que constroem fidelidade.

Design bonito é **REGRA** (table stakes), não proposta de valor. O diferencial está na infraestrutura invisível — server-side, GTM, pixel, otimização, dados.

A interseção **Hard Skills + Soft Skills** explica a escassez: poucos têm técnica (design, otimização, GTM) **E** postura (comunicação, proatividade, presença). Quem tem ambos, é raro.

Intimidade com o cliente é vantagem competitiva — conhecer as fragilidades da operação dele permite atuar onde realmente importa.

### 4.2 Heurísticas

- **H4.1** Fórmula do diferencial: "Através de [método], resolvo [dor específica] e entrego [resultado mensurável]."
- **H4.2** "A forma que você faz uma coisa é a forma que faz todas" — se relaxa o processo para clientes menores, vai falhar com os ideais.
- **H4.3** Melhor cliente = paga + indica + dá autoridade. Conquista-se impressionando — entregando mais do que espera.
- **H4.4** Não se prender à limitação do material — usar todos os recursos disponíveis para fazer o melhor possível com o que tem.
- **H4.5** Cobre pelo RESULTADO, não pelo serviço.

> "Eu tô cobrando pelo resultado que eu posso gerar."

### 4.3 Exemplos / Cases

- **Mateus Werner:** 4M seguidores, +20M faturamento, cliente recorrente desde o primeiro lançamento. +40 páginas entregues. Relacionamento construído por entrega consistente acima do esperado.
- **Monitoramento ao vivo:** Lorenzi monitora CPLs ao vivo, participa de debriefings, migra páginas quando há problemas — tudo sem cobrar a mais. Isso gera confiança e recorrência.
- **Case Apple:** Mandou celular com dobro da memória após defeito → fidelidade irracional. Over delivery na resolução de problema.
- **Reposicionamento do Lorenzi:** Cálculo matemático de R$186k de diferença com otimização de connect rate — demonstração concreta de que o diferencial é mensurável.

### 4.4 Anti-padrões

- **ERRO:** Agir como "prestador de serviço" — entrega e acabou, sem envolvimento com resultado.
  **CORREÇÃO:** Parceiro de trincheira. Acompanhar o resultado, não só o entregável.

> "Esse é o cara que sempre vai ganhar pouco."

- **ERRO:** Corpo mole no suporte: não conferir botões, não colocar favicon, não configurar título/descrição.
  **CORREÇÃO:** Essas são obrigações mínimas — "corte de grama básico."

- **ERRO:** Não estar presente: ler briefing superficialmente, não buscar entender a intenção real.
  **CORREÇÃO:** Presença ativa = diferenciar-se de 95% do mercado.

- **ERRO:** Iniciante achar que precisa de diferencial claro desde o dia 1.
  **CORREÇÃO:** No início, o diferencial é construído no processo. Ele emerge da prática.

### 4.5 Perguntas-guia

1. Se um cliente seu ligasse para um amigo e dissesse "contrata esse cara porque...", como completaria a frase?
2. O que você faz que outros web designers/builders NÃO fazem?
3. Depois de entregar o projeto, você acompanha o resultado? Como?
4. Liste suas hard skills (técnicas) e soft skills (postura/comunicação). Onde é mais forte?
5. Qual foi a última vez que você entregou algo além do escopo — sem cobrar — e qual foi a reação do cliente?
6. Se eu tirasse você do seu melhor cliente hoje, o que ele perderia além da página?
7. Qual é o seu "método" — como você trabalha diferente?

### 4.6 Critérios de Validação

- [ ] `formula_diferencial` articulada no formato [método] → [dor] → [resultado]
- [ ] `hard_skills[]` e `soft_skills[]` com pelo menos 3 itens cada
- [ ] `postura` descrita vai além de "sou comprometido" — tem comportamentos concretos
- [ ] `mecanismo_unico` é algo que o concorrente não pode copiar facilmente
- [ ] Builder consegue explicar seu diferencial em 30 segundos sem mencionar "design bonito"

---

## Bloco 5 — Oferta (O Que Vendo)

**Objetivo:** Transformar competências e diferenciais em pacotes de solução nomeados, precificados e posicionados numa esteira de valor.

**Campos output:** `nome_oferta`, `escopo[]`, `entregaveis[]`, `preco`, `modelo_cobranca`, `escada_valor{entrada, principal, premium, recorrencia}`

### 5.1 Fundamentos

A solução NÃO é o entregável.

> "Você vai oferecer jardinagem ou um ambiente acolhedor?"

Vender a solução completa é superior a vender serviço isolado. Cliente compra **resultado**, não entregável técnico.

Empacotar reduz negociações, boardings e gestões de tarefa. É mais eficiente e mais lucrativo.

> "É mais fácil chegar no 5000 vendendo um pacote ou vendendo 5 identidade visual?"

A solução deve ser construída a partir dos **desejos e dores do cliente**, não do que o designer gosta de entregar.

> "Converter é obrigação. Te faço ser lembrado."

A Big Idea deve ser curta, memorável e tocar no emocional.

Entregáveis devem virar **"produtos nomeados"** (pacotes) — criam ancoragem, posição de autoridade e facilitam upsell.

**Ancoragem:** Apresente o pacote completo primeiro (valor maior), mesmo que feche só parte. A percepção fica ancorada no todo.

**Popstar = 80/20:** Alta demanda, bom lucro, menos tempo, mais resultado. Para Júnior: pacote de lançamento.

Over delivery é entregar mais **DENTRO** do produto, não algo avulso.

> "A qualidade do corte, não uma flor extra."

Aprenda com cada cliente para melhorar o produto padrão: se um pediu LGPD, coloque em todos.

Preço sobe quando o balde vaza — demanda excede capacidade.

> "É neste momento que você sobe o preço."

### 5.2 Heurísticas

- **H5.1** Retorno ÷ Tempo: o serviço com maior resultado por hora investida é o carro-chefe.
- **H5.2** Produtização em 4 passos: (1) listar TODOS os serviços → (2) precificar cada avulso → (3) marcar os de melhor retorno/tempo → (4) empacotar como solução nomeada.
- **H5.3** Agrupe por **metodologia do cliente** (lançamento semente, MVP, posicionamento), não por tipo de página.
- **H5.4** Desconto no pacote vs soma dos avulsos cria percepção de economia e parceria.
- **H5.5** Esteira obrigatória: após projeto entregue, sugira o próximo passo (down-sell, upsell, mentoria, teste AB, manutenção).
- **H5.6** Down-sell = reduzir entregáveis, NUNCA baixar preço. "Vamos reduzir um entregável, focar no essencial."
- **H5.7** Regra dos 20%: 20% dos compradores estão dispostos a pagar até 8x mais. Sempre tenha upsell pronto.
- **H5.8** Cross-sell recorrente: suporte (R$100/mês) ou teste AB (R$250/mês). 4 clientes = R$1.000 extra em ~4h.
- **H5.9** Mais eficiente criar múltiplos entregáveis para o MESMO cliente (paleta, KV, PSD são reaproveitados).
- **H5.10** Crie pacotes por contexto: lançamento, perpétuo, high ticket, posicionamento, rede social.
- **H5.11** Precificação condicional por resultado: "Se não melhorar X, custa Y. Se melhorar, custa Z."

### 5.3 Exemplos / Cases

- **Pacote "Lançamento Semente":** Identidade (R$1.000) + Criativos (R$50/un) + Membros (R$500) + Checkout (R$400) + Slides CPL (R$600) + Captura (R$1.000) + Venda+Obrigado (R$1.750) = R$5.300 → vendido por R$4.500.
- **Pacote lançamento completo (agência):** R$25.000.
- **LP 2 dobras com Easy Builder:** 3 horas, R$2.000 = R$630/hora.
- **Down-sell real:** Pacote completo R$6.797 → down-sell para R$3.500 (só venda + captura). Sem baixar preço por item.
- **Premium vs Minimalista:** Estratégia de down-sell no início — oferece Premium, fecha Minimalista se necessário.
- **Pacote "Posicionamento Digital":** Link bio + 6 postagens + página links + identidade + página de vendas.
- **Pacote "High Ticket":** Postagens + anúncios + membros + captação + formulário sessão estratégica.

### 5.4 Anti-padrões

- **ERRO:** Vender avulsos isolados em vez de soluções empacotadas.
  **CORREÇÃO:** Empacotar como solução que resolve as dores mapeadas no Bloco 3.

- **ERRO:** Responder preço avulso imediato quando cliente pergunta "quanto custa uma LP?".
  **CORREÇÃO:** Apresentar pacote completo primeiro. Ancoragem no todo.

> "Mandando 1.750, você perdeu a chance de vender 5.300."

- **ERRO:** Ficar preso ao entregável na comunicação ("faço LP responsiva otimizada em 48h").
  **CORREÇÃO:** Comunicar a transformação e o resultado que o pacote gera.

- **ERRO:** Não ter recorrência na esteira — viver de projetos one-shot.
  **CORREÇÃO:** Incluir cross-sell recorrente (suporte, teste AB, manutenção).

- **ERRO:** Achar que transformação exige mentoria cara ou programa elaborado.
  **CORREÇÃO:** Transformação acontece na entrega + atendimento + postura diária.

### 5.5 Perguntas-guia

1. Liste todos os serviços que você oferece hoje — todos, mesmo os que cobra pouco.
2. Qual desses serviços tem o melhor retorno por hora investida?
3. Seus clientes costumam precisar de mais de um serviço ao mesmo tempo? Quais combinações são frequentes?
4. Você já tem pacotes nomeados ou vende tudo avulso?
5. Quando um cliente pede desconto, como você reage hoje?
6. Após entregar um projeto, o que acontece? O cliente volta? Você sugere próximo passo?
7. Qual é o serviço que você entrega que seu cliente NÃO sabe que precisa — mas quando recebe, fica impressionado?
8. Se pudesse vender apenas 1 pacote para todos os clientes, o que teria dentro?

### 5.6 Critérios de Validação

- [ ] Pelo menos 1 pacote nomeado com escopo claro e preço definido
- [ ] `escada_valor` com pelo menos 2 degraus (entrada + principal OU principal + premium)
- [ ] Recorrência presente na esteira (suporte, teste AB, manutenção ou similar)
- [ ] Preço do pacote é inferior à soma dos avulsos — ancoragem funcional
- [ ] Builder consegue explicar o que está FORA do escopo — exclusões são tão claras quanto inclusões

---

## Bloco 6 — Posicionamento (Como Comunico)

**Objetivo:** Traduzir o diferencial e a oferta em comunicação magnética que atrai o ICP e repele o restante.

**Campos output:** `bio`, `promessa`, `elemento_autoridade`, `filtro_cta`, `linguagem_icp`

### 6.1 Fundamentos

Bio em 3 camadas: (1) abraçar a dor → (2) tocar vaidade → (3) gerar escassez.

> "Converter é obrigação. Te faço ser lembrado."
> "Seu último web designer."

Posicionamento funciona como **filtro**: atrai o bom e repele o ruim.

> "Se atrai todo mundo, teu posicionamento é ruim."

Autoridade se comunica pela **capacidade de entrega**, não por ostentação.

> "Eu não preciso ficar arrotando salsicha."

Quando todos copiam a mesma bio, o cliente iguala todos. Diferenciação é sobrevivência.

> "Se lê algo que tá na bio de outro designer, iria me equiparar."

Cada palavra precisa justificar sua existência.

> "O negócio aqui é falar mais com menos."

Autoridade por **proxy de investimento**: "quanto de investimento já passou pelas minhas páginas" é mais crível e diferenciado do que "fiz X projetos."

O cliente quer **tranquilidade e segurança**, não só métrica.

> "O projeto vai ser entregue no prazo, com compromisso."

Para público feminino, comunicação mais emocional/acolhedora. Sensações e autoestima superam métricas.

### 6.2 Heurísticas

- **H6.1** Fale a linguagem do **nível de consciência** do cliente. Se ele entende connect rate, use. Se não, traduza para benefícios tangíveis.
- **H6.2** Proposta comercial com copy vende melhor que proposta padrão — mockups, diferenciais e benefícios na proposta já é posicionamento.
- **H6.3** CTA com filtro implícito: mensagem pré-formatada no WhatsApp que já filtra. Quem não entende a linguagem, não entra em contato.
- **H6.4** Framework da bio: **Transformação → Autoridade → CTA** — mas subvertido pelo resultado real, linguagem do cliente e filtro implícito.

### 6.3 Exemplos / Cases

- **Lorenzi e lançamentos:** Tem +R$1M em lançamentos mas NÃO usa "especialista em lançamentos" na bio — seria igualado a todos que usam o mesmo rótulo.
- **Sem print de pix:** Nunca postou print de pix no Instagram mesmo com resultados expressivos. Autoridade pela competência demonstrada.
- **"Infradesigner":** Nomenclatura própria que comunica a camada técnica invisível — server-side, GTM, pixel, otimização. Diferente de tudo que existe.
- **Métricas de autoridade:** "30 milhões investidos nas páginas que criei" e "1 milhão de leads captados com 90% connect rate" — específico, verificável, diferenciado.

### 6.4 Anti-padrões

- **ERRO:** Copiar bio de outros designers (Ctrl+C / Ctrl+V).
  **CORREÇÃO:** Diferenciação baseada na sua capacidade de entrega real — o que SÓ VOCÊ faz.

- **ERRO:** Usar prints de pix e conquistas como principal autoridade.
  **CORREÇÃO:** Autoridade pela competência demonstrada, não por ostentação.

- **ERRO:** Posicionamento genérico que atrai todo tipo de cliente.
  **CORREÇÃO:** Pergunte: "seu posicionamento atual atrai o tipo de cliente que você QUER?"

- **ERRO:** Promessa que atrai público errado ("conquiste o topo do mercado" pode atrair vaidosos e não o ICP).
  **CORREÇÃO:** Alinhar promessa com ICP real definido no Bloco 2.

- **ERRO:** Usar promessa genérica "alta conversão" ou "LP otimizada".
  **CORREÇÃO:** Big Idea que toque na dor específica do seu ICP. Curta, memorável, emocional.

### 6.5 Perguntas-guia

1. Se alguém lê sua bio hoje, em 5 segundos entende o que você faz de diferente?
2. Qual métrica de autoridade você tem que seria difícil para um concorrente copiar?
3. Sua bio atual atrairia seu cliente ideal ou qualquer pessoa que precise de site?
4. Como seu melhor cliente te descreveria para outro empresário?
5. Se tivesse que resumir sua promessa em UMA frase, qual seria?
6. Seu CTA filtra — ou qualquer pessoa se sentiria confortável em mandar mensagem?
7. Você tem um "nome" para o que faz — algo que seja só seu? (ex: infradesigner, easy optimize)

### 6.6 Critérios de Validação

- [ ] `bio` com as 3 camadas presentes: dor/transformação + autoridade + escassez/CTA
- [ ] `promessa` é diferente de "alta conversão" e "LP otimizada" — toca na dor do ICP
- [ ] `elemento_autoridade` é verificável e difícil de copiar (não genérico)
- [ ] `filtro_cta` presente — a mensagem/CTA filtra quem não é ICP
- [ ] `linguagem_icp` usa termos que o cliente entende — não jargão de designer

---

## Bloco 7 — Meta Operacional (Quanto e Quando)

**Objetivo:** Definir meta de faturamento realista, compatível com capacidade de entrega, e o critério para subir preço.

**Campos output:** `ticket_medio`, `clientes_mes`, `faturamento_alvo`, `criterio_subir_preco`, `capacidade_entrega`

### 7.1 Fundamentos

Metas irrealistas geram ciclo destrutivo: frustração → procrastinação → inação → "o mercado não funciona" → designer injustiçado.

> "Sejam realistas. Se estão fazendo 2 por mês, foca nos 3K primeiro."

Crescimento é **escada**, não elevador. Cada degrau valida o próximo.

Funil automático de captação **SÓ funciona** se os fundamentos (PA, serviços, pacotes) estiverem definidos antes.

Toda vez que o balde vaza (demanda > capacidade), é o momento de subir preço.

Recorrência > volume de clientes novos. Reter custa menos e rende mais.

### 7.2 Heurísticas

- **H7.1** Faixas por nível: Iniciante → 3K/mês | Intermediário → 5-7K/mês | Avançado → 10K+/mês.
- **H7.2** Sequência obrigatória: (1) Público-alvo → (2) Serviços precificados → (3) Pacotes/soluções → (4) Posicionamento → (5) Funil de captação. Sem atalhos.
- **H7.3** Acompanhamento pós-entrega (monitorar lançamento, participar de debriefing) é o que gera recorrência e indicação.
- **H7.4** Volume de clientes planejado deve ser compatível com capacidade de entrega ANTES de estratégias de captação.
- **H7.5** Pouca demanda? Não se preocupe com preço — foco em vender. Muita demanda vazando? Hora de subir preço.

### 7.3 Exemplos / Cases

- **Ana/Aurora:** Ticket médio R$2.600, 5-6 sites/mês = R$15.000/mês — operação enxuta e consistente.
- **Agência do Júnior:** De R$500 por carrossel → R$15-20k por pacote de lançamento. Evolução por escada.
- **Cross-sell real:** 4 clientes pagando R$250/mês de teste AB = R$1.000 extra em ~4h de trabalho mensal.

### 7.4 Anti-padrões

- **ERRO:** Definir meta muito acima do momento atual (faz 2K e mira 10K direto).
  **CORREÇÃO:** Escada realista — cada degrau valida o próximo. 2K → 3K → 5K → 7K → 10K.

- **ERRO:** Frustrar-se e concluir "o mercado não funciona."
  **CORREÇÃO:** Frustração quase sempre vem de expectativas irrealistas, não de mercado ruim.

- **ERRO:** Atrair volume sem capacidade de entrega → contratar sem controle → perder qualidade → manchar reputação.
  **CORREÇÃO:** Calcular capacidade máxima antes de escalar captação.

- **ERRO:** Montar funil automático sem ter PA, serviços e pacotes definidos.
  **CORREÇÃO:** Bloquear avanço se Blocos 2, 3 e 5 não estão preenchidos. Funil sem fundamento queima dinheiro.

- **ERRO:** Baixar preço quando cliente pede desconto.
  **CORREÇÃO:** Reduzir escopo, não preço. Down-sell estruturado.

### 7.5 Perguntas-guia

1. Quanto você quer faturar nos próximos 3 meses? E em 12 meses?
2. Com base no seu ticket médio atual, quantos clientes por mês precisa para atingir essa meta?
3. Você consegue entregar essa quantidade com qualidade? Se não, qual é seu limite real?
4. Qual é sua capacidade máxima de projetos simultâneos sem perder qualidade?
5. Já teve mês que recusou cliente por falta de tempo? O que fez com o preço?
6. Qual o próximo degrau realista — qual faturamento mensal seria um avanço factível em 90 dias?
7. Você tem fonte de recorrência hoje ou vive 100% de projetos novos?
8. Qual é o critério que vai usar para decidir quando é hora de subir o preço?

### 7.6 Critérios de Validação

- [ ] `faturamento_alvo` é coerente com `serie_atual` do Bloco 1 (não pula degrau)
- [ ] `clientes_mes` × `ticket_medio` = `faturamento_alvo` — a conta fecha
- [ ] `capacidade_entrega` é compatível com `clientes_mes` — sem sobrecarga
- [ ] `criterio_subir_preco` definido com gatilho claro (ex: "quando recusar 2 clientes por falta de tempo")
- [ ] Blocos 2, 3 e 5 estão preenchidos antes de qualquer plano de captação

---

## Caminho Neural — 11 Passos Sequenciais

Sequência extraída do Lorenzi aplicando o método **para si mesmo** no vídeo de reposicionamento. Serve como blueprint para o agente guiar o aluno:

1. **Diagnóstico de contexto pessoal** — "Preciso de renda extra, mas não tenho tempo para projetos completos. Preciso de algo rápido e de alto valor." Mapear realidade antes de qualquer decisão.

2. **Inventário de competências** — Listar tudo que sabe fazer e identificar onde é mais forte. Cruzar com demanda de mercado.

3. **Mapeamento do funil do cliente** — Desenhar funil completo do cliente ideal e identificar onde está o 80/20 de impacto. Onde a alavanca é maior?

4. **Demonstração matemática do impacto** — Calcular cenários (base vs otimizado) e mostrar o delta financeiro. Provar com números que a solução se paga.

5. **Definição da fatia de mercado** — Quem fatura 6+ dígitos, equipe estruturada, investe em tráfego. Filtrar por quem pode pagar E valorizar.

6. **Definição do escopo de serviço** — O que incluir e **EXCLUIR** explicitamente. Exclusão é tão importante quanto inclusão.

7. **Prova de resultado com case real** — Dashboard de cliente mostrando melhoria após sua entrada. Evidência concreta supera qualquer promessa.

8. **Construção do posicionamento/bio** — Brainstorm iterativo de dezenas de versões, testando ângulos diferentes. Não aceitar a primeira versão.

9. **Definição de autoridade** — Escolha de métricas específicas e verificáveis (investimento que passou pelas páginas, leads captados, connect rate).

10. **Precificação** — Começar em X, reconhecer que pelo resultado poderia ser 3x. Planejar testar e escalar conforme demanda.

11. **CTA e filtro** — Mensagem pré-formatada que filtra pela linguagem. Quem não entende a linguagem, não é ICP.

---

## Frameworks Mestres

Modelos mentais transversais que permeiam todos os blocos. O agente deve referenciar o framework relevante ao guiar cada bloco.

### FM1 — 80/20 do Funil

A página de captura é o 80/20 do lançamento. Pequenas melhorias percentuais geram o maior impacto financeiro absoluto. Aplicar em qualquer análise de prioridade: onde está o 80/20 do SEU cliente?

### FM2 — Cenário Pessimista / Bom / Excelente

Projeção de 3 cenários com métricas **antes** de começar qualquer projeto ou mudança. Remove ansiedade e cria referência objetiva de sucesso.

### FM3 — Sênior que Toca o Setor

Não executor de tarefas, mas gerente de área. Faz reunião com tráfego, cobra copy, cria testes AB, monitora KPIs. Postura que justifica ticket alto.

### FM4 — Hard + Soft = Escassez

A interseção de técnica **E** postura é rara. Por isso pagam bem. A maioria tem um ou outro — quem tem ambos se torna difícil de substituir.

### FM5 — Metáfora do Balde

Balde = operação do builder. Água = clientes. Furos = falhas na entrega/processo. Torneira = canais de captação. Filtro = posicionamento. Não adianta abrir a torneira se o balde tem furo. Não adianta tampar furos se não tem filtro.

### FM6 — Lateralização de Nicho

Corte transversal por **comportamento**, não vertical por setor. Empresários que faturam R$100k+, investem em tráfego e se frustram com freelancers existem em TODOS os nichos.

### FM7 — Efeito Ímã

Posicionamento = frequência magnética. Atrai o compatível, repele o incompatível. Se atrai todo mundo, a frequência está errada.

### FM8 — Eu + Cliente vs Problema

Parceiro de trincheira, não fornecedor. A relação é de aliança contra um inimigo comum (o problema), não de comprador e vendedor.

### FM9 — Precificação Condicional

Preço base + bônus atrelado a resultado. Alinha incentivos (builder e cliente querem o mesmo), reduz objeção ("se não funcionar, paga menos") e abre porta para ticket alto.

### FM10 — Frustração Inversa

O diferencial do builder vem de **resolver a dor que o próprio mercado já causa**: atrasos, erros, falta de visão estratégica, descaso no suporte. Ser o oposto do que o cliente já sofreu.

### FM11 — Jardineiro vs Cortador de Grama

O designer que entrega LP e manda Pix = cortador de grama. Qualquer um faz, cobra barato, é substituível. O que cuida do "ambiente acolhedor" — resultado, experiência, prevenção — é jardineiro. Cobra mais, fideliza, é indicado.

### FM12 — Converter é Obrigação, Difícil é Ser Lembrado

Posicionar-se como "alta conversão" é commodity — todo designer diz isso. O diferencial é ser **memorável**: a experiência de trabalhar com você, a segurança, a presença. Isso não se copia.
