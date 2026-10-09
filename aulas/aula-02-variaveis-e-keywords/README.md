# Aula 02: Variáveis e keywords

Nesta aula peguei o teste da aula 1, que tinha tudo escrito direto nos passos, e comecei a organizar. Os locators foram para variáveis e os passos viraram keywords com nome no formato BDD, então o teste agora se lê quase como uma frase.

## O que foi estudado

- Seção `Variables` e como usar as variáveis nos passos
- Criar keywords próprias e nomeá-las no padrão BDD (`Dado que...`, `E...`, `Então...`)
- CSS Selector e XPath como alternativas de locator
- O que acontece quando o formulário é enviado com campos vazios (as mensagens de campo obrigatório, que viraram o segundo teste na aula 3)

## Testes feitos

Arquivo: `preenchimento_correto.robot`

| Caso de teste | O que valida |
|---|---|
| Verificar se ao preencher corretamente o formulário os dados são inseridos corretamente na lista e se um novo card é criado no time esperado | Preenche o formulário, cria o card e confere que o colaborador aparece no time de Programação |

Ainda não tem teardown: o navegador fica aberto no fim do teste. Isso é resolvido na aula seguinte.

## Como executar

1. Inicie o Organo (`npm start`, na pasta da aplicação).
2. Em outro terminal, na raiz do repositório:
```
robot --outputdir resultados aulas/aula-02-variaveis-e-keywords/preenchimento_correto.robot
```

## O que aprendi

- Variáveis deixam o teste mais fácil de manter: se um locator mudar, eu altero em um lugar só.
- Dar nomes no padrão BDD às keywords faz o teste ficar legível até para quem não conhece o Robot.
- Um mesmo elemento pode ser encontrado de formas diferentes (id, classe, CSS Selector ou XPath). Vale escolher o mais estável.
