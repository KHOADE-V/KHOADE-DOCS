# Git: o essencial

O Git guarda o histórico do seu projeto. Cada **commit** é uma foto do projeto naquele momento, e você pode voltar a qualquer uma delas.

## Configuração inicial (uma vez só)

```bash
git config --global user.name "Seu Nome"
git config --global user.email "voce@exemplo.com"
git config --global init.defaultBranch main
```

## O ciclo do dia a dia

```bash
git status                 # o que mudou?
git add arquivo.py         # escolhe o que entra no próximo commit
git commit -m "Corrige o cálculo do total"
git push                   # envia para o GitHub
git pull                   # traz as novidades do GitHub
```

Dica: use `git add -p` para escolher trechos do arquivo, não o arquivo inteiro.

## Começando um projeto

```bash
git init                                  # projeto novo, na sua máquina
git clone https://github.com/usuario/repo # copia um projeto que já existe
```

## Branches: trabalhar sem estragar o principal

```bash
git switch -c minha-ideia   # cria e entra numa branch nova
# ... edita, add, commit ...
git switch main
git merge minha-ideia       # junta o trabalho na main
git branch -d minha-ideia   # apaga a branch já integrada
```

## Desfazendo coisas

| Situação | Comando |
| --- | --- |
| Tirar um arquivo do `git add` | `git restore --staged arquivo` |
| Descartar mudanças ainda não commitadas num arquivo | `git restore arquivo` (**não tem volta**) |
| Refazer a mensagem do último commit (ainda não enviado) | `git commit --amend` |
| Desfazer um commit já enviado, sem reescrever o histórico | `git revert <hash>` |

## Olhando o histórico

```bash
git log --oneline --graph --decorate -15
git diff                # mudanças ainda não adicionadas
git diff --staged       # mudanças já adicionadas
```

## O que evitar

- `git push --force` em branch compartilhada: pode apagar o trabalho dos outros. Se precisar, use `--force-with-lease`.
- Commitar senhas, tokens e arquivos `.env`. Use o `.gitignore`. Se um segredo vazou, **troque o segredo**: apagar o commit não basta, o histórico já foi copiado.
- Commits gigantes com "várias coisas". Commits pequenos são mais fáceis de entender e de desfazer.

## Modelo de `.gitignore` básico

```
.env
__pycache__/
node_modules/
.DS_Store
```
