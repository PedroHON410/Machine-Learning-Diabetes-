# Classificação e Predição de Diabetes com Machine Learning

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Latest-orange.svg)
![Status](https://img.shields.io/badge/Status-Em%20Desenvolvimento-green.svg)

Este projeto consiste no desenvolvimento e avaliação de modelos de Machine Learning (Aprendizado de Máquina) para classificar e prever se uma paciente possui ou não diabetes, com base em medições diagnósticas clínicas.

##  Objetivo do Projeto
O principal objetivo é construir um classificador preditivo robusto. O projeto define como meta de sucesso a validação do modelo caso este atinja ou supere **95% de acurácia/precisão** nas previsões.

##  Sobre a Base de Dados
A base de dados utilizada é composta por registros de pacientes do sexo feminino. Os atributos (features) clínicos avaliados são:

* **Pregnancies:** Número de gestações da paciente.
* **Glucose:** Concentração de glicose plasmática após 2 horas em um teste oral de tolerância à glicose.
* **BloodPressure:** Pressão arterial diastólica (mm Hg).
* **SkinThickness:** Espessura da prega cutânea do tríceps (mm).
* **Insulin:** Insulina sérica após 2 horas (µU/ml).
* **BMI (IMC):** Índice de massa corporal (peso em kg / (altura em m)²).
* **DiabetesPedigreeFunction:** Função de pedigree do diabetes (calcula a probabilidade de desenvolver a doença com base no histórico familiar).
* **Age:** Idade (em anos).
* **Outcome (Alvo):** Classe binária onde `0` indica "Não possui a doença" e `1` indica "Possui a doença".

## Tecnologias e Bibliotecas Utilizadas
* **Python** (Linguagem base)
* **Pandas & NumPy:** Manipulação, limpeza e tratamento de dados.
* **Matplotlib & Seaborn:** Visualização de dados e análise exploratória.
* **Scikit-Learn (Sklearn):** * Divisão de dados (`train_test_split`).
    * Padronização de features (`StandardScaler`).
    * Algoritmos de Classificação: *Logistic Regression*, *K-Neighbors Classifier (KNN)*, e *Random Forest Classifier*.
    * Otimização de Hiperparâmetros (`GridSearchCV` e `RandomizedSearchCV`).
    * Métricas de Avaliação (`ConfusionMatrixDisplay`, `RocCurveDisplay`, `classification_report`).

##  Etapas do Desenvolvimento

### 1. Tratamento de Dados (Data Cleaning)
Identificou-se que valores iguais a `0` em atributos como *Glucose, BloodPressure, SkinThickness, Insulin* e *BMI* representavam, na verdade, dados faltantes (NaN). 
* Os valores `0` foram substituídos pela **média** de cada respectiva coluna.
* Os dados tratados foram devidamente convertidos para os tipos numéricos adequados (`int64`).

### 2. Análise Exploratória (EDA)
Foram geradas visualizações para compreender o comportamento dos dados, incluindo:
* Distribuição da variável alvo (`Outcome`).
* Análise de correlação cruzada entre o número de gestações (`Pregnancies`) e a incidência da doença.
* Dispersão comparativa relacionando a Idade e o Número de Gestações com a detecção de diabetes.

### 3. Modelagem e Treinamento
Os dados foram separados em conjuntos de treino e teste. Foram testados e tunados diferentes algoritmos de classificação para buscar a melhor performance em direção à meta estabelecida.
