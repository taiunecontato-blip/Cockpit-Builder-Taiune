# Auditoria de Insumos Operacionais — knowledge-base.md

**Data:** 2026-08-20
**Arquivo auditado:** `00-Sistema/Skills/Plano-de-Negocio/knowledge-base.md`
**Objetivo:** Verificar se cada bloco (1-7) contém material suficiente para um agente conversacional GUIAR o aluno na construção do plano de negócio, segundo o Método Antiprospecção do Lorenzi.

---

## Bloco 1 — Contexto do Builder (Quem Sou Eu)

### 1. Fundamentos (citações/blockquotes do Lorenzi)

| # | Citação exata |
|---|---------------|
| 1 | "Esse aqui é o 80/20 do conteúdo. Não subestimem isso." |
| 2 | "Não é sobre quanto teu trampo cobra, é sobre quanto teu trampo vale." |

Conceitos fundamentais declarados (não em blockquote):
- Mentalidade e comportamento = 80% do resultado; técnica = 20%.
- Evolução de preço é consequência de competência demonstrada, não decisão arbitrária.
- Ser builder = usar/criar ferramentas para resolver problemas de alto valor no menor tempo.

### 2. Heurísticas codificadas

| Código | Texto |
|--------|-------|
| H1.1 | Se está no início (horizontal), foque no meio-termo entre volume e qualidade. Se já está no meio-termo, foque na escala vertical — especialização + ticket mais alto. |
| H1.2 | Iniciante deve cobrar barato, fechar clientes reais, adquirir experiência e montar portfólio. Preço sobe conforme competência sobe. |
| H1.3 | Trabalhar de graça é válido **SE** for com intencionalidade — para clientes que geram portfólio forte, indicações ou contratos futuros. |
| H1.4 | Aprenda por engenharia reversa: Ads Library + `sitemap.xml` de lançamentos reais para mapear funis completos. |

**Total: 4 heurísticas**

### 3. Cases/Exemplos

1. **Builder iniciante R$500:** Cobrava R$500, achou "desrespeito", não fechou por 3 meses. Ao ajustar preço para nível compatível, fechou 4 no mês seguinte.
2. **Lorenzi no início:** Começou cobrando barato, entregou acima do esperado, evolução de preço veio como consequência da demanda crescente.

**Total: 2 cases**

### 4. Anti-padrões (ERRO → CORREÇÃO)

| # | ERRO | CORREÇÃO |
|---|------|----------|
| 1 | Iniciante se recusar a cobrar barato por achar "desrespeito" — não fecha nenhum cliente. | No início, experiência e portfólio valem mais que ticket alto. O preço sobe quando a competência justifica. |
| 2 | Adicionar serviços novos (ex: copywriting via ChatGPT) sem competência consolidada no serviço principal. | Foco no que domina primeiro. Só expandir quando o core estiver sólido. |
| 3 | Não saber quanto fatura ou quanto tempo tem disponível — operar no escuro. | Números reais antes de qualquer plano. Sem diagnóstico, qualquer meta é chute. |

**Total: 3 anti-padrões**

### 5. Perguntas-guia

1. Quanto você faturou nos últimos 3 meses com serviços de web design/builder?
2. Quais são suas 3 competências mais fortes hoje — as que entrega com mais velocidade e qualidade?
3. Quantas horas por semana você tem disponíveis para trabalhar em projetos de clientes?
4. Quais ferramentas você domina? (Elementor, Webflow, Framer, Easy Builder, Figma, etc.)
5. Quantos projetos já entregou no total? E nos últimos 6 meses?
6. Você se considera iniciante, intermediário ou avançado? Por quê?
7. De 0 a 10, quanto você se sente confiante para atender um cliente que fatura R$100k/mês?

**Total: 7 perguntas**

### 6. Critérios de validação

1. `meta_faturamento` preenchido com valor numérico real (não estimativa vaga)
2. Pelo menos 3 competências listadas com nível de domínio (básico/intermediário/avançado)
3. `tempo_disponivel` definido em horas/semana — compatível com meta de faturamento desejada
4. `serie_atual` classificada coerentemente com faturamento e portfólio declarados
5. Ferramentas listadas correspondem às competências declaradas

**Total: 5 critérios**

### 7. Frameworks mestres aplicáveis

Nenhum FM explicitamente referenciado no bloco. Aplicáveis por contexto:
- **FM4** (Hard+Soft=Escassez) — avaliação de competências
- **FM5** (Metáfora do Balde) — diagnóstico antes de ação

### Avaliação de suficiência — Bloco 1

**Suficiente para conduzir conversa real?** ✅ SIM — é o bloco mais completo em termos de diagnóstico. As perguntas são concretas, os critérios são verificáveis e os anti-padrões cobrem os erros mais comuns de iniciantes.

**O que está genérico?** Pouco. A H1.4 (engenharia reversa) poderia ter um passo-a-passo mais detalhado, mas não é crítico neste bloco.

**O que está faltando?**
- Não há referência explícita aos FMs — o agente teria que inferir quais aplicar.
- Falta uma tabela/matriz de calibração: "se fatura X e tem Y projetos, série provável = Z". Hoje depende da auto-avaliação do aluno.

---

## Bloco 2 — ICP / Público-Alvo (Pra Quem)

### 1. Fundamentos (citações/blockquotes do Lorenzi)

| # | Citação exata |
|---|---------------|
| 1 | "O mercado, o nicho, não é tão importante quanto o porte do cliente." |
| 2 | "Não se apeguem ao nicho." |
| 3 | "Quem é atraído é só quem tá compatível com aquilo que eu tô comunicando." |
| 4 | "Isso aqui tem que ser ajustado frequentemente." |

Conceitos fundamentais declarados:
- Público-alvo se define por padrões de comportamento, porte e momento — NÃO pelo segmento vertical.
- Funciona como ímã — frequência certa atrai compatível e repele incompatível.
- Seguidores não é métrica confiável. Métricas sólidas: investimento em marketing, faturamento, equipe.
- ICP definido por momento de vida e nível de consciência.

### 2. Heurísticas codificadas

| Código | Texto |
|--------|-------|
| H2.1 | 5 dimensões do ICP: (1) Área/setor, (2) Momento do cliente, (3) Tipo de produto/serviço que vendem, (4) Faturamento estimado, (5) Tamanho da equipe. |
| H2.2 | Filtro de exclusão triplo: sem consciência de marketing **+** sem dinheiro **+** vai dar dor de cabeça → NÃO é público-alvo. |
| H2.3 | Google Maps para prospecção local: buscar empresas do setor, verificar se sites têm problemas que você resolve. |
| H2.4 | Usar GPT para estimar dados de mercado (faturamento médio, porte típico) quando não tem informação direta. |
| H2.5 | Se aparecer cliente fora do nicho mas sua solução resolve o problema dele, **ATENDA**. Nicho é farol, não barreira. |
| H2.6 | Fontes de pesquisa: GPT, comentários YouTube, seguir pessoas do segmento, LinkedIn, Google Maps. |
| H2.7 | Usar perguntas de onboarding/briefing para investigar investimento real e faturamento — dados que o cliente nem sempre voluntaria. |

**Total: 7 heurísticas**

### 3. Cases/Exemplos

1. **ICP infoprodutos:** Marketing digital, foco em lançamentos. ~R$50k/lançamento em tráfego. R$300k/lançamento ou R$100k/mês recorrente.
2. **ICP negócio local:** 4-8 funcionários, R$70k+/mês, vendem pela internet, investem em tráfego pago.
3. **ICP do Dinis:** Pai de família, empresário digital, quer escalar mas contrata incompetentes. Fechou com Júnior por identificação com valores.
4. **Prospecção via Google Maps:** Empresas de energia solar sem site ou com site amador — oportunidade clara.

**Total: 4 cases**

### 4. Anti-padrões (ERRO → CORREÇÃO)

| # | ERRO | CORREÇÃO |
|---|------|----------|
| 1 | Definir público apenas pelo nicho ("meu nicho é advocacia"). | Definir por porte, momento e investimento. Advocacia é setor, não público-alvo. |
| 2 | Ser genérico ("atendo qualquer empresa que precise de site"). | Aplicar filtro triplo de exclusão. Nem toda empresa que "precisa de site" é cliente. |
| 3 | Usar seguidores como critério principal de porte. | Métricas sólidas — tráfego real, faturamento declarado, tamanho da equipe, investimento em ads. |
| 4 | Querer atender todos os tipos de serviço ao mesmo tempo. | Focar onde resolve com mais facilidade e maior retorno por tempo. |
| 5 | Tratar nicho como limitação rígida e recusar clientes fora dele. | Nicho direciona comunicação, não impede negócios. Se resolve a dor, atenda. |

**Total: 5 anti-padrões**

### 5. Perguntas-guia

1. Quais foram seus 3 melhores clientes até hoje? O que eles tinham em comum?
2. Qual o faturamento mínimo que seu cliente ideal precisa ter para pagar seu serviço sem pestanejar?
3. Quantas pessoas tem na equipe do seu cliente típico?
4. Seu cliente ideal já investe em marketing digital ou você teria que convencê-lo?
5. Que tipo de produto ou serviço seu cliente vende? (infoproduto, serviço local, SaaS, e-commerce?)
6. Em que momento da jornada está o cliente ideal? (começando, escalando, reestruturando?)
7. Quais tipos de cliente você NÃO quer atender — e por quê?
8. Se pudesse clonar um cliente que já teve, quem seria e por quê?

**Total: 8 perguntas**

### 6. Critérios de validação

1. `area_setor` definido com pelo menos 1 segmento — mas ICP descrito por comportamento, não só por setor
2. `porte_empresa` com pelo menos 2 das 3 métricas preenchidas (faturamento, equipe, investimento)
3. `filtros_exclusao[]` com pelo menos 2 critérios claros de "quem NÃO atendo"
4. `momento_empresa` descrito — o agente verifica se é coerente com a oferta do builder
5. Builder consegue descrever seu ICP em 2 frases sem usar a palavra "qualquer"

**Total: 5 critérios**

### 7. Frameworks mestres aplicáveis

Nenhum FM explicitamente referenciado no bloco. Aplicáveis por contexto:
- **FM6** (Lateralização de Nicho) — corte transversal por comportamento, não vertical
- **FM7** (Efeito Ímã) — posicionamento como frequência magnética

### Avaliação de suficiência — Bloco 2

**Suficiente para conduzir conversa real?** ⚠️ PARCIALMENTE — o material conceitual é forte, mas falta um **processo passo-a-passo de construção do ICP**.

**O que está genérico?**
- As 5 dimensões do ICP (H2.1) são listadas mas não há um processo guiado para PREENCHER cada uma. O agente sabe o que perguntar, mas não como CONDUZIR a construção.
- Falta o conceito de "avatar" ou persona detalhada — nome, idade, rotina, medos, aspirações — que aparece nas aulas.

**O que está faltando?**
- **Processo passo-a-passo de construção do ICP:** "Primeiro defina X, depois Y, depois cruze com Z." Hoje são dimensões soltas.
- **Template de ICP preenchido:** Um exemplo completo de ICP preenchido campo a campo (não só narrativa).
- **Exercício de lateralização:** Como o aluno pega seu nicho vertical e faz o corte horizontal? Falta o passo-a-passo.
- **Conceito de nível de consciência do cliente** (Eugene Schwartz) é mencionado mas não detalhado — o agente não saberia classificar o cliente em níveis.
- **FM6 e FM7 não são referenciados explicitamente** — o agente teria que inferir a conexão.

---

## Bloco 3 — Dor e Problema (O Que Resolver)

### 1. Fundamentos (citações/blockquotes do Lorenzi)

| # | Citação exata |
|---|---------------|
| 1 | "Chega no dia do lançamento a página tá sem link no botão." |
| 2 | "Seja uma ponte entre a dor e o problema." |
| 3 | "Eu não quero saber se você edita no Cap Cut ou no Premiere. Eu quero o meu problema resolvido." |
| 4 | "Se você for esse designer orçamenteiro, acabou." |
| 5 | "O grande problema do web designer é esse. Ele quer fazer a página. A página é o de menos." |

Conceitos fundamentais declarados:
- Nem todo cliente sabe que tem problema.
- Frustração com freelancers é dor recorrente e estrutural.
- Dor primária do cliente maduro NÃO é falta de design — é perda de tempo com retrabalho.
- Cadeia causal: contrata errado → retrabalho → sai do 80/20 → menos dinheiro → menos tempo com família → ansiedade.
- Dois mercados: prestação de serviço vs resolução de problemas (mina de ouro).
- Percepção de valor funciona como reciprocidade.

### 2. Heurísticas codificadas

| Código | Texto |
|--------|-------|
| H3.1 | Para descobrir dor real: pergunte "por quê?" repetidamente até a raiz emocional (segurança, tempo, família). Técnica dos 5 porquês. |
| H3.2 | Venda para quem está preparado para comprar — o nível de consciência do cliente determina se ele vai valorizar seu trabalho. |
| H3.3 | Pesquise dores em: comentários de YouTube do nicho, GPT, canais de referência do segmento. |
| H3.4 | Escuta ativa do cliente atual: "me conta como posso te ajudar" — e genuinamente ouvir. |
| H3.5 | Exercício imaginativo de empatia: "quanto tempo/esforço o cliente precisa investir para me pagar X? Estou recompensando na mesma medida?" |

**Total: 5 heurísticas**

### 3. Cases/Exemplos

1. **CPLs encarecendo:** CPLs mais caros, comparecimento caindo, conversão caindo — dor crescente em lançamentos.
2. **Link quebrado no lançamento:** Freelancer entregou página com botão sem link no dia do lançamento ao vivo.
3. **Advogado de Brasília:** Concorrente cobrou R$700. Quando ouviu R$3.500, respondeu "tá certíssimo" — já se frustrou com o barato.
4. **Easy Optimize:** 12% de aumento no connect rate gerou R$600.000 a mais num único lançamento.
5. **Hamburgueria:** Pedidos atrasados por processo manual → oportunidade de sistema de agendamento. Dor era operação, não estética.
6. **Advogado de 38 anos:** Fechou com Júnior por identificação com valores, não pelo portfólio.

**Total: 6 cases**

### 4. Anti-padrões (ERRO → CORREÇÃO)

| # | ERRO | CORREÇÃO |
|---|------|----------|
| 1 | Achar que problema do cliente é técnico (design bonito) quando é operacional (retrabalho, tempo perdido). | Mapear cadeia de dor completa — do sintoma à raiz emocional. |
| 2 | Vender serviço em vez de solução. | Entender que o cliente compra resultado, não entregável. |
| 3 | Focar na página em vez do resultado. | A página é meio, não fim. |

**Total: 3 anti-padrões**

### 5. Perguntas-guia

1. Qual é a maior reclamação que seus clientes atuais tinham do profissional anterior?
2. Quando seu cliente perde dinheiro, qual é a causa raiz — falta de tráfego, página ruim, processo quebrado?
3. Se seu cliente pudesse resolver UM problema hoje, qual seria?
4. O que seu cliente ideal deseja que vai além do entregável técnico? (tempo? segurança? paz?)
5. Qual frustração faz seu cliente perder o sono — literalmente?
6. Se você parasse de atender seu melhor cliente amanhã, qual seria o impacto real na vida dele?
7. Seu cliente sabe que tem o problema que você resolve, ou você precisa educá-lo primeiro?

**Total: 7 perguntas**

### 6. Critérios de validação

1. `dor_primaria` descrita em termos emocionais/operacionais, não técnicos
2. `frustracoes[]` com pelo menos 3 itens — vindos de pesquisa real ou experiência direta
3. `problema_traduzido` é algo que o CLIENTE diria, não o builder — linguagem do ICP
4. `regra_80_20` identificada: qual ponto do funil/operação gera maior impacto com menor esforço
5. Builder consegue explicar a cadeia de dor em pelo menos 3 níveis de profundidade

**Total: 5 critérios**

### 7. Frameworks mestres aplicáveis

Nenhum FM explicitamente referenciado no bloco. Aplicáveis por contexto:
- **FM1** (80/20 do Funil) — identificar onde está a alavanca
- **FM10** (Frustração Inversa) — resolver dor que o mercado causa
- **FM11** (Jardineiro vs Cortador de Grama) — distinguir tipos de solução

### Avaliação de suficiência — Bloco 3

**Suficiente para conduzir conversa real?** ✅ SIM — é um dos blocos mais ricos. A técnica dos 5 porquês (H3.1) dá ao agente um método claro. Os cases são variados e concretos.

**O que está genérico?**
- H3.3 (pesquise dores em YouTube, GPT) é conselho genérico — não explica COMO filtrar o que encontrar.
- O conceito de "cadeia causal" é descrito mas não tem um template estruturado para o aluno preencher.

**O que está faltando?**
- **Template de cadeia de dor:** Sintoma → Causa 1 → Causa 2 → Raiz emocional. Hoje é narrativo.
- **Exercício guiado dos 5 porquês:** Exemplo completo aplicado a um caso real, passo a passo.
- **Mapeamento explícito dos FMs** — FM1, FM10, FM11 são diretamente relevantes mas não referenciados.

---

## Bloco 4 — Diferencial (Como EU Resolvo)

### 1. Fundamentos (citações/blockquotes do Lorenzi)

| # | Citação exata |
|---|---------------|
| 1 | "Quais são as frustrações, como você ajuda resolver — esse é seu diferencial." |
| 2 | "Isso muda muita coisa." (sobre postura Eu+Cliente vs Problema) |
| 3 | "Não seja um resolvedor de problemas, seja um ANIQUILADOR de problemas. Resolve + previne." |
| 4 | "Eu tô cobrando pelo resultado que eu posso gerar." |
| 5 | "Esse é o cara que sempre vai ganhar pouco." (sobre prestador que entrega e acabou) |

Conceitos fundamentais declarados:
- Diferencial nasce de COMO resolve, não do quê faz.
- Postura: "Eu + cliente contra o problema" — parceiro, não prestador.
- Confiança vem de caráter: honra, honestidade, coerência, servir ativamente.
- Presença no trabalho é diferencial subestimado.
- Saber servir além do escopo gera microtransformações.
- Design bonito é regra (table stakes), não proposta de valor.
- Interseção Hard+Soft explica a escassez.
- Intimidade com o cliente é vantagem competitiva.

### 2. Heurísticas codificadas

| Código | Texto |
|--------|-------|
| H4.1 | Fórmula do diferencial: "Através de [método], resolvo [dor específica] e entrego [resultado mensurável]." |
| H4.2 | "A forma que você faz uma coisa é a forma que faz todas" — se relaxa o processo para clientes menores, vai falhar com os ideais. |
| H4.3 | Melhor cliente = paga + indica + dá autoridade. Conquista-se impressionando — entregando mais do que espera. |
| H4.4 | Não se prender à limitação do material — usar todos os recursos disponíveis para fazer o melhor possível com o que tem. |
| H4.5 | Cobre pelo RESULTADO, não pelo serviço. |

**Total: 5 heurísticas**

### 3. Cases/Exemplos

1. **Mateus Werner:** 4M seguidores, +20M faturamento, cliente recorrente desde o primeiro lançamento. +40 páginas. Relacionamento por entrega consistente.
2. **Monitoramento ao vivo:** Lorenzi monitora CPLs ao vivo, participa de debriefings, migra páginas — sem cobrar a mais.
3. **Case Apple:** Mandou celular com dobro da memória após defeito → fidelidade irracional.
4. **Reposicionamento do Lorenzi:** R$186k de diferença com otimização de connect rate — diferencial mensurável.

**Total: 4 cases**

### 4. Anti-padrões (ERRO → CORREÇÃO)

| # | ERRO | CORREÇÃO |
|---|------|----------|
| 1 | Agir como "prestador de serviço" — entrega e acabou, sem envolvimento com resultado. | Parceiro de trincheira. Acompanhar o resultado, não só o entregável. |
| 2 | Corpo mole no suporte: não conferir botões, não colocar favicon, não configurar título/descrição. | Essas são obrigações mínimas — "corte de grama básico." |
| 3 | Não estar presente: ler briefing superficialmente, não buscar entender a intenção real. | Presença ativa = diferenciar-se de 95% do mercado. |
| 4 | Iniciante achar que precisa de diferencial claro desde o dia 1. | No início, o diferencial é construído no processo. Ele emerge da prática. |

**Total: 4 anti-padrões**

### 5. Perguntas-guia

1. Se um cliente seu ligasse para um amigo e dissesse "contrata esse cara porque...", como completaria a frase?
2. O que você faz que outros web designers/builders NÃO fazem?
3. Depois de entregar o projeto, você acompanha o resultado? Como?
4. Liste suas hard skills (técnicas) e soft skills (postura/comunicação). Onde é mais forte?
5. Qual foi a última vez que você entregou algo além do escopo — sem cobrar — e qual foi a reação do cliente?
6. Se eu tirasse você do seu melhor cliente hoje, o que ele perderia além da página?
7. Qual é o seu "método" — como você trabalha diferente?

**Total: 7 perguntas**

### 6. Critérios de validação

1. `formula_diferencial` articulada no formato [método] → [dor] → [resultado]
2. `hard_skills[]` e `soft_skills[]` com pelo menos 3 itens cada
3. `postura` descrita vai além de "sou comprometido" — tem comportamentos concretos
4. `mecanismo_unico` é algo que o concorrente não pode copiar facilmente
5. Builder consegue explicar seu diferencial em 30 segundos sem mencionar "design bonito"

**Total: 5 critérios**

### 7. Frameworks mestres aplicáveis

Nenhum FM explicitamente referenciado no bloco. Aplicáveis por contexto:
- **FM4** (Hard+Soft=Escassez) — diretamente mencionado nos fundamentos
- **FM8** (Eu+Cliente vs Problema) — postura central do bloco
- **FM10** (Frustração Inversa) — resolver o que o mercado causa
- **FM11** (Jardineiro vs Cortador de Grama) — distinção de postura

### Avaliação de suficiência — Bloco 4

**Suficiente para conduzir conversa real?** ⚠️ PARCIALMENTE — conceitos inspiracionais são fortes, mas o **processo de construção do diferencial é vago**.

**O que está genérico?**
- A H4.1 (fórmula do diferencial) é um template de frase, mas não há um exercício guiado para o aluno CHEGAR à frase. O agente teria que improvisar o processo.
- "Presença", "servir ativamente", "parceiro de trincheira" são conceitos inspiracionais — falta operacionalizar em COMPORTAMENTOS verificáveis.

**O que está faltando?**
- **Processo passo-a-passo de construção do diferencial:** "Pegue sua lista de hard skills do Bloco 1, cruze com as dores do Bloco 3, identifique onde a interseção é mais rara…"
- **Exercício de diferenciação competitiva:** Como o aluno mapeia o que concorrentes fazem e encontra seu espaço único? Não há método.
- **Checklist de "comportamentos de presença":** Exemplos concretos de ações que demonstram presença (ex: "conferir links 24h antes do lançamento", "enviar relatório pós-projeto sem ser pedido").
- **Conexão explícita entre Blocos 1-3 e 4:** O diferencial deveria ser derivado dos blocos anteriores, mas o agente não tem instrução de como fazer essa síntese.

---

## Bloco 5 — Oferta (O Que Vendo) ⭐ FOCO ESPECIAL

### 1. Fundamentos (citações/blockquotes do Lorenzi)

| # | Citação exata |
|---|---------------|
| 1 | "Você vai oferecer jardinagem ou um ambiente acolhedor?" |
| 2 | "É mais fácil chegar no 5000 vendendo um pacote ou vendendo 5 identidade visual?" |
| 3 | "Converter é obrigação. Te faço ser lembrado." |
| 4 | "A qualidade do corte, não uma flor extra." (sobre over delivery) |
| 5 | "É neste momento que você sobe o preço." (quando balde vaza) |
| 6 | "Mandando 1.750, você perdeu a chance de vender 5.300." (anti-padrão, na seção de anti-padrões) |

Conceitos fundamentais declarados:
- Solução NÃO é o entregável.
- Vender solução completa > vender serviço isolado.
- Empacotar reduz negociações, boardings e gestões de tarefa.
- Solução construída a partir de desejos/dores do cliente.
- Big Idea: curta, memorável, toca no emocional.
- Entregáveis devem virar "produtos nomeados" (pacotes).
- Ancoragem: apresentar pacote completo primeiro.
- Popstar = 80/20: alta demanda, bom lucro, menos tempo, mais resultado.
- Over delivery é dentro do produto, não algo avulso.
- Aprender com cada cliente para melhorar produto padrão.
- Preço sobe quando balde vaza (demanda > capacidade).

### 2. Heurísticas codificadas

| Código | Texto |
|--------|-------|
| H5.1 | Retorno ÷ Tempo: o serviço com maior resultado por hora investida é o carro-chefe. |
| H5.2 | Produtização em 4 passos: (1) listar TODOS os serviços → (2) precificar cada avulso → (3) marcar os de melhor retorno/tempo → (4) empacotar como solução nomeada. |
| H5.3 | Agrupe por **metodologia do cliente** (lançamento semente, MVP, posicionamento), não por tipo de página. |
| H5.4 | Desconto no pacote vs soma dos avulsos cria percepção de economia e parceria. |
| H5.5 | Esteira obrigatória: após projeto entregue, sugira o próximo passo (down-sell, upsell, mentoria, teste AB, manutenção). |
| H5.6 | Down-sell = reduzir entregáveis, NUNCA baixar preço. "Vamos reduzir um entregável, focar no essencial." |
| H5.7 | Regra dos 20%: 20% dos compradores estão dispostos a pagar até 8x mais. Sempre tenha upsell pronto. |
| H5.8 | Cross-sell recorrente: suporte (R$100/mês) ou teste AB (R$250/mês). 4 clientes = R$1.000 extra em ~4h. |
| H5.9 | Mais eficiente criar múltiplos entregáveis para o MESMO cliente (paleta, KV, PSD são reaproveitados). |
| H5.10 | Crie pacotes por contexto: lançamento, perpétuo, high ticket, posicionamento, rede social. |
| H5.11 | Precificação condicional por resultado: "Se não melhorar X, custa Y. Se melhorar, custa Z." |

**Total: 11 heurísticas** (o bloco com mais heurísticas)

### 3. Cases/Exemplos

1. **Pacote "Lançamento Semente":** Identidade (R$1.000) + Criativos (R$50/un) + Membros (R$500) + Checkout (R$400) + Slides CPL (R$600) + Captura (R$1.000) + Venda+Obrigado (R$1.750) = R$5.300 → vendido por R$4.500.
2. **Pacote lançamento completo (agência):** R$25.000.
3. **LP 2 dobras com Easy Builder:** 3h, R$2.000 = R$630/hora.
4. **Down-sell real:** Pacote R$6.797 → down-sell para R$3.500 (só venda + captura). Sem baixar preço por item.
5. **Premium vs Minimalista:** Estratégia de down-sell no início — oferece Premium, fecha Minimalista.
6. **Pacote "Posicionamento Digital":** Link bio + 6 postagens + página links + identidade + página de vendas.
7. **Pacote "High Ticket":** Postagens + anúncios + membros + captação + formulário sessão estratégica.

**Total: 7 cases** (bloco com mais exemplos concretos)

### 4. Anti-padrões (ERRO → CORREÇÃO)

| # | ERRO | CORREÇÃO |
|---|------|----------|
| 1 | Vender avulsos isolados em vez de soluções empacotadas. | Empacotar como solução que resolve as dores mapeadas no Bloco 3. |
| 2 | Responder preço avulso imediato quando cliente pergunta "quanto custa uma LP?". | Apresentar pacote completo primeiro. Ancoragem no todo. |
| 3 | Ficar preso ao entregável na comunicação ("faço LP responsiva otimizada em 48h"). | Comunicar a transformação e o resultado que o pacote gera. |
| 4 | Não ter recorrência na esteira — viver de projetos one-shot. | Incluir cross-sell recorrente (suporte, teste AB, manutenção). |
| 5 | Achar que transformação exige mentoria cara ou programa elaborado. | Transformação acontece na entrega + atendimento + postura diária. |

**Total: 5 anti-padrões**

### 5. Perguntas-guia

1. Liste todos os serviços que você oferece hoje — todos, mesmo os que cobra pouco.
2. Qual desses serviços tem o melhor retorno por hora investida?
3. Seus clientes costumam precisar de mais de um serviço ao mesmo tempo? Quais combinações são frequentes?
4. Você já tem pacotes nomeados ou vende tudo avulso?
5. Quando um cliente pede desconto, como você reage hoje?
6. Após entregar um projeto, o que acontece? O cliente volta? Você sugere próximo passo?
7. Qual é o serviço que você entrega que seu cliente NÃO sabe que precisa — mas quando recebe, fica impressionado?
8. Se pudesse vender apenas 1 pacote para todos os clientes, o que teria dentro?

**Total: 8 perguntas**

### 6. Critérios de validação

1. Pelo menos 1 pacote nomeado com escopo claro e preço definido
2. `escada_valor` com pelo menos 2 degraus (entrada + principal OU principal + premium)
3. Recorrência presente na esteira (suporte, teste AB, manutenção ou similar)
4. Preço do pacote é inferior à soma dos avulsos — ancoragem funcional
5. Builder consegue explicar o que está FORA do escopo — exclusões são tão claras quanto inclusões

**Total: 5 critérios**

### 7. Frameworks mestres aplicáveis

Nenhum FM explicitamente referenciado no bloco. Aplicáveis por contexto:
- **FM5** (Metáfora do Balde) — dimensionar capacidade antes de escalar
- **FM9** (Precificação Condicional) — diretamente presente como H5.11
- **FM11** (Jardineiro vs Cortador de Grama) — pacote vs serviço avulso
- **FM12** (Converter é Obrigação) — citado nos fundamentos

### Avaliação de suficiência — Bloco 5 ⭐

**Suficiente para conduzir conversa real?** ⚠️ PARCIALMENTE — é o bloco com mais heurísticas e exemplos, mas há **lacunas conceituais significativas** entre o que está nas aulas e o que está na base.

**O que ESTÁ bem documentado:**
- H5.2 (produtização em 4 passos) é o melhor processo passo-a-passo da base inteira
- Os 7 cases de pacotes são concretos e com preços reais
- Ancoragem, down-sell e cross-sell estão operacionalizados
- H5.11 (precificação condicional) está presente

**O que está genérico?**
- "Big Idea: curta, memorável, toca no emocional" — citado nos fundamentos mas sem PROCESSO para construir uma Big Idea. Como o aluno chega à sua Big Idea? Não há exercício.
- "Popstar = 80/20" — conceito mencionado mas não desdobrado. Como o aluno identifica seu Popstar? É só "melhor retorno por hora"?

**O que está FALTANDO (comparação com conteúdo das aulas):**

| Conceito das aulas | Status na KB | Impacto |
|---------------------|-------------|---------|
| **Produtização em 4 passos** | ✅ Presente (H5.2) | OK |
| **Conceito do Popstar** | ⚠️ Mencionado superficialmente | Falta explicar: alta demanda + bom lucro + menos tempo + mais resultado. Como identificar? |
| **Ancoragem** | ✅ Presente (fundamentos + H5.4 + anti-padrão) | OK |
| **Escada de valor** | ⚠️ Mencionada nos campos output e critérios | Falta definir os degraus com clareza: entrada → principal → premium → recorrência. Não há processo de como MONTAR a escada. |
| **Big Idea** | ⚠️ Citada nos fundamentos ("curta, memorável, emocional") | Falta PROCESSO de construção. Como o aluno cria a Big Idea? Nenhum exercício, nenhum template. |
| **Modelo condicional** | ✅ Presente (H5.11 + FM9) | OK, mas sem exemplo numérico detalhado. |
| **Processo de dar nome ao pacote** | ❌ Ausente | Como o builder nomeia seus pacotes? O case mostra nomes prontos, mas não o processo criativo. |
| **Matriz retorno × tempo** | ⚠️ Implícita em H5.1 | Falta template visual/estruturado. O aluno deveria plotar serviços numa matriz. |
| **Exemplos de esteira completa** | ⚠️ Parcial | Há pacotes isolados, mas não uma esteira COMPLETA mostrando: isca → entrada → principal → premium → recorrência. |
| **Regra de precificação por hora** | ⚠️ Há 1 exemplo (R$630/h) | Falta diretriz: "quanto deveria ser sua hora mínima por série?" |
| **Valor percebido vs custo real** | ❌ Ausente | Conceito de que o cliente paga pelo valor percebido, não pelo custo de produção. |
| **Proposta comercial como ferramenta de venda** | ❌ Ausente neste bloco | Mencionada no Bloco 6 (H6.2), mas deveria ter estrutura aqui. |

---

## Bloco 6 — Posicionamento (Como Comunico)

### 1. Fundamentos (citações/blockquotes do Lorenzi)

| # | Citação exata |
|---|---------------|
| 1 | "Converter é obrigação. Te faço ser lembrado." |
| 2 | "Seu último web designer." |
| 3 | "Se atrai todo mundo, teu posicionamento é ruim." |
| 4 | "Eu não preciso ficar arrotando salsicha." |
| 5 | "Se lê algo que tá na bio de outro designer, iria me equiparar." |
| 6 | "O negócio aqui é falar mais com menos." |
| 7 | "O projeto vai ser entregue no prazo, com compromisso." |

Conceitos fundamentais declarados:
- Bio em 3 camadas: (1) abraçar a dor → (2) tocar vaidade → (3) gerar escassez.
- Posicionamento funciona como filtro.
- Autoridade por capacidade de entrega, não ostentação.
- Diferenciação é sobrevivência — se todos copiam a mesma bio, cliente iguala todos.
- Cada palavra justifica existência.
- Autoridade por proxy de investimento.
- Cliente quer tranquilidade e segurança.
- Para público feminino: comunicação mais emocional/acolhedora.

### 2. Heurísticas codificadas

| Código | Texto |
|--------|-------|
| H6.1 | Fale a linguagem do **nível de consciência** do cliente. Se ele entende connect rate, use. Se não, traduza para benefícios tangíveis. |
| H6.2 | Proposta comercial com copy vende melhor que proposta padrão — mockups, diferenciais e benefícios na proposta já é posicionamento. |
| H6.3 | CTA com filtro implícito: mensagem pré-formatada no WhatsApp que já filtra. Quem não entende a linguagem, não entra em contato. |
| H6.4 | Framework da bio: **Transformação → Autoridade → CTA** — mas subvertido pelo resultado real, linguagem do cliente e filtro implícito. |

**Total: 4 heurísticas**

### 3. Cases/Exemplos

1. **Lorenzi e lançamentos:** Tem +R$1M em lançamentos mas NÃO usa "especialista em lançamentos" na bio.
2. **Sem print de pix:** Nunca postou print de pix no Instagram.
3. **"Infradesigner":** Nomenclatura própria que comunica camada técnica invisível.
4. **Métricas de autoridade:** "30 milhões investidos nas páginas que criei" e "1 milhão de leads captados com 90% connect rate".

**Total: 4 cases**

### 4. Anti-padrões (ERRO → CORREÇÃO)

| # | ERRO | CORREÇÃO |
|---|------|----------|
| 1 | Copiar bio de outros designers (Ctrl+C / Ctrl+V). | Diferenciação baseada na sua capacidade de entrega real. |
| 2 | Usar prints de pix e conquistas como principal autoridade. | Autoridade pela competência demonstrada, não por ostentação. |
| 3 | Posicionamento genérico que atrai todo tipo de cliente. | Pergunte: "seu posicionamento atual atrai o tipo de cliente que você QUER?" |
| 4 | Promessa que atrai público errado ("conquiste o topo do mercado" pode atrair vaidosos). | Alinhar promessa com ICP real definido no Bloco 2. |
| 5 | Usar promessa genérica "alta conversão" ou "LP otimizada". | Big Idea que toque na dor específica do seu ICP. Curta, memorável, emocional. |

**Total: 5 anti-padrões**

### 5. Perguntas-guia

1. Se alguém lê sua bio hoje, em 5 segundos entende o que você faz de diferente?
2. Qual métrica de autoridade você tem que seria difícil para um concorrente copiar?
3. Sua bio atual atrairia seu cliente ideal ou qualquer pessoa que precise de site?
4. Como seu melhor cliente te descreveria para outro empresário?
5. Se tivesse que resumir sua promessa em UMA frase, qual seria?
6. Seu CTA filtra — ou qualquer pessoa se sentiria confortável em mandar mensagem?
7. Você tem um "nome" para o que faz — algo que seja só seu? (ex: infradesigner, easy optimize)

**Total: 7 perguntas**

### 6. Critérios de validação

1. `bio` com as 3 camadas presentes: dor/transformação + autoridade + escassez/CTA
2. `promessa` é diferente de "alta conversão" e "LP otimizada" — toca na dor do ICP
3. `elemento_autoridade` é verificável e difícil de copiar (não genérico)
4. `filtro_cta` presente — a mensagem/CTA filtra quem não é ICP
5. `linguagem_icp` usa termos que o cliente entende — não jargão de designer

**Total: 5 critérios**

### 7. Frameworks mestres aplicáveis

Nenhum FM explicitamente referenciado no bloco. Aplicáveis por contexto:
- **FM7** (Efeito Ímã) — posicionamento como frequência
- **FM12** (Converter é Obrigação) — diretamente citado

### Avaliação de suficiência — Bloco 6

**Suficiente para conduzir conversa real?** ⚠️ PARCIALMENTE — o framework conceitual é claro, mas falta o **processo iterativo de construção da bio**.

**O que está genérico?**
- H6.4 (framework da bio: Transformação → Autoridade → CTA) é um template, mas não há exercício guiado de como PREENCHER cada camada.
- "Big Idea curta, memorável, emocional" aparece como anti-padrão (correção) mas sem processo de brainstorming.

**O que está faltando?**
- **Exercício de brainstorming iterativo de bio:** O Caminho Neural (passo 8) diz "brainstorm iterativo de dezenas de versões", mas não há template ou método para isso.
- **Exemplos de bios RUINS vs BOAS lado a lado:** O case do Lorenzi mostra o que ele faz, mas falta um "antes/depois" para o aluno médio.
- **Adaptação por público:** Menciona "público feminino = mais emocional", mas não tem diretrizes para outros perfis de ICP.
- **Template de proposta comercial:** H6.2 diz que proposta com copy vende melhor, mas não há estrutura de proposta.

---

## Bloco 7 — Meta Operacional (Quanto e Quando)

### 1. Fundamentos (citações/blockquotes do Lorenzi)

| # | Citação exata |
|---|---------------|
| 1 | "Sejam realistas. Se estão fazendo 2 por mês, foca nos 3K primeiro." |

Conceitos fundamentais declarados:
- Metas irrealistas geram ciclo destrutivo: frustração → procrastinação → inação → "o mercado não funciona".
- Crescimento é escada, não elevador.
- Funil automático SÓ funciona se fundamentos (PA, serviços, pacotes) estiverem definidos.
- Balde vaza (demanda > capacidade) = momento de subir preço.
- Recorrência > volume de clientes novos.

### 2. Heurísticas codificadas

| Código | Texto |
|--------|-------|
| H7.1 | Faixas por nível: Iniciante → 3K/mês \| Intermediário → 5-7K/mês \| Avançado → 10K+/mês. |
| H7.2 | Sequência obrigatória: (1) Público-alvo → (2) Serviços precificados → (3) Pacotes/soluções → (4) Posicionamento → (5) Funil de captação. Sem atalhos. |
| H7.3 | Acompanhamento pós-entrega (monitorar lançamento, participar de debriefing) é o que gera recorrência e indicação. |
| H7.4 | Volume de clientes planejado deve ser compatível com capacidade de entrega ANTES de estratégias de captação. |
| H7.5 | Pouca demanda? Não se preocupe com preço — foco em vender. Muita demanda vazando? Hora de subir preço. |

**Total: 5 heurísticas**

### 3. Cases/Exemplos

1. **Ana/Aurora:** Ticket médio R$2.600, 5-6 sites/mês = R$15.000/mês — operação enxuta e consistente.
2. **Agência do Júnior:** De R$500/carrossel → R$15-20k/pacote de lançamento. Evolução por escada.
3. **Cross-sell real:** 4 clientes × R$250/mês de teste AB = R$1.000 extra em ~4h mensal.

**Total: 3 cases**

### 4. Anti-padrões (ERRO → CORREÇÃO)

| # | ERRO | CORREÇÃO |
|---|------|----------|
| 1 | Definir meta muito acima do momento atual (faz 2K e mira 10K direto). | Escada realista — cada degrau valida o próximo. 2K → 3K → 5K → 7K → 10K. |
| 2 | Frustrar-se e concluir "o mercado não funciona." | Frustração quase sempre vem de expectativas irrealistas, não de mercado ruim. |
| 3 | Atrair volume sem capacidade de entrega → contratar sem controle → perder qualidade. | Calcular capacidade máxima antes de escalar captação. |
| 4 | Montar funil automático sem ter PA, serviços e pacotes definidos. | Bloquear avanço se Blocos 2, 3 e 5 não estão preenchidos. |
| 5 | Baixar preço quando cliente pede desconto. | Reduzir escopo, não preço. Down-sell estruturado. |

**Total: 5 anti-padrões**

### 5. Perguntas-guia

1. Quanto você quer faturar nos próximos 3 meses? E em 12 meses?
2. Com base no seu ticket médio atual, quantos clientes por mês precisa para atingir essa meta?
3. Você consegue entregar essa quantidade com qualidade? Se não, qual é seu limite real?
4. Qual é sua capacidade máxima de projetos simultâneos sem perder qualidade?
5. Já teve mês que recusou cliente por falta de tempo? O que fez com o preço?
6. Qual o próximo degrau realista — qual faturamento mensal seria um avanço factível em 90 dias?
7. Você tem fonte de recorrência hoje ou vive 100% de projetos novos?
8. Qual é o critério que vai usar para decidir quando é hora de subir o preço?

**Total: 8 perguntas**

### 6. Critérios de validação

1. `faturamento_alvo` é coerente com `serie_atual` do Bloco 1 (não pula degrau)
2. `clientes_mes` × `ticket_medio` = `faturamento_alvo` — a conta fecha
3. `capacidade_entrega` é compatível com `clientes_mes` — sem sobrecarga
4. `criterio_subir_preco` definido com gatilho claro (ex: "quando recusar 2 clientes por falta de tempo")
5. Blocos 2, 3 e 5 estão preenchidos antes de qualquer plano de captação

**Total: 5 critérios**

### 7. Frameworks mestres aplicáveis

Nenhum FM explicitamente referenciado no bloco. Aplicáveis por contexto:
- **FM2** (Cenário Pessimista/Bom/Excelente) — projeção de meta
- **FM5** (Metáfora do Balde) — dimensionar capacidade

### Avaliação de suficiência — Bloco 7

**Suficiente para conduzir conversa real?** ✅ SIM — é objetivo e calculável. As faixas por nível (H7.1) e a matemática simples (clientes × ticket = meta) dão ao agente lógica clara.

**O que está genérico?**
- H7.1 (faixas por nível) são referências úteis, mas poderiam ter mais granularidade (ex: sub-faixas por tipo de serviço).

**O que está faltando?**
- **FM2 (3 cenários) não está referenciado** — o agente deveria guiar o aluno a fazer projeção pessimista/boa/excelente, mas não sabe que esse framework existe para este bloco.
- **Calculadora de capacidade:** Fórmula tipo "horas disponíveis ÷ horas por projeto = projetos máximos". Está implícita mas não operacionalizada.
- **Plano de ação com timeline:** O bloco define metas mas não um plano de 30/60/90 dias.

---

## Elementos Transversais

### Caminho Neural (11 Passos)

Presente na KB como sequência extraída do Lorenzi aplicando o método para si mesmo. Serve como blueprint.

**Status:** ✅ Documentado, mas **não referenciado pelos blocos**. O agente não sabe quando usar essa sequência em complemento aos blocos.

### Frameworks Mestres (FM1-FM12)

| FM | Nome | Blocos onde seria útil | Referenciado nos blocos? |
|----|------|----------------------|------------------------|
| FM1 | 80/20 do Funil | 3, 5, 7 | ❌ Não |
| FM2 | Cenário Pessimista/Bom/Excelente | 7 | ❌ Não |
| FM3 | Sênior que Toca o Setor | 1, 4 | ❌ Não |
| FM4 | Hard+Soft=Escassez | 1, 4 | ❌ Não (conceito aparece no texto do Bloco 4 mas sem referência ao FM) |
| FM5 | Metáfora do Balde | 1, 5, 7 | ❌ Não |
| FM6 | Lateralização de Nicho | 2 | ❌ Não |
| FM7 | Efeito Ímã | 2, 6 | ❌ Não |
| FM8 | Eu+Cliente vs Problema | 4 | ❌ Não |
| FM9 | Precificação Condicional | 5 | ❌ Não (conceito aparece como H5.11 mas sem referência ao FM) |
| FM10 | Frustração Inversa | 3, 4 | ❌ Não |
| FM11 | Jardineiro vs Cortador de Grama | 3, 4, 5 | ❌ Não |
| FM12 | Converter é Obrigação | 5, 6 | ❌ Não (citação aparece mas sem referência ao FM) |

**Diagnóstico:** NENHUM framework mestre é explicitamente referenciado dentro dos blocos. O agente teria que inferir quais FMs se aplicam — ou simplesmente não usá-los, desperdiçando material de alta qualidade.

---

## Resumo Quantitativo

| Bloco | Citações | Heurísticas | Cases | Anti-padrões | Perguntas | Critérios | Suficiente? |
|-------|----------|-------------|-------|-------------|-----------|-----------|-------------|
| 1 — Contexto | 2 | 4 | 2 | 3 | 7 | 5 | ✅ Sim |
| 2 — ICP | 4 | 7 | 4 | 5 | 8 | 5 | ⚠️ Parcial |
| 3 — Dor | 5 | 5 | 6 | 3 | 7 | 5 | ✅ Sim |
| 4 — Diferencial | 5 | 5 | 4 | 4 | 7 | 5 | ⚠️ Parcial |
| 5 — Oferta | 6 | 11 | 7 | 5 | 8 | 5 | ⚠️ Parcial |
| 6 — Posicionamento | 7 | 4 | 4 | 5 | 7 | 5 | ⚠️ Parcial |
| 7 — Meta | 1 | 5 | 3 | 5 | 8 | 5 | ✅ Sim |
| **TOTAL** | **30** | **41** | **30** | **30** | **52** | **35** | — |

---

## Avaliação Crítica Global

### O que a KB faz BEM

1. **Estrutura consistente:** Todos os 7 blocos seguem o mesmo formato (Fundamentos → Heurísticas → Cases → Anti-padrões → Perguntas → Critérios). Isso dá previsibilidade ao agente.
2. **Voz autêntica do Lorenzi:** 30 blockquotes com frases exatas. O agente pode citar o mentor.
3. **Anti-padrões como guardrails:** 30 pares ERRO→CORREÇÃO são essenciais para o agente identificar quando o aluno está desviando.
4. **Cases concretos com números:** R$500→4 clientes, R$5.300→R$4.500, R$186k de delta, R$630/hora. Números reais dão credibilidade.
5. **Critérios de validação objetivos:** 35 critérios verificáveis evitam que o agente aceite respostas vagas.

### O que a KB faz MAL (problemas estruturais)

1. **Frameworks mestres desconectados dos blocos:** 12 FMs existem mas ZERO são referenciados dentro dos blocos. O agente não sabe quando acioná-los. Isso desperdiça ~30% do material mais valioso da base.

2. **Processos passo-a-passo ausentes nos blocos críticos:** Os Blocos 2 (ICP), 4 (Diferencial) e 6 (Posicionamento) têm conceitos, mas não têm PROCESSOS de construção guiada. O agente sabe o que perguntar, mas não como conduzir a montagem.

3. **Bloco 5 tem lacunas conceituais vs conteúdo das aulas:**
   - Big Idea: mencionada sem processo de construção
   - Escada de valor: mencionada nos campos output mas sem definição dos degraus
   - Popstar: citado como "80/20" mas não operacionalizado
   - Valor percebido vs custo real: ausente
   - Processo de dar nome ao pacote: ausente
   - Proposta comercial: mencionada no Bloco 6 mas sem template

4. **Caminho Neural sub-utilizado:** Os 11 passos existem mas não são referenciados pelos blocos. O agente não sabe se deve usar os 11 passos OU os 7 blocos — ou como eles se complementam.

### Análise Específica: Blocos 2, 4 e 5 — O processo passo-a-passo está claro?

#### Bloco 2 (ICP) — ⚠️ NÃO está claro o suficiente

O agente sabe as 5 dimensões (H2.1) e tem perguntas, mas não tem um processo tipo:
> "Passo 1: Liste seus 3 melhores clientes → Passo 2: Identifique o que têm em comum nas 5 dimensões → Passo 3: Aplique o filtro de exclusão triplo → Passo 4: Descreva o ICP em 2 frases → Passo 5: Valide com os critérios."

O agente teria que improvisar essa sequência.

#### Bloco 4 (Diferencial) — ⚠️ NÃO está claro o suficiente

O agente tem a fórmula H4.1 ("Através de [X], resolvo [Y] e entrego [Z]"), mas não tem o processo de como o aluno CHEGA a preencher X, Y e Z. Deveria ser algo como:
> "Passo 1: Pegue hard_skills do Bloco 1 → Passo 2: Cruze com dor_primaria do Bloco 3 → Passo 3: Identifique a interseção que é RARA (FM4) → Passo 4: Descreva comportamentos de presença concretos → Passo 5: Articule na fórmula H4.1."

#### Bloco 5 (Oferta) — ⚠️ PARCIALMENTE claro

H5.2 (produtização em 4 passos) é o melhor processo da base. MAS:
- Falta o passo de **construir a escada de valor** (após produtizar, como montar entrada → principal → premium → recorrência?)
- Falta o passo de **definir a Big Idea** do pacote
- Falta o passo de **dar nome** ao pacote
- Falta o passo de **montar a proposta comercial**

### Recomendações de Ação (prioridade)

| Prioridade | Ação | Impacto |
|------------|------|---------|
| 🔴 P0 | **Referenciar FMs dentro de cada bloco** — adicionar seção "Frameworks aplicáveis" em cada bloco com instruções de quando/como o agente deve acioná-los | Conecta 30% do material que hoje está "morto" |
| 🔴 P0 | **Adicionar processo passo-a-passo nos Blocos 2, 4 e 5** — sequência numerada que o agente segue para CONSTRUIR (não só perguntar) | Transforma o agente de "entrevistador" em "construtor guiado" |
| 🟡 P1 | **Completar Bloco 5 com conceitos das aulas:** Big Idea (processo), escada de valor (degraus), Popstar (critérios), nomeação de pacotes, proposta comercial | Elimina lacunas que o usuário já identificou |
| 🟡 P1 | **Definir relação Blocos × Caminho Neural** — mapear quais dos 11 passos correspondem a quais blocos | Resolve ambiguidade sobre qual sequência usar |
| 🟢 P2 | **Adicionar template preenchido completo** em cada bloco — exemplo end-to-end de ICP, diferencial, pacote, bio | Dá ao agente um "modelo" para comparar o output do aluno |
| 🟢 P2 | **Adicionar exercícios guiados** — "brainstorm 10 versões de bio" (Bloco 6), "5 porquês aplicados" (Bloco 3), "matriz retorno × tempo" (Bloco 5) | Transforma perguntas em ATIVIDADES |
