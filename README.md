![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=flat-square&logo=python&logoColor=white)
![Machine Learning](https://img.shields.io/badge/Machine_Learning-Scikit_Learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/Model-XGBoost-1db954?style=flat-square)
![Status](https://img.shields.io/badge/Status-Concluído-success?style=flat-square)

# Detecção de Anomalias em Transações (Fraudes)

## Resumo Executivo
Este projeto foi desenvolvido como parte do Bootcamp da **Digital Innovation One (DIO)**. O objetivo é estabelecer um pipeline completo de Machine Learning para identificar transações fraudulentas em cartões de crédito. 

O grande desafio deste cenário é o **alto desbalanceamento dos dados** (fraudes representam uma fração minúscula das transações totais). Para resolver isso, o projeto implementa técnicas avançadas de balanceamento e modelagem, culminando em uma camada de explicabilidade para justificar as decisões do algoritmo.

## Contexto de Negócio
Instituições financeiras perdem bilhões anualmente devido a fraudes em cartões de crédito. Um modelo de detecção eficaz precisa de um framework duplo:
1. **Alto Recall para Fraudes:** Minimizar Falsos Negativos (deixar uma fraude passar é o pior cenário financeiro).
2. **Explicabilidade:** Entender *por que* o modelo bloqueou uma transação é crucial para auditoria e atendimento ao cliente.

## Arquitetura Técnica
O fluxo de trabalho implementa o seguinte pipeline de processamento:

1. **Coleta e Pré-processamento (ETL):**
   * Importação do dataset histórico de transações.
   * Padronização de features contínuas utilizando `StandardScaler`.
2. **Engenharia de Dados e Balanceamento:**
   * Divisão estratificada entre treino e teste.
   * Aplicação de **SMOTE (Synthetic Minority Over-sampling Technique)** para gerar exemplos sintéticos da classe minoritária (fraudes) no conjunto de treino.
3. **Motor de Inferência (Modelagem):**
   * Treinamento de um modelo avançado baseado em árvores de decisão: **XGBoost Classifier**.
4. **Avaliação e Explicabilidade:**
   * Avaliação focada em métricas de negócio (Precision, Recall e F1-Score).
   * Implementação da biblioteca **SHAP (SHapley Additive exPlanations)** para extrair a importância de cada variável na tomada de decisão do modelo.

## Pré-requisitos do Projeto
Para replicar este ambiente, são necessárias as seguintes dependências:
* Ambiente Python 3.10+
* Bibliotecas: `pandas`, `numpy`, `scikit-learn`, `imbalanced-learn`, `xgboost`, `shap`, `matplotlib`, `seaborn`.

## Instruções de Uso
1. Clone o repositório: `git clone https://github.com/seixobr/deteccao-anomalias-transacoes.git`
2. Instale as dependências via pip.
3. Execute o notebook `deteccao_anomalias_transacoes.ipynb` em um ambiente Jupyter ou Google Colab.

## Aviso Legal (Disclaimer)
Este software foi desenvolvido estritamente para **fins educacionais** e de portfólio. O sistema fornece uma avaliação baseada em dados históricos anonimizados e não constitui um sistema de produção pronto para bloqueio real de transações bancárias.
