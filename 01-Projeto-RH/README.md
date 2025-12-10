# 📊 Projeto 01: Análise e Gestão de Recursos Humanos (RH)

## 🎯 Contexto e Objetivo de Negócio
O objetivo deste projeto era fornecer à área de RH uma visão clara e instantânea dos indicadores-chave (KPIs) de pessoal para tomar decisões estratégicas sobre contratações e retenção.
* **Problema Principal:** Medir a taxa de Rotatividade (Turnover) de forma consistente e identificar os departamentos com maior índice.
* **Solução:** Desenvolvimento de um dashboard em Power BI com medidas de Time Intelligence.

## 🛠️ Modelagem e Tratamento de Dados
Para este projeto, utilizei um modelo de dados simples, mas robusto:
* **Fontes:** Dados de Funcionários (Dimensão) e Tabela de Movimentação (Fatos - Entradas/Saídas).
* **Modelagem:** Estrutura Star Schema com relacionamento 1 para Muitos (1:N) entre a Tabela Calendário e a Tabela de Fatos.
* **DAX Crucial:** Para o cálculo de *Turnover*, utilizamos a função `CALCULATE` combinada com funções de agregação, garantindo precisão:
  ```dax
  Turnover Mensal = 
  DIVIDE(
      COUNTROWS(
          FILTER('Fato Movimentacao', 'Fato Movimentacao'[Tipo] = "Saída")
      ), 
      AVERAGEX(
          ALLSELECTED('Dimensao Funcionario'), 
          [Headcount Atual] 
      )
  )
