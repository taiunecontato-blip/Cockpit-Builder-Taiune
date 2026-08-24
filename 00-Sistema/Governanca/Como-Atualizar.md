# Como Atualizar

Quando este repo for usado como template, o clone do usuario pode receber
atualizacoes do repositorio oficial usando `upstream`.

Configurar uma vez:

```bash
git remote add upstream https://github.com/OWNER/cockpit-builder.git
```

Atualizar:

```bash
git fetch upstream
git merge upstream/main
```

Para reduzir conflitos, nao personalize areas admin-owned. Coloque dados e
customizacoes em areas user-owned.

