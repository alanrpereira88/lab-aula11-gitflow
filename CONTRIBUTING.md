# Guia de Contribuição

## Workflow adotado: Git Flow

### Fluxo para features (exercício desta aula)

```
develop → feature/nome → develop
```

1. Sempre crie feature a partir da `develop`
2. Trabalhe na sua branch
3. Merge de volta para `develop` com `--no-ff`
4. Delete a branch de feature após o merge

### Nomenclatura de branches

| Tipo | Padrão |
|------|--------|
| Feature | `feature/nome-sobrenome-descricao` |
| Release | `release/vX.Y` |
| Hotfix | `hotfix/descricao-curta` |

## Padrão de commits

Use [Conventional Commits](https://www.conventionalcommits.org/pt-br/):

```
<tipo>: <descrição curta em português>
```

| Tipo | Quando usar |
|------|-------------|
| `feat` | Nova funcionalidade ou adição de conteúdo |
| `fix` | Correção de algo errado |
| `docs` | Alteração apenas em documentação |
| `merge` | Commit de merge de branches |

## O que não fazer

- Não criar feature a partir da `main`
- Não fazer merge direto sem `--no-ff`
- Não commitar na `main` manualmente
- Não deletar a branch `develop`
