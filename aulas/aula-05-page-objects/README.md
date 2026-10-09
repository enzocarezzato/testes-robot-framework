# Aula 05: Page Objects

Última aula do curso. Até aqui eu copiava variáveis e keywords de um arquivo de teste para o outro. Com o Page Object Model (POM) separei a lógica da página dos testes, e os dois arquivos de teste passaram a usar o que está centralizado.

## O que foi estudado

- O que é o Page Object Model e por que ele ajuda na manutenção
- Separar o projeto em `resources` (lógica) e `testes` (cenários)
- Uma página do sistema como se fosse uma "classe": a página de cadastro do Organo concentra os elementos e as ações
- Arquivo `main.robot` que reúne as bibliotecas e os recursos do projeto

## Estrutura

O código desta aula é o projeto que fica na raiz do repositório, nas pastas `resources/` e `testes/`:

```
resources/
├── main.robot                  # bibliotecas e imports de todo o projeto
├── pages/
│   └── cadastro.robot          # variáveis e keywords da página de cadastro
└── shared/
    └── setup_teardown.robot    # abrir e fechar o navegador
testes/
├── preenchimento_correto.robot
└── preenchimento_incorreto.robot
```

Os testes ficaram só com os cenários. Variáveis e keywords estão em `resources/pages/cadastro.robot`.

## Testes feitos

São os mesmos 4 testes da aula 4 e da aula 3, agora rodando a partir da pasta `testes/`:

| Arquivo | Testes |
|---|---|
| `preenchimento_correto.robot` | Criar um card, criar três cards no mesmo time e criar um card em cada time |
| `preenchimento_incorreto.robot` | Mensagens de campo obrigatório com o formulário vazio |

## Como executar

1. Inicie o Organo (`npm start`, na pasta da aplicação).
2. Em outro terminal, na raiz do repositório:
```
robot --outputdir resultados testes
```

## Resultado

Os 4 testes passaram, divididos nas duas suítes.

![Log da execução](../../docs/prints/log-aula-05-pom.png)

## O que aprendi

- Se um locator mudar na página, eu corrijo em um arquivo só (`cadastro.robot`) e todos os testes continuam funcionando.
- Separar a lógica dos testes deixa os cenários curtos, fáceis de ler e fáceis de acrescentar.
- Esse formato já deixa o projeto preparado para novas páginas: cada uma ganharia o seu arquivo em `resources/pages/`.
