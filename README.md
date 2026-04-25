# 📊 Case Técnico — Operations (Monks)

## 📌 Visão Geral

Este projeto apresenta a **auditoria, limpeza e análise de dados de oportunidades comerciais**, simulando um cenário real de atuação em **Revenue Operations (RevOps)**.

A base original contém **413 registros em nível de produto**, o que exige tratamento para consolidação correta das oportunidades e geração de análises confiáveis.

---

## 🎯 Objetivo

- Identificar problemas de qualidade nos dados
- Corrigir inconsistências estruturais e semânticas
- Garantir confiabilidade da base
- Gerar insights relevantes para o negócio

---

## ⚙️ Abordagem

A resolução do problema foi estruturada em etapas claras, combinando boas práticas de **Data Cleaning**, análise exploratória e validação contínua.

### 🧪 1. Preparação do ambiente

Foram utilizadas as seguintes bibliotecas:

- `pandas` → manipulação de dados
- `numpy` → suporte numérico
- `matplotlib` / `seaborn` → visualização
- `openpyxl` → leitura/escrita de Excel

O desenvolvimento foi realizado em **Jupyter Notebook**, permitindo análise iterativa.

---

### 🧠 2. Planejamento

Antes da implementação:

- Estudo de boas práticas de limpeza de dados
- Quebra do problema em etapas menores
- Definição de regras com base no contexto do case

---

### 🤖 3. Uso de IA

A IA foi utilizada como ferramenta de apoio para:

- Estruturação inicial do código
- Sugestão de abordagens
- Comparação entre soluções

Todas as saídas foram:

- Validadas manualmente
- Testadas com dados reais
- Ajustadas conforme necessário

---

## 🔍 Auditoria dos Dados

Durante a análise, foram identificados problemas relevantes:

### 🔁 Duplicação de registros

- Dados em nível de produto (não oportunidade)
- Uma mesma oportunidade aparece em múltiplas linhas

**Impacto:**

- Superestimação de oportunidades
- Distorção de métricas

---

### 💰 Divergência de valores

- Inconsistência entre `Amount` e soma de `Total_Product_Amount`

**Regra aplicada:**

> A soma dos produtos foi considerada como fonte da verdade

---

### 🔢 Problemas em dados numéricos

- Valores armazenados como texto
- Formatação inconsistente

---

### 🔤 Inconsistência em campos categóricos

Exemplos:

- `Closed Wonn`
- `Clossed Won`

**Impacto:**

- Quebra de agrupamentos
- Erros analíticos

---

### 🚫 Dados fora do escopo

- Registros com `Type` inválido para o case

**Ação:**

- Remoção dos dados

---

## 🧼 Limpeza e Padronização

Foram aplicadas as seguintes transformações:

- Conversão de `Amount` e `Total_Product_Amount` para `float`
- Correção de inconsistências financeiras
- Padronização textual (trim + normalização)
- Correção de erros de grafia
- Criação da coluna `Lead_Source_Category`
- Remoção de dados fora do escopo
- Consolidação da base em nível de oportunidade

---

## ✅ Validação

Após a limpeza, foram validados:

- Consistência dos valores financeiros
- Integridade das categorias
- Estrutura da base final
- Coerência das análises

---

## 📊 Análise dos Dados

Com a base tratada, foram gerados insights como:

### 📈 Receita ao longo do tempo (MoM)

- Identificação de concentração de receita em períodos específicos

### 🎯 Performance por Lead Source

- Comparação entre volume de leads e conversão

### 🏆 Top oportunidades e clientes

- Identificação de maiores contribuintes de receita

### 🔄 Pipeline de vendas

- Distribuição por estágio
- Identificação de gargalos

### ⏱️ Ciclo de vendas

- Tempo médio entre criação e fechamento
- Diferenças entre escritórios

---

## 📦 Estrutura do Projeto

```text
caseMonks/
|-- data/
|   └── opps_corrupted.xlsx
|-- notebooks/
|   └── audit.ipynb
|-- output/
|   ├── opps_corrigido.xlsx
|   └── relatorio_erros.html
|-- insights/
|   └── analise.html
└── README.md
```
