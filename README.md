# Case Monks - Auditoria de Qualidade de Dados

Este projeto implementa uma auditoria sobre a planilha `opps_corrupted.xlsx`, identificando problemas de qualidade, aplicando correcoes e gerando entregaveis finais para analise.

## Objetivo

O notebook [`notebooks/audit.ipynb`](./notebooks/audit.ipynb) foi criado para:

- identificar problemas de qualidade na planilha original
- corrigir os registros dentro do escopo da analise
- gerar uma versao limpa da planilha
- produzir um relatorio HTML em linguagem natural, voltado para publico nao tecnico

## Estrutura do projeto

```text
caseMonks/
|-- data/
|   `-- opps_corrupted.xlsx
|-- notebooks/
|   `-- audit.ipynb
|-- output/
|   |-- opps_corrigido.xlsx
|   `-- relatorio_erros.html
`-- README.md
```

## Regras aplicadas na auditoria

O notebook segue as orientacoes do case:

- considera apenas oportunidades com `Type` em:
  - `Project - Competitive`
  - `Project - Not Competitive`
  - `Change Order/Upsell`
- respeita a granularidade por produto, evitando contar linhas como se fossem oportunidades unicas
- corrige inconsistencias em `Stage`, `Lead_Source` e `Lead_Office`
- cria a coluna `Lead_Source_Category` com a taxonomia pedida
- recalcula `Amount` com base na soma de `Total_Product_Amount` quando houver divergencia
- padroniza `Amount` e `Total_Product_Amount` como `float`
- preserva oportunidades em estagios iniciais sem valor/produto como casos esperados

## Entregaveis

Ao executar o notebook, sao gerados:

- [`output/opps_corrigido.xlsx`](./output/opps_corrigido.xlsx)
- [`output/relatorio_erros.html`](./output/relatorio_erros.html)

## Como executar

1. Ative o ambiente virtual.
2. Abra e execute o notebook `notebooks/audit.ipynb`.
3. Os arquivos finais serao gerados na pasta `output/`.

Se preferir executar o conteudo do notebook por script, basta rodar as celulas com Python em um ambiente que tenha `pandas` e suporte a leitura/escrita de Excel.

## Saida esperada

O relatorio HTML inclui:

- resumo executivo
- quantidade de problemas por categoria
- exemplos reais encontrados na base
- explicacao simples do problema
- descricao do que foi corrigido

## Observacoes

- A pasta `output/` contem artefatos gerados automaticamente.
- A pasta `.venv/` e arquivos auxiliares do Jupyter nao fazem parte da logica do projeto.
