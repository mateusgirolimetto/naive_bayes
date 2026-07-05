# Naive Bayes - Predição de Diabetes

Este projeto implementa um modelo **Naive Bayes** em R para prever o diagnóstico de diabetes (`diagnosed_diabetes`) a partir de variáveis clínicas e sociodemográficas de um conjunto de dados de pacientes.

## 📋 Descrição

O script (`Naive_Bayes.Rmd`) realiza todo o pipeline de modelagem, desde o pré-processamento dos dados até a avaliação final do modelo:

1. **Carregamento e preparação dos dados** — leitura do dataset e conversão das variáveis categóricas em fatores (gênero, etnia, escolaridade, renda, status de emprego, tabagismo, histórico familiar, hipertensão, histórico cardiovascular, etc.).
2. **Divisão treino/validação/teste e padronização** — separação dos dados em treino (85%), validação (10%) e teste (5%), com padronização (z-score) das variáveis numéricas baseada nos parâmetros do treino.
3. **Seleção de hiperparâmetros** — busca em grade (*grid search*) testando combinações de `laplace` (suavização) e `usekernel` (estimativa de densidade via kernel), avaliadas por AUC na validação.
4. **Escolha do limiar de decisão** — seleção do threshold de classificação a partir da curva ROC, buscando sensibilidade mínima de 90%.
5. **Modelo final** — treinamento do modelo Naive Bayes com os melhores hiperparâmetros usando todo o conjunto de treino.
6. **Avaliação no conjunto de teste** — matriz de confusão e curva ROC/AUC para medir o desempenho final do modelo.

## 🛠️ Tecnologias e pacotes utilizados

- [R](https://www.r-project.org/)
- `readr` — leitura de dados
- `dplyr` — manipulação de dados
- `caret` — particionamento dos dados e matriz de confusão
- `naivebayes` — treinamento do modelo Naive Bayes
- `pROC` — curva ROC e cálculo de AUC
- `ggplot2` — visualização da curva ROC

## 👤 Autor

Mateus V Girolimetto
