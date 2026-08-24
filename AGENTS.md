# AGENTS.md — Cockpit Builder

Instrucoes para agentes de IA trabalhando neste ambiente.

## Primer

Este repositorio e uma estrutura operacional duplicavel. Ele nao contem app,
backend, banco de dados ou build.

## Hierarquia

| pasta | propriedade | papel |
|---|---|---|
| `00-Sistema/` | admin-owned | governanca, cartorio, skills, agentes e SOPs oficiais |
| `10-Obra/` | user-owned | negocio/projeto do usuario |
| `20-Construtor/` | user-owned | estudos e desenvolvimento pessoal |
| `30-Apps/` | admin-owned | apps e interfaces conectadas ao ambiente |
| `40-Memoria/` | user-owned | memoria do usuario/comunidade |

## Regras

- Nao grave dados do usuario dentro de `00-Sistema/`.
- Nao grave dados oficiais dentro de `10-Obra/`, `20-Construtor/` ou
  `40-Memoria/`.
- Antes de mover conteudo entre areas, leia
  `00-Sistema/Governanca/Propriedade-das-Pastas.md`.
- Use numero apenas no primeiro nivel, salvo quando uma subpasta representar
  uma sequencia operacional real.
- Preserve arquivos existentes do usuario; memoria e obra pertencem ao clone.

## Commits

Use Conventional Commits em portugues:

- `feat:`
- `fix:`
- `docs:`
- `chore:`
- `refactor:`

