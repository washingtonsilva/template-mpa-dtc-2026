# Template do projeto — MPA DTC 2026

Este repositório é o ponto de partida para o projeto individual da disciplina **Documentos Técnicos e Científicos com Quarto e LaTeX**, do Mestrado Profissional em Administração do IFMG Campus Formiga.

O template oferece uma estrutura inicial simples e comum a toda a turma. A partir da Aula 3, o mesmo repositório será ampliado à medida que cada tipo de documento for estudado. Isso mantém fontes e resultados organizados, facilita o uso de caminhos relativos e evita a criação de um projeto diferente para cada aula.

No GitHub, use este template para criar um repositório público denominado `mpa-dtc-2026-nome-sobrenome`. Substitua `nome-sobrenome` pelo seu primeiro nome e último sobrenome, em letras minúsculas, sem espaços e sem acentos.

Se esse repositório já existir e contiver somente arquivos da configuração inicial, siga a orientação da Aula 3 para substituí-lo pelo projeto criado a partir do template. Se houver qualquer trabalho produzido por você, não exclua o repositório nem sua pasta local: consulte o professor antes de continuar.

## O que é um projeto Quarto?

Um projeto Quarto é uma pasta que reúne documentos e recursos relacionados sob uma configuração comum. Ele permite compartilhar opções entre documentos e renderizar um arquivo, uma pasta ou o projeto inteiro. A [documentação oficial do Quarto](https://quarto.org/docs/projects/quarto-projects.html) apresenta essas funções e as demais possibilidades dos projetos.

Neste template, a mesma pasta terá três funções relacionadas, mas distintas:

| Elemento | Função |
|---|---|
| Repositório Git | Registra o histórico dos arquivos e permite compartilhá-los pelo GitHub. |
| Projeto Quarto | Organiza e renderiza os documentos conforme as configurações do `_quarto.yml`. |
| Projeto RStudio | Permite que o RStudio trate a pasta como uma unidade de trabalho depois que o programa criar o arquivo `.Rproj` individual. |

### O que é o arquivo `_quarto.yml`?

O `_quarto.yml`, localizado na raiz, é o arquivo de configuração do projeto Quarto. O Quarto reconhece esse nome específico; por isso, o arquivo não deve ser renomeado. Sua extensão `.yml` indica que ele utiliza YAML, um formato de texto estruturado e legível por pessoas, frequentemente empregado em arquivos de configuração. YAML significa *YAML Ain't Markup Language*, conforme a [especificação oficial](https://yaml.org/spec/1.2.2/).

No YAML, os dois-pontos separam uma opção de seu valor, e a indentação indica quais opções estão subordinadas a outras. Por isso, os espaços no início das linhas fazem parte da estrutura do arquivo; não use a tecla Tab para indentar.

Neste template, o `_quarto.yml` começa com:

```yaml
project:
  type: default
  execute-dir: project

lang: pt-BR

editor: source
```

Essa configuração informa ao Quarto que:

- `type: default` define um projeto padrão, voltado inicialmente à produção de documentos;
- `execute-dir: project` faz o código usar a raiz do projeto como diretório de trabalho; por isso, os caminhos fornecidos na disciplina começam nessa raiz;
- `lang: pt-BR` define o português do Brasil como idioma principal;
- `editor: source` indica a preferência pelo editor de código-fonte do arquivo `.qmd`.

O `_quarto.yml` contém configurações compartilhadas pelo projeto. Já o bloco YAML delimitado por `---` no início de um arquivo `.qmd` contém metadados e opções específicas daquele documento.

## Estrutura inicial

```text
mpa-dtc-2026-nome-sobrenome/
├── .gitignore
├── README.md
└── _quarto.yml
```

| Caminho | Papel no projeto |
|---|---|
| `.gitignore` | Evita o versionamento de caches, arquivos temporários, credenciais e configurações locais do RStudio, do macOS e do Windows. |
| `README.md` | Explica a finalidade, a estrutura e as convenções do projeto. |
| `_quarto.yml` | Define a raiz como um projeto Quarto e estabelece opções comuns aos documentos. |

## Primeira ampliação na Aula 3

Na Aula 3, cada estudante criará a pasta `dados/`, salvará nela o CSV fornecido
e criará o primeiro documento Quarto em `relatorios/01-relatorio/`:

```text
mpa-dtc-2026-nome-sobrenome/
├── dados/
│   └── dados-vendas.csv
└── relatorios/
    └── 01-relatorio/
        └── relatorio.qmd
```

Essa ampliação não vem pronta no template porque criar as pastas, salvar o dado
fornecido e criar o documento fazem parte da prática da aula. O Git também não
registra pastas vazias; uma pasta passa a integrar o repositório quando recebe
um arquivo.

A extensão `.qmd` identifica um documento Quarto Markdown. Esse arquivo é a fonte editável: ele pode reunir cabeçalho YAML, texto em Markdown e código R. Durante a renderização, o código é executado e seus resultados são incorporados às saídas. Alterações de conteúdo devem ser feitas no `.qmd`, não diretamente nos arquivos gerados.

O primeiro documento será renderizado em HTML. A mesma fonte também permitirá
comparar as saídas PDF e Word. A fonte e os arquivos gerados permanecerão em
`relatorios/01-relatorio/`; o dado compartilhado pelo projeto ficará em
`dados/dados-vendas.csv`.

## Convenções de organização

- Cada relatório deve ficar em uma subpasta própria de `relatorios/`.
- O prefixo numérico com zero à esquerda indica a ordem: `01-`, `02-`, `03-`.
- O número pertence ao nome da subpasta; dentro dela, a fonte mantém o nome descritivo `relatorio.qmd`.
- Nomes de arquivos e pastas usam letras minúsculas, sem acentos e com hífens no lugar de espaços.
- Dados compartilhados por documentos do projeto ficam em `dados/`, na raiz.
- Imagens e outros recursos exclusivos de um relatório ficam na subpasta correspondente.
- Na Aula 3, `dados/` não possui subpastas. `dados/brutos/` e
  `dados/derivados/` serão criadas somente quando tiverem função concreta.
- Pastas e arquivos novos serão acrescentados somente quando tiverem uma função concreta na disciplina.

## Evolução do projeto

- **Aula 3:** primeiro documento Quarto renderizado em HTML e comparação com as saídas PDF e Word.
- **Aula 4:** relatório técnico reprodutível, dados preservados, referências e identidade visual com `_brand.yml`.
- **Aula 5:** versões parametrizadas do relatório técnico.
- **Aula 6:** apresentação produzida com Quarto.
- **Aula 7:** criação do blog, configuração do website e publicação com GitHub Pages.

A estrutura de blog não faz parte do template inicial. Arquivos como `index.qmd`, `about.qmd` e `.nojekyll`, além das pastas `posts/` e `docs/`, serão criados somente na Aula 7.

## Projeto RStudio

O template não contém arquivo `.Rproj`, porque ele pertence ao RStudio e seu nome deve acompanhar o repositório individual. Ao clonar o repositório por **File → New Project → Version Control → Git**, o RStudio criará `mpa-dtc-2026-nome-sobrenome.Rproj` na raiz. Se o repositório já estiver clonado, use **File → New Project → Existing Directory** e selecione essa mesma raiz. O arquivo `.Rproj` individual pode ser versionado normalmente.

A raiz do repositório deve ser também a raiz do projeto Quarto e do projeto RStudio. Não crie outra pasta envolvendo o projeto.

## Cuidados com o repositório público

Publique somente dados e documentos autorizados. Credenciais, dados pessoais, sigilosos ou sujeitos a restrições de uso não devem ser adicionados ao Git.

O `.gitignore` ajuda a impedir o rastreamento inicial de arquivos previstos em suas regras, mas não protege um arquivo que já tenha sido adicionado ao Git. Antes de cada `commit`, confira os arquivos que serão publicados.

Os projetos da AP1, da AP2 e do miniartigo permanecem privados no Overleaf e não fazem parte deste repositório.
