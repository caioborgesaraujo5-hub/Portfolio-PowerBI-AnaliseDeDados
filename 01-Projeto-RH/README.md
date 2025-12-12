# 👥 Dashboard de Recursos Humanos: Acompanhamento Descritivo da Força de Trabalho

## 📄 1. Visão Geral do Projeto

Este projeto consiste em um Dashboard Descritivo de página única, desenvolvido para fornecer uma visão instantânea sobre a composição e distribuição da força de trabalho. O foco está em métricas chave de **remuneração e distribuição de funcionários** para dar suporte à gestão operacional de RH.

## 🎯 2. Problema de Negócio / Objetivo

* **Problema:** O RH necessita de uma ferramenta rápida para visualizar a distribuição salarial e de gênero, e para monitorar a frequência (faltas) por filial, de forma a identificar desvios e garantir a equidade na remuneração.
* **Objetivo:** Criar um painel que permita ao gestor:
    * Analisar a distribuição de Salários por Filial e Departamento.
    * Entender a proporção de funcionários por Gênero e Média de Idade.
    * Monitorar a incidência de Faltas por Filial para ações corretivas.

## 💾 3. Fonte dos Dados

* **Arquivo Fonte:** - Arquivo Fonte: base_analitica.xlsx
* **Conteúdo:** Tabela de Funcionários contendo Nome, Departamento, Filial, Salário, Gênero, Data de Nascimento e Registros de Faltas.

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

As seguintes métricas principais são exibidas no dashboard:

* **Total de Funcionários:** 21 (Exibido em destaque no topo).
* **Distribuição de Gênero:** Percentual e contagem de Masculino (MASC) e Feminino (FEM).
* **Média de Idade:** Média de idade para MASC e FEM.
* **Salário por Filial:** Soma total dos salários pagos em SP, RJ, MG e ES.
* **Total de Faltas:** Contagem de faltas por Filial.

## 🖼️ 6. Dashboard: Visualização do Resultado

O dashboard é composto por **uma página focada na descritiva da base de funcionários**.

* **Descrição da Página Única:**
    * **Filtros:** Possui filtros verticais à esquerda para NOME, FILIAL, CONTRATAÇÕES, DEMISSÕES, SEXO e QTDE FALTA.
    * **Visualizações:** Gráfico de Área para distribuição Salarial por Departamento, Gráficos de Coluna para Salário e Faltas por Filial, e gráficos de Rosca para Distribuição de Gênero e Idade.

## ✅ 7. Insights Gerados (Conclusão)

A análise inicial do dashboard revelou:

* **Foco Salarial:** O departamento de **Gerência** concentra a maior parte do Salário por Departamento, e a Filial de **SP** tem o maior Salário por Filial.
* **Faltas:** A Filial **RJ** possui o maior número de faltas (22), indicando um ponto de atenção para gestão de frequência.
* **Composição da Força de Trabalho:** A equipe tem um perfil predominantemente feminino (66,67%) e uma média de idade bem distribuída entre os gêneros.

## 🛠️ 8. Ferramentas Utilizadas

* **Power BI Desktop:** Excel, Power Query (M), Modelagem, DAX, Visualização,
