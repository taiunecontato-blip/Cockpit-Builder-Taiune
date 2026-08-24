# Cockpit Builder

Ambiente operacional duplicavel para comunidades Builder.

Este repositorio nao e um app. Ele e uma estrutura de pastas, regras e memoria
para organizar Sistema, Obra, Construtor, Apps e Memoria.

## Skill incluida

O template ja vem com a skill `plano-de-negocio` instalada em
`.claude/skills/plano-de-negocio/` e documentada em
`00-Sistema/Skills/Plano-de-Negocio/`.

Ela cria os artefatos do usuario em `10-Obra/Plano-de-Negocio/`.

## Estrutura

```txt
00-Sistema/      # governanca, cartorio, skills, agentes e SOPs oficiais
10-Obra/         # negocio/projeto do usuario
20-Construtor/   # estudos e desenvolvimento pessoal
30-Apps/         # apps e interfaces conectadas ao ambiente
40-Memoria/      # memoria do usuario/comunidade
```

## Comecar

Leia nesta ordem:

1. `AGENTS.md`
2. `CLAUDE.md`
3. `00-Sistema/Governanca/Como-Comecar.md`
4. `00-Sistema/Governanca/Propriedade-das-Pastas.md`

## Atualizar

Este repo foi pensado para ser usado como template. O usuario clona, preenche
as areas user-owned e puxa atualizacoes das areas admin-owned quando houver nova
versao oficial.

