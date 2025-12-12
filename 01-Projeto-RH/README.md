# 📈 Dashboard de Desempenho de Vendas: Análise de E-commerce

## 📄 1. Visão Geral do Projeto

Este projeto foca em **desempenho comercial**, oferecendo uma análise detalhada das métricas de vendas, faturamento e lucratividade de uma operação de E-commerce. O objetivo é permitir que a equipe comercial tome decisões baseadas em dados sobre a performance de produtos, regiões e canais de venda.

## 🎯 2. Problema de Negócio / Objetivo

* **Problema:** A empresa precisa identificar seus produtos/regiões de maior e menor desempenho para otimizar o estoque, direcionar campanhas de marketing e melhorar a margem de lucro.
* **Objetivo:** Criar um dashboard que responda a perguntas como:
    * Qual é a nossa **taxa de crescimento** (YoY - Year over Year)?
    * Quais são os **Top 5 Produtos** em faturamento e lucro?
    * Como o desempenho de vendas se distribui geograficamente?

## 💾 3. Fonte dos Dados

* **Arquivo Fonte:** [Descreva o arquivo, ex: `vendas_e_produtos.csv`]
* **Conteúdo:** Tabela de Fatos de Vendas (Data, Produto ID, Quantidade, Valor) e Tabelas Dimensão (Produtos, Clientes, Tempo/Calendário).

## ⚙️ 4. Transformação e Modelagem de Dados (ETL)

Considerando a natureza dos dados descritivos, o foco do ETL foi garantir a **qualidade e integridade** para os cálculos de Salário e Faltas.

1.  **Transformação (Power Query - Linguagem M):**
    * **Limpeza e Tratamento:** Garantia de que não havia valores nulos (`null`) nas colunas críticas (Salário, Filial e Chaves de Identificação).
    * **Tipagem de Dados:** Conversão correta de colunas, como garantir que Salário estivesse em formato numérico e datas no formato `Date`.
    * **Enriquecimento:** Criação de colunas auxiliares (ex: Mês/Ano para a data de admissão, ou Idade a partir da data de nascimento).
2.  **Modelagem Dimensional (Power BI Desktop):**
    * **Estrutura:** Modelo simples, geralmente com uma tabela Fato principal de Funcionários/Movimentações e a criação de uma Tabela Dimensão de Tempo (Date Table) para permitir análise temporal por ano/mês.
    * **Relações:** Criação e validação de relações 1:N (Um para Muitos) para garantir a correta propagação dos filtros.
    
## 💡 5. Principais Métricas (KPIs) e DAX

* **Faturamento Total**
* **Crescimento Anual (YoY):** $\text{Vendas Ano Atual} / \text{Vendas Ano Anterior} - 1$
* **Margem de Lucro Bruta:** $\text{Lucro} / \text{Faturamento}$
* **Ticket Médio:** $\text{Faturamento} / \text{Número de Pedidos}$

## 🖼️ 6. Dashboard: Visualização do Resultado

O dashboard é composto por **uma página focada na descritiva da base de funcionários**.

## ✅ 7. Insights Gerados (Conclusão)

(Será preenchida após a análise do dashboard).

## 🛠️ 8. Ferramentas Utilizadas

* **Power BI Desktop:** Modelagem, DAX, Visualização.
