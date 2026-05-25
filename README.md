# Lab — Git Flow

**DevOps I · Aula 11.1 · Unidade 2**

---

## O que é Git Flow?

Git Flow é um modelo de branching com papéis bem definidos para cada tipo de branch. É indicado para projetos com ciclos de release planejados.

```
main     ──●──────────────────────────────●──  (somente releases estáveis)
            \                            /
develop  ────●──●──●──●──●──●──●──●──●──     (integração contínua)
                \         \
feature          ●──●──●   ●──●──●            (funcionalidades isoladas)
                          \
release                    ●──●               (preparação de release)
```

### Branches e seus papéis

| Branch | Papel |
|--------|-------|
| `main` | Código em produção — somente releases |
| `develop` | Branch de integração — base para features |
| `feature/*` | Uma funcionalidade por branch — criada a partir de `develop` |
| `release/*` | Preparação de versão — congelamento de features |
| `hotfix/*` | Correção urgente em produção — criada a partir de `main` |

---

## Exercício — Adicione seu perfil ao time

### Passo 1 — Clone o repositório

```bash
git clone git@github-univertix:alanrpereira88/lab-aula11-gitflow.git
cd lab-aula11-gitflow
```

### Passo 2 — Acesse a branch `develop`

```bash
git switch develop
git pull
```

> No Git Flow, **você nunca cria feature a partir da `main`**. A base é sempre a `develop`.

### Passo 3 — Crie sua feature branch

```bash
git switch -c feature/seu-nome-perfil
```

Exemplo: `feature/joao-silva-perfil`

### Passo 4 — Copie o template e preencha seu perfil

```bash
cp time/_template.md time/seu-nome.md
```

Edite `time/seu-nome.md` com suas informações reais.

### Passo 5 — Commits na feature branch

```bash
git add time/seu-nome.md
git commit -m "feat: adiciona perfil de [Seu Nome]"
```

Adicione pelo menos 2 commits (ex: adicione a seção de objetivos num commit, as tecnologias em outro).

### Passo 6 — Merge de volta para `develop`

```bash
git switch develop
git merge --no-ff feature/seu-nome-perfil -m "merge: integra perfil de [Seu Nome]"
git branch -d feature/seu-nome-perfil
git push origin develop
```

> O `--no-ff` é obrigatório no Git Flow — preserva o registro de quando a feature foi integrada.

---

## Observe o histórico

```bash
git log --oneline --graph --all
```

Você deve ver os commits da feature como um caminho separado que se junta ao `develop`.

---

## Entrega

- Print do `git log --oneline --graph --all` mostrando o merge da sua feature
- URL do repositório com o push em `develop`

---

## Estrutura do repositório

```
lab-aula11-gitflow/
├── README.md          ← você está aqui
├── CONTRIBUTING.md    ← regras de contribuição
├── docs/
│   └── sobre-o-projeto.md
└── time/
    ├── _template.md   ← copie este arquivo
    └── alan-pereira.md  ← exemplo do professor
```
