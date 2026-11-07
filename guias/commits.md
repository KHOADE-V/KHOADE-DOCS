# Mensagens de commit

Um bom histórico responde "o que mudou e por quê" sem precisar abrir o código.

## Estrutura

```
<tipo>: <resumo curto no imperativo>

<corpo opcional: explica o porquê, não o como>
```

- **Resumo** com até uns 50 caracteres, sem ponto final.
- **Imperativo**: "Adiciona login", não "Adicionado login" nem "Adicionei login".
- **Corpo** separado do resumo por uma linha em branco. Use para explicar a motivação e efeitos colaterais.

## Tipos mais usados

| Tipo | Quando usar |
| --- | --- |
| `feat` | Funcionalidade nova |
| `fix` | Correção de bug |
| `docs` | Só documentação |
| `refactor` | Reorganiza o código sem mudar o comportamento |
| `test` | Cria ou ajusta testes |
| `chore` | Tarefas de manutenção (dependências, configuração) |

## Exemplos

Bom:

```
fix: impede divisão por zero no cálculo da média

Listas vazias causavam ZeroDivisionError ao gerar o relatório.
Agora a função devolve 0 nesse caso.
```

```
feat: adiciona comando /dado ao bot
```

Ruim:

```
mudanças
arrumei umas coisas
asdf
```

## Teste rápido

Complete a frase: "Se aplicado, este commit **vai** ___". Se a frase fizer sentido ("... corrigir a divisão por zero"), a mensagem está boa.

## Dicas

- Um commit, uma ideia. Se o resumo precisa de "e", talvez sejam dois commits.
- Referencie issues no corpo: `Fecha #12`.
- Não coloque dados sensíveis na mensagem: ela fica no histórico para sempre.
