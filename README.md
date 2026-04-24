# 📊 Case Técnico — Operations (Monks)

## 📌 Visão Geral

Este projeto tem como objetivo realizar a **auditoria, limpeza e análise de dados de oportunidades comerciais**, simulando um cenário real de atuação em RevOps.

A base fornecida contém **413 registros em nível de produto**, o que exige tratamento para consolidar corretamente as oportunidades e garantir análises confiáveis.

---

## 🎯 Objetivo

- Identificar problemas de qualidade nos dados
- Corrigir inconsistências estruturais e semânticas
- Garantir confiabilidade da base
- Gerar insights relevantes para o negócio

---

## ⚙️ Abordagem

### 🧪 1. Preparação do ambiente

Foram utilizadas as seguintes bibliotecas:

- `pandas` → manipulação de dados
- `numpy` → suporte numérico
- `matplotlib` / `seaborn` → visualização
- `openpyxl` → leitura/escrita Excel

O desenvolvimento foi realizado em **Jupyter Notebook**, permitindo análise iterativa e validação contínua.

---

### 🧠 2. Planejamento

Antes da implementação:

- Estudei boas práticas atuais de **Data Cleaning**
- Estruturei o problema em **etapas menores**
- Defini regras baseadas no contexto do case

---

### 🤖 3. Uso de IA

A IA foi utilizada como **ferramenta de apoio**, não como solução final:

- Estruturação inicial do código
- Sugestão de abordagens
- Comparação entre diferentes soluções

✔️ Todas as saídas foram:

- validadas manualmente
- testadas com dados reais
- ajustadas conforme necessário

---

## 🔍 Auditoria dos Dados

Foram identificados diversos problemas de qualidade:

### 🔁 Duplicação de registros

- A base está em nível de produto
- Uma mesma oportunidade aparece em múltiplas linhas

👉 Impacto:

- Superestimação do número de oportunidades
- Distorção de métricas de receita

---

### 💰 Divergência de valores

- Inconsistência entre:
  - `Amount`
  - soma de `Total_Product_Amount`

👉 Regra aplicada:

> A soma dos produtos foi considerada como fonte da verdade

---

### 🔢 Problemas em dados numéricos

- Valores armazenados como texto
- Formatação inconsistente

👉 Exemplo:

- números com caracteres inválidos

---

### 🔤 Inconsistência em campos categóricos

Foram encontrados erros de digitação e variações como:

- `Closed Wonn`
- `Clossed Won`

👉 Impacto:

- Quebra de agrupamentos
- Erros em análises por estágio

---

### 🚫 Dados fora do escopo

- Registros com `Type` não permitido pelo case

👉 Ação:

- Remoção desses registros

---

## 🧼 Limpeza e Padronização

As seguintes ações foram realizadas:

- Conversão de `Amount` e `Total_Product_Amount` para `float`
- Correção de valores inconsistentes
- Padronização de textos (trim + normalização)
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

---

### 🎯 Performance por Lead Source

- Diferença entre volume de leads e taxa de conversão

---

### 🏆 Top oportunidades e clientes

- Identificação de oportunidades de alto valor
- Análise de concentração de receita

---

### 🔄 Pipeline

- Distribuição por estágio
- Identificação de possíveis gargalos

---

### ⏱️ Ciclo de vendas

- Tempo médio entre criação e fechamento
- Diferença entre escritórios

---

## 📦 Entregas

- `opps_corrigido.xlsx`  
  → Base limpa e confiável

- `relatorio_erros.html`  
  → Detalhamento dos problemas encontrados

- `analise.html`  
  → Dashboard com visualizações e insights

- `apresentacao.pdf`  
  → Síntese executiva para stakeholders

---

## 💡 Principais Aprendizados

- Dados brutos raramente estão prontos para análise
- Pequenos erros (ex: digitação) geram grande impacto
- A etapa de limpeza é crítica em qualquer análise
- IA acelera o processo, mas exige validação rigorosa

---

## 🚀 Recomendações

Para evitar problemas futuros:

- Implementar validações no CRM (campos obrigatórios)
- Utilizar listas controladas (dropdowns)
- Criar alertas para inconsistência de valores
- Monitorar qualidade dos dados continuamente

---

## 🏁 Conclusão

Este projeto reforça a importância de unir:

- engenharia de dados
- análise crítica
- entendimento de negócio

para transformar dados inconsistentes em **insights confiáveis e acionáveis**.
