# Especificacao: Sistema de Memoria — Skill Plano de Negocio

## 1. ARQUITETURA DA MEMORIA

### 1.1 Onde fica

```
10-Obra/Plano-de-Negocio/
└── .builder/
    ├── perfil.yaml          ← Bloco 1 (ja existe)
    └── memory.yaml          ← NOVO: memoria persistente entre sessoes
```

O arquivo `memory.yaml` vive junto do `perfil.yaml` na pasta `.builder/` — a mesma pasta que ja guarda dados internos do agente. Nao e um arquivo que o builder edita manualmente; e infraestrutura do Mentor Builder.

### 1.2 Principio de design

A memoria NAO duplica dados. Os `_dados.yaml` dos blocos sao a fonte da verdade para o conteudo de cada bloco. A memoria guarda apenas:

1. **Estado de navegacao** — onde o builder parou no fluxo
2. **Snapshot de decisoes-chave** — valores que o agente precisa consultar rapido sem ler 7 arquivos
3. **Historico de evolucao** — o que mudou ao longo do tempo (serie, precos, ticket)
4. **Contexto de sessao** — timestamps, versao do plano, tarefas pendentes

### 1.3 Fluxo de leitura/escrita

```
INICIO DA SESSAO
│
├─ 1. Le memory.yaml
│     → Sabe: ultimo bloco, serie, versao, decisoes-chave
│
├─ 2. Le perfil.yaml
│     → Confirma: serie atual, nome, dados do builder
│
├─ 3. Le _dados.yaml dos blocos relevantes (sob demanda)
│     → So le o que precisa (ex: se vai revisar Bloco 5, le pacotes/_dados.yaml)
│
├─ 4. Compara memory.yaml com estado real dos arquivos
│     → Detecta: inconsistencias, arquivos novos que nao estavam na memoria
│
└─ 5. Monta contexto e inicia conversa com retomada precisa

DURANTE A SESSAO
│
├─ A cada decisao importante do builder:
│     → Atualiza snapshot de decisoes na memoria (em buffer)
│
└─ A cada checkpoint de parede salvo:
      → Grava memory.yaml com estado atualizado

FIM DA SESSAO
│
├─ Grava memory.yaml com:
│     → ultimo_bloco_completo atualizado
│     → ultima_parede_salva atualizada
│     → decisoes-chave atualizadas
│     → timestamp da sessao
│     → registro de evolucao (se houve mudanca)
│
└─ Se houve mudanca de serie, preco ou posicionamento:
      → Adiciona entrada no historico de evolucao
```

### 1.4 Quando gravar

| Evento | Acao na memoria |
|--------|----------------|
| Checkpoint de parede salvo | Atualiza `progresso`, `decisoes`, `timestamps` |
| Serie reclassificada | Atualiza `serie_atual`, adiciona ao `historico_evolucao` |
| Preco/ticket alterado | Atualiza `decisoes.precos`, adiciona ao `historico_evolucao` |
| Posicionamento redefinido | Atualiza `decisoes.posicionamento`, adiciona ao `historico_evolucao` |
| Sessao encerrada (qualquer motivo) | Atualiza `ultima_sessao`, `resumo_sessao` |
| Builder completa revisita | Incrementa `versao_plano`, registra mudancas |

---

## 2. O QUE A MEMORIA GUARDA

### 2.1 Estado do fluxo

- Ultimo bloco completo (1-7)
- Ultima parede salva (1-4)
- Bloco em andamento (se parou no meio)
- Etapa em andamento dentro do bloco (FUNDAMENTAR/GUIAR/VALIDAR/REGISTRAR)
- Se e primeira passagem ou revisita
- Versao atual do plano

### 2.2 Perfil do builder (snapshot)

Nao duplica o `perfil.yaml` inteiro — guarda apenas o que o agente precisa para calibrar sem abrir outro arquivo:

- Nome
- Serie atual
- Faturamento mensal (ultimo dado)
- Ticket medio atual
- Horas disponiveis/semana
- Competencias-chave (lista resumida)

### 2.3 Estado de clientes

- Tem clientes ativos? (sim/nao)
- Quantos clientes ativos
- Quantos projetos entregues desde o ultimo checkpoint
- Tem recorrencia ativa? Quantas?
- Fonte principal de aquisicao

### 2.4 Decisoes tomadas

Snapshot das decisoes mais importantes, extraidas dos blocos. Cada decisao registra o valor e quando foi definida:

- ICP definido (resumo em 1 frase)
- Dor primaria (resumo em 1 frase)
- Formula diferencial
- Pacote principal: nome + preco
- Escada de valor: nomes e precos
- Frase de posicionamento / frase-mae
- Meta de 90 dias
- Criterio de subida de preco

### 2.5 Historico de precos

Array cronologico de mudancas de preco:

- Data da mudanca
- Preco anterior → preco novo
- Pacote afetado
- Motivo da mudanca (se registrado)

### 2.6 Historico de evolucao

Array cronologico de marcos:

- Mudanca de serie (iniciante → intermediario, etc.)
- Aumento de ticket
- Novo pacote adicionado
- Meta batida
- Posicionamento redefinido

### 2.7 Tarefas pendentes

Referencia ao `tarefas.md` + snapshot das tarefas criticas que afetam o proximo passo do builder:

- Tarefas do ultimo checkpoint que ainda estao abertas
- Prazo associado (se houver)
- Prioridade (alta/media/baixa)

### 2.8 Timestamps

- Data de criacao do plano
- Data da ultima sessao
- Data de cada parede salva
- Data de cada revisita

---

## 3. COMO O AGENTE USA A MEMORIA

### 3.1 Inicio da sessao — Retomada

```
1. Le memory.yaml
2. SE memory.yaml nao existe:
     → Primeira sessao. Fluxo normal (Bloco 1).
3. SE memory.yaml existe:
     a. Identifica ultimo_bloco_completo e ultima_parede
     b. Identifica se ha bloco em andamento (parou no meio)
     c. Le perfil.yaml para confirmar serie
     d. Le _dados.yaml dos blocos ja completos (sob demanda)
     e. Monta saudacao com retomada:
        - "E ai, [nome]! Vi que voce ja tem [X] paredes levantadas."
        - "Ultimo bloco completo: [nome]. [Etapa/bloco] em andamento."
        - "Quer continuar de onde parou ou revisar algo?"
```

**Regra critica:** Se o builder parou no meio de um bloco (ex: Bloco 3, etapa GUIAR), o agente retoma EXATAMENTE daquele ponto. Nao refaz perguntas ja respondidas naquele bloco.

### 3.2 Durante a conversa — Calibracao

A memoria calibra o comportamento do agente em tempo real:

| Dado da memoria | Como calibra |
|-----------------|-------------|
| `serie_atual` | Profundidade das perguntas e complexidade dos pacotes |
| `ticket_medio` | Sugestoes de preco realistas (proximo degrau, nao salto) |
| `clientes_ativos` | Se pode sugerir recorrencia ou se e cedo demais |
| `frase_posicionamento` | Lembrar em blocos posteriores para manter coerencia |
| `formula_diferencial` | Referencia ao construir pacotes e posicionamento |
| `dor_primaria` | Ancora todas as sugestoes na dor real do ICP |
| `meta_90_dias` | Conecta cada decisao com o objetivo concreto |
| `tarefas_pendentes` | Cobra execucao antes de avancar para novos blocos |

**Exemplo de calibracao:**

```
# Builder intermediario voltando para revisitar

MENTOR: E ai, Lorenzi! Vi que voce levantou as 4 paredes do plano v1.
Teu ticket ta em R$2.800 no Estrutura de Conversao, meta de R$15k em 90 dias.

Na ultima sessao, ficou de:
1. Converter 3 clientes para Parceiro de Trafego
2. Fechar proximo projeto no novo ticket

Como foi? Conseguiu executar?
```

### 3.3 Final da sessao — Atualizacao

Ao encerrar (por conclusao de parede ou por interrupção do builder):

```
1. Atualiza progresso:
   - ultimo_bloco_completo
   - ultima_parede_salva
   - bloco_em_andamento (se aplicavel)
   - etapa_em_andamento (se parou no meio)

2. Atualiza decisoes-chave:
   - Qualquer valor que mudou durante a sessao

3. Registra evolucao (se houve):
   - Mudou de serie?
   - Mudou preco?
   - Redefiniu posicionamento?

4. Atualiza tarefas pendentes:
   - Novas tarefas geradas nesta sessao
   - Tarefas concluidas removidas

5. Grava timestamp da sessao

6. Grava memory.yaml
```

### 3.4 Em revisitas — Deteccao de evolucao

Quando o builder volta apos ter atendido clientes:

```
1. Compara estado anterior (memoria) com estado atual (conversa):
   - "Na ultima vez voce estava com ticket de R$1.300. E agora?"
   - "Voce disse que ia converter 3 clientes para recorrencia. Conseguiu?"

2. Detecta gatilhos de mudanca de serie:
   - Faturamento subiu? Numero de clientes subiu?
   - SE atingiu criterios da proxima serie:
     → "Lorenzi, com 11 projetos entregues e ticket de R$2.800,
        voce ja esta operando como intermediario consolidado.
        Vamos recalibrar os blocos pra refletir isso."

3. Compara precos anteriores com atuais:
   - Se subiu: celebra e registra o marco
   - Se desceu: confronta com respeito — "Baixou preco ou reduziu escopo?"

4. Atualiza memoria com novos dados
```

---

## 4. SCHEMA YAML — `.builder/memory.yaml`

```yaml
# =============================================================
# MEMORIA PERSISTENTE — Mentor Builder
# Este arquivo e gerenciado automaticamente pelo agente.
# NAO editar manualmente.
# =============================================================

versao_schema: 1
versao_plano: 1
tipo_sessao: "primeira_passagem"  # primeira_passagem | revisita

# --- PROGRESSO DO FLUXO ---
progresso:
  ultimo_bloco_completo: 7  # 0-7 (0 = nenhum)
  ultima_parede_salva: 4    # 0-4 (0 = nenhuma)
  bloco_em_andamento: null   # null se nao tem bloco incompleto
  etapa_em_andamento: null   # fundamentar | guiar | validar | registrar
  blocos_status:
    bloco_1_identidade: "completo"      # pendente | em_andamento | completo
    bloco_2_icp: "completo"
    bloco_3_dor: "completo"
    bloco_4_diferencial: "completo"
    bloco_5_pacotes: "completo"
    bloco_6_posicionamento: "completo"
    bloco_7_meta: "completo"

# --- PERFIL DO BUILDER (snapshot) ---
builder:
  nome: "Lorenzi"
  serie_atual: "intermediario"          # iniciante | intermediario | avancado
  faturamento_mensal: 1700              # ultimo dado conhecido (R$)
  ticket_medio: 1300                    # ultimo ticket praticado (R$)
  horas_semana: 25
  competencias_chave:
    - "LP Figma + Elementor"
    - "Responsividade"
    - "Diagnostico de conversao"

# --- ESTADO DE CLIENTES ---
clientes:
  tem_clientes_ativos: true
  quantidade_ativos: 6                  # estimativa
  projetos_desde_ultimo_checkpoint: 0
  recorrencia_ativa: 0                  # numero de contratos recorrentes
  fonte_aquisicao: "indicacao + Instagram + networking"

# --- DECISOES-CHAVE (snapshot para acesso rapido) ---
decisoes:
  icp_resumo: "Negocios com oferta validada que investem em trafego pago — R$25k-100k/mes"
  dor_primaria: "Investe em trafego mas nao confia que a pagina converte"
  formula_diferencial: "Diagnostico antes de design + QA pre-publicacao + acompanhamento pos"
  posicionamento:
    frase_mae: "Voce ja paga pelo clique. Eu trabalho para ele nao virar desperdicio."
    bio_completa: |
      Voce ja paga pelo clique. Eu trabalho para ele nao virar desperdicio.
      Landing pages para quem ja investe em trafego e quer converter mais.
      Conheca meu portfolio: [link]
    data_definicao: "2026-08-21"
  precos:
    pacote_entrada:
      nome: "Diagnostico de Conversao"
      preco: 450
    pacote_principal:
      nome: "Estrutura de Conversao"
      preco: 2800
    pacote_premium:
      nome: "Funil de Conversao"
      preco: 4500
    recorrencia:
      nome: "Parceiro de Trafego"
      preco: 500
  meta_90_dias: 15000
  criterio_subida_preco: "Quando pegar novo cliente implica em prejudicar os que ja atende"

# --- HISTORICO DE PRECOS ---
historico_precos:
  - data: "2026-08-20"
    tipo: "definicao_inicial"
    pacote: "Estrutura de Conversao"
    preco_anterior: null
    preco_novo: 2800
    motivo: "Primeiro plano de negocio — ticket definido na Parede 3"
  - data: "2026-08-20"
    tipo: "definicao_inicial"
    pacote: "Parceiro de Trafego"
    preco_anterior: null
    preco_novo: 500
    motivo: "Recorrencia definida na Parede 3"

# --- HISTORICO DE EVOLUCAO ---
historico_evolucao:
  - data: "2026-08-20"
    tipo: "plano_criado"
    descricao: "Primeiro plano de negocio completo (v1)"
    serie: "intermediario"
    detalhes:
      faturamento: 1700
      ticket: 1300
      projetos_total: 11

# --- TAREFAS PENDENTES (snapshot de tarefas.md) ---
tarefas_pendentes:
  - descricao: "Converter 3 clientes existentes para Parceiro de Trafego"
    prioridade: "alta"
    prazo: "esta semana"
    origem: "bloco_7_meta"
  - descricao: "Fechar proximo projeto em R$2.800"
    prioridade: "alta"
    prazo: null
    origem: "bloco_5_pacotes"
  - descricao: "Atualizar bio do Instagram com novo posicionamento"
    prioridade: "media"
    prazo: null
    origem: "bloco_6_posicionamento"

# --- TIMESTAMPS ---
timestamps:
  plano_criado: "2026-08-20"
  ultima_sessao: "2026-08-21"
  proxima_revisao_sugerida: "2026-11-20"  # 90 dias apos criacao
  paredes:
    parede_1: "2026-08-20"
    parede_2: "2026-08-20"
    parede_3: "2026-08-20"
    parede_4: "2026-08-21"
  sessoes:
    - data: "2026-08-20"
      tipo: "primeira_passagem"
      blocos_trabalhados: [1, 2, 3, 4, 5]
      paredes_salvas: [1, 2, 3]
      resumo: "Construcao dos blocos 1-5, paredes 1-3 levantadas"
    - data: "2026-08-21"
      tipo: "primeira_passagem"
      blocos_trabalhados: [6, 7]
      paredes_salvas: [4]
      resumo: "Posicionamento e meta definidos, plano v1 completo"

# --- CONTEXTO PARA PROXIMA SESSAO ---
proxima_sessao:
  sugestao: "revisita"
  foco: "Validar ticket de R$2.800 e converter recorrencias"
  perguntas_para_abrir:
    - "Conseguiu fechar algum projeto no novo ticket?"
    - "Quantos clientes converteu para Parceiro de Trafego?"
    - "Como foi a reacao ao novo preco?"
```

---

## 5. INSTRUCOES PARA O SYSTEM PROMPT

O bloco abaixo deve ser inserido no `system-prompt.md` como nova secao (sugestao: entre a secao 3 "Fluxo de Construcao" e a secao 4 "Profundidade Adaptativa"):

```markdown
## MEMORIA PERSISTENTE

### O que e

Voce tem um arquivo de memoria persistente em `.builder/memory.yaml` que guarda
o estado do builder entre sessoes. Ele te permite retomar de onde parou, calibrar
sugestoes e acompanhar a evolucao do builder ao longo do tempo.

### Regra de ouro

A memoria NAO substitui os `_dados.yaml` dos blocos. Ela guarda SNAPSHOTS para
acesso rapido e HISTORICO de evolucao. Se precisar do dado completo de um bloco,
leia o `_dados.yaml` correspondente.

### No inicio de TODA sessao

1. **Leia `.builder/memory.yaml`.**
   - Se NAO existe: primeira sessao. Crie o arquivo ao final da primeira parede.
   - Se existe: retomada. Siga o fluxo abaixo.

2. **Monte o contexto de retomada:**
   - Identifique `progresso.ultimo_bloco_completo` e `progresso.ultima_parede_salva`.
   - Se ha `bloco_em_andamento` != null: o builder parou no meio. Retome daquela
     etapa exata (FUNDAMENTAR/GUIAR/VALIDAR/REGISTRAR). NAO refaca perguntas.
   - Se todos os blocos estao completos: e uma revisita. Use `proxima_sessao`
     para abrir a conversa.

3. **Leia `perfil.yaml` para confirmar serie.**
   Compare `memory.builder.serie_atual` com `perfil.yaml.serie_atual`. Se
   divergem, use o mais recente e atualize ambos.

4. **Verifique tarefas pendentes:**
   Liste `tarefas_pendentes` para o builder. Cobre execucao antes de avancar
   para novos blocos: "Na ultima sessao voce ficou de [X]. Conseguiu?"

5. **Saudacao com contexto:**
   ```
   E ai, [nome]! Vi que voce [resumo do estado].
   [Ultimo progresso: parede X levantada, bloco Y completo.]
   [Tarefas pendentes, se houver.]
   Quer [continuar de onde parou / revisar algo / atualizar com novos dados]?
   ```

### Durante a conversa

- **Calibre com `decisoes`:** Use `dor_primaria`, `formula_diferencial`,
  `frase_mae` para manter coerencia entre blocos. Sempre referencia decisoes
  anteriores ao construir novos blocos.

- **Calibre com `builder.serie_atual`:** A profundidade das perguntas, a
  complexidade dos pacotes e o nivel das sugestoes dependem da serie.

- **Calibre com `precos`:** Quando sugerir valores, use o historico de precos
  como ancora. Proximo degrau, nao salto.

- **Nao refaca perguntas:** Se a memoria indica que uma decisao ja foi tomada
  (ex: ICP definido), parta desse ponto. Pergunte se quer REVISAR, nao
  reconstruir do zero.

- **Detecte evolucao em tempo real:** Se o builder menciona dados novos
  (faturamento subiu, novos clientes, preco aumentou), registre mentalmente
  e atualize a memoria no proximo checkpoint.

### Nos checkpoints de parede

Ao salvar uma parede, TAMBEM atualize o memory.yaml:

1. Atualize `progresso` (ultimo bloco, ultima parede, status dos blocos).
2. Atualize `decisoes` com qualquer valor novo definido nesta sessao.
3. Se houve mudanca de serie, preco ou posicionamento:
   - Adicione entrada em `historico_evolucao`.
   - Se mudou preco: adicione em `historico_precos`.
4. Atualize `timestamps.paredes` com a data da parede salva.
5. Atualize `tarefas_pendentes` (novas tarefas geradas, tarefas concluidas).

### Ao encerrar a sessao

SEMPRE grave o memory.yaml ao encerrar, mesmo que nao tenha salvo parede:

1. Registre a sessao em `timestamps.sessoes`:
   ```yaml
   - data: "YYYY-MM-DD"
     tipo: "primeira_passagem | revisita"
     blocos_trabalhados: [numeros]
     paredes_salvas: [numeros]
     resumo: "1 frase do que aconteceu"
   ```

2. Se o builder parou no meio de um bloco:
   ```yaml
   progresso:
     bloco_em_andamento: 3  # numero do bloco
     etapa_em_andamento: "guiar"  # etapa exata
   ```

3. Atualize `proxima_sessao` com sugestao de foco:
   ```yaml
   proxima_sessao:
     sugestao: "continuar | revisita"
     foco: "Completar Bloco 3 (Dor) — parou na etapa GUIAR"
     perguntas_para_abrir:
       - "Pergunta especifica baseada no contexto"
   ```

4. Atualize `timestamps.ultima_sessao`.

### Em revisitas — Deteccao de evolucao

Quando o builder volta apos ter atendido clientes:

1. **Compare dados anteriores com novos:**
   - "Na ultima vez voce estava com ticket de R$[X]. E agora?"
   - "Voce disse que ia [tarefa]. Conseguiu?"

2. **Detecte gatilhos de mudanca de serie:**
   - Faturamento subiu consistentemente?
   - Numero de projetos entregues cresceu?
   - Confianca aumentou?
   - SE atingiu criterios da proxima serie: reclassifique e recalibre.

3. **Registre marcos de evolucao:**
   ```yaml
   historico_evolucao:
     - data: "YYYY-MM-DD"
       tipo: "mudanca_serie | aumento_ticket | meta_batida | reposicionamento"
       descricao: "Subiu de intermediario para avancado"
       serie: "avancado"
       detalhes:
         faturamento: 7000
         ticket: 4500
   ```

4. **Celebre avancos genuinos:**
   - "Lorenzi, quando voce comecou o plano seu ticket era R$1.300.
      Agora ta em R$2.800. Isso e evolucao real — feita fazendo, nao estudando."

### Conflito entre memoria e arquivos

Se memory.yaml diverge dos _dados.yaml (ex: memoria diz pacote = R$2.800 mas
pacotes/_dados.yaml diz R$3.200):

1. Os _dados.yaml sao a fonte da verdade para dados dos blocos.
2. Atualize o memory.yaml para refletir o estado real dos arquivos.
3. Se a divergencia indica uma mudanca que nao foi registrada:
   - Pergunte ao builder: "Vi que o preco do Estrutura de Conversao mudou
     de R$2.800 pra R$3.200. Voce ajustou? Como foi?"
   - Registre no historico de precos.
```

---

## 6. REGRAS DE INTEGRIDADE

### 6.1 Tamanho do arquivo

O memory.yaml nao deve crescer indefinidamente:

- `historico_precos`: manter ultimas 20 entradas. Apos 20, comprimir as mais
  antigas em 1 entrada resumo ("5 ajustes entre 2026-08 e 2027-02, ticket
  medio subiu de R$1.300 para R$3.500").

- `historico_evolucao`: manter ultimos 15 marcos. Consolidar marcos antigos.

- `timestamps.sessoes`: manter ultimas 10 sessoes. Consolidar anteriores em
  contagem ("12 sessoes anteriores entre 2026-08-20 e 2027-01-15").

- `tarefas_pendentes`: maximo 10 tarefas. Priorizar por relevancia. Tarefas
  muito antigas (>90 dias) sao arquivadas ou removidas com aviso ao builder.

### 6.2 Validacao na leitura

Ao ler o memory.yaml, o agente DEVE validar:

1. `versao_schema` e compativel (atualmente: 1).
2. `builder.nome` coincide com `perfil.yaml.nome`.
3. `builder.serie_atual` coincide com `perfil.yaml.serie_atual`.
4. Blocos marcados como "completo" tem seus _dados.yaml correspondentes.
5. Timestamps sao coerentes (ultima sessao nao e no futuro).

Se encontrar inconsistencia: corrige silenciosamente e registra a correcao.

### 6.3 Criacao do memory.yaml

O arquivo e criado na primeira vez que uma parede e salva (Parede 1).
Antes disso, o agente opera sem memoria persistente (sessao unica normal).

Se o builder ja tem arquivos de blocos mas NAO tem memory.yaml (caso de
migracao — plano foi construido antes do sistema de memoria existir):

1. Reconstituir o memory.yaml a partir dos arquivos existentes:
   - Ler perfil.yaml → popular `builder`
   - Ler cada _dados.yaml → popular `progresso` e `decisoes`
   - Marcar `tipo_sessao: "revisita"`
   - Registrar em `historico_evolucao`: "Memoria reconstituida a partir de arquivos existentes"

2. Informar o builder: "Criei seu arquivo de memoria com base no plano que
   voce ja tem. Agora vou lembrar de tudo entre sessoes."

---

## 7. DIAGRAMA DE FLUXO COMPLETO

```
┌─────────────────────────────────────────────────────┐
│                  INICIO DA SESSAO                   │
└──────────────────────┬──────────────────────────────┘
                       │
                       ▼
              ┌─────────────────┐
              │ memory.yaml     │
              │ existe?         │
              └───┬─────────┬───┘
                  │         │
                 SIM       NAO
                  │         │
                  ▼         ▼
          ┌───────────┐  ┌──────────────────┐
          │ Ler       │  │ Existem          │
          │ memoria   │  │ _dados.yaml?     │
          └─────┬─────┘  └──┬────────────┬──┘
                │            │            │
                │           SIM          NAO
                │            │            │
                │            ▼            ▼
                │    ┌──────────────┐  ┌────────────────┐
                │    │ Reconstituir │  │ Primeira sessao │
                │    │ memoria dos  │  │ Bloco 1         │
                │    │ arquivos     │  └────────┬───────┘
                │    └──────┬───────┘           │
                │           │                   │
                ▼           ▼                   │
          ┌──────────────────────┐              │
          │ Ler perfil.yaml     │              │
          │ Comparar memoria    │              │
          │ Verificar tarefas   │              │
          └──────────┬─────────┘              │
                     │                         │
                     ▼                         │
          ┌──────────────────────┐              │
          │ Saudacao com         │              │
          │ contexto de          │◄─────────────┘
          │ retomada             │
          └──────────┬───────────┘
                     │
                     ▼
          ┌──────────────────────┐
          │ CONVERSA             │
          │ (calibrada pela      │
          │  memoria)            │
          └──────────┬───────────┘
                     │
                     ▼
          ┌──────────────────────┐
          │ Checkpoint de        │──► Grava memory.yaml
          │ parede?              │    + _dados.yaml
          └──────────┬───────────┘    + README.md
                     │
                     ▼
          ┌──────────────────────┐
          │ FIM DA SESSAO        │──► Grava memory.yaml
          │                      │    (sempre, mesmo sem
          └──────────────────────┘     parede salva)
```

---

## 8. EXEMPLO DE RETOMADA COM MEMORIA

### Cenario: Builder volta 2 semanas depois

**Estado da memoria:**
```yaml
progresso:
  ultimo_bloco_completo: 7
  ultima_parede_salva: 4
decisoes:
  precos:
    pacote_principal:
      nome: "Estrutura de Conversao"
      preco: 2800
tarefas_pendentes:
  - descricao: "Converter 3 clientes para Parceiro de Trafego"
    prioridade: "alta"
timestamps:
  ultima_sessao: "2026-08-21"
```

**Comportamento do agente:**

```
MENTOR: E ai, Lorenzi! Faz 2 semanas que a gente levantou as 4 paredes
do teu plano v1.

Teu ticket ta em R$2.800 no Estrutura de Conversao, meta de R$15k em
90 dias, e voce ficou de converter 3 clientes para o Parceiro de Trafego.

Me conta: o que rolou desde a ultima vez?
- Fechou algum projeto no novo ticket?
- Converteu algum cliente pra recorrencia?
- Alguma coisa mudou no teu cenario?

[Espera resposta antes de sugerir qualquer coisa]
```

### Cenario: Builder parou no meio do Bloco 3

**Estado da memoria:**
```yaml
progresso:
  ultimo_bloco_completo: 2
  ultima_parede_salva: 1
  bloco_em_andamento: 3
  etapa_em_andamento: "guiar"
```

**Comportamento do agente:**

```
MENTOR: E ai, Lorenzi! Vi que voce parou no Bloco 3 — Dor e Problema.
A gente tava na parte de entender as frustracoes do seu ICP.

Ate agora voce definiu:
- ICP: Negocios com oferta validada, R$25k-100k/mes
- Serie: Intermediario

Vamos retomar. Eu ia te perguntar sobre as frustracoes mais comuns dos
seus clientes com o profissional anterior. Me conta: qual e a maior
reclamacao?

[Retoma da pergunta exata onde parou — NAO refaz Blocos 1 e 2]
```
