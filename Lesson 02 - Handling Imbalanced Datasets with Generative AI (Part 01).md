# Lesson 02 — Handling Imbalanced Datasets with Generative AI (Part 01)

## Overview

This lesson presents a practical case study on how **Generative Artificial Intelligence** can be applied to address one of the most common challenges in Machine Learning: **imbalanced datasets**.

Using a fraud detection scenario, the lesson demonstrates how a baseline classification model behaves under severe class imbalance and how **synthetic data generation** with Generative AI can be used to improve model performance.

---

## Choose the language

<details>
<summary><strong>English</strong></summary>

## Objective

The objective of this lesson is to demonstrate how **Generative AI** can support the correction of **imbalanced datasets**, particularly in fraud detection problems, by generating realistic synthetic data to enhance Machine Learning models.

---

## Problem Context: Fraud Detection and Data Imbalance

In fraud detection tasks, datasets are typically highly imbalanced:
- More than 99% of transactions are legitimate
- Less than 1% represent fraudulent activity

Traditional Machine Learning models, such as **Logistic Regression**, tend to become biased toward the majority class, resulting in poor fraud detection performance.

---

## Environment Setup

The practical implementation is carried out using **Google Colaboratory**, which provides:
- A cloud-based notebook environment
- No dependency on local machine resources
- Easy collaboration and sharing

### Libraries Used
- `google.generativeai`
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`

All required libraries are installed using `pip` when necessary.

---

## Dataset Description

The dataset used in this lesson is a **credit card transaction dataset**, originally provided by TensorFlow resources.

Key characteristics:
- 284,807 transactions
- 31 numerical features
- Target column: `class`
  - `0` → legitimate transaction
  - `1` → fraudulent transaction

---

## Exploratory Data Analysis (EDA)

An initial exploratory analysis is conducted to understand class distribution.

Findings:
- Approximately **99.83%** of transactions are legitimate
- Only **0.17%** are fraudulent

This confirms the extreme imbalance and highlights the challenge for traditional classifiers.

---

## Baseline Model Construction

A **Logistic Regression** model is used as the baseline classifier.

### Workflow:
1. Feature-target separation (`X` and `y`)
2. Train-test split (70% training, 30% testing)
3. Model training on the original imbalanced dataset
4. Prediction on unseen test data

---

## Model Evaluation

Two main evaluation approaches are applied:

### Classification Report
Key metrics analyzed:
- Precision
- Recall
- F1-score

Special attention is given to **Recall for the fraud class**, as failing to detect fraud is considered a critical error.

---

### Confusion Matrix

The confusion matrix is used to visually analyze model errors.

Key insight:
- Errors related to **false negatives** (fraud classified as legitimate) are more critical than false positives.

This reinforces the need for improving minority class detection.

---

## Generative AI for Synthetic Data Creation

To address class imbalance, **Generative AI (Gemini)** is used to generate synthetic fraud transactions.

### Process:
1. Randomly select real fraud samples from the training set
2. Format samples as structured text examples
3. Build a prompt instructing the model to generate realistic synthetic fraud data
4. Generate new fraud samples using **Gemini 1.5 Flash**

The generated samples are structured as dictionaries to facilitate direct integration into the dataset.

---

## Expected Outcome

By augmenting the dataset with synthetic fraud samples:
- The representation of the minority class increases
- The Machine Learning model gains better exposure to fraud patterns
- Model performance is expected to improve in subsequent evaluations

This improvement will be analyzed in the next part of the case study.

</details>

<details>
<summary><strong>Português</strong></summary>

## Objetivo

O objetivo desta aula é demonstrar como a **IA Generativa** pode ser utilizada para corrigir **datasets desbalanceados**, especialmente em cenários de detecção de fraude, por meio da geração de dados sintéticos realistas.

---

## Contexto do Problema: Detecção de Fraudes

Em problemas de detecção de fraude, os dados apresentam forte desbalanceamento:
- Mais de 99% das transações são legítimas
- Menos de 1% correspondem a fraudes

Modelos clássicos de Machine Learning, como a **Regressão Logística**, tendem a favorecer a classe majoritária, prejudicando a identificação de fraudes.

---

## Configuração do Ambiente

A implementação prática utiliza o **Google Colaboratory**, que oferece:
- Execução em nuvem
- Uso de recursos computacionais do Google
- Facilidade de compartilhamento e colaboração

### Bibliotecas Utilizadas
- `google.generativeai`
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`

As bibliotecas são instaladas via `pip` quando necessário.

---

## Descrição do Dataset

O dataset utilizado é composto por transações de cartão de crédito.

Características principais:
- 284.807 registros
- 31 variáveis numéricas
- Coluna alvo: `class`
  - `0` → transação legítima
  - `1` → transação fraudulenta

---

## Análise Exploratória dos Dados (EDA)

A análise inicial confirma o desbalanceamento extremo:
- Aproximadamente **99,83%** das transações são legítimas
- Apenas **0,17%** são fraudes

Esse cenário compromete o desempenho de modelos tradicionais.

---

## Construção do Modelo Baseline

Foi utilizado um modelo de **Regressão Logística** como baseline.

### Etapas:
1. Separação entre variáveis preditoras (`X`) e variável alvo (`y`)
2. Divisão dos dados em treino e teste
3. Treinamento do modelo com dados desbalanceados
4. Geração de predições no conjunto de teste

---

## Avaliação do Modelo

### Relatório de Classificação
Foram analisadas métricas como:
- Precisão
- Recall
- F1-score

O **Recall da classe de fraude** é tratado como métrica crítica.

---

### Matriz de Confusão

A matriz de confusão permite avaliar visualmente os erros do modelo.

Ponto de atenção:
- **Falsos negativos** (fraudes classificadas como legítimas) são considerados os erros mais graves.

---

## Uso de IA Generativa para Geração de Dados Sintéticos

Para mitigar o desbalanceamento, foi utilizada **IA Generativa (Gemini)** para gerar transações fraudulentas sintéticas.

### Etapas:
1. Seleção de exemplos reais de fraude
2. Estruturação dos dados em formato textual
3. Construção de um prompt orientado à geração de dados
4. Geração de novas transações fraudulentas com o **Gemini 1.5 Flash**

Os dados gerados seguem uma estrutura compatível com o dataset original.

---

## Resultado Esperado

Com a ampliação da classe minoritária:
- O modelo passa a aprender melhor os padrões de fraude
- A detecção de fraudes tende a melhorar
- A comparação entre modelos será realizada na próxima parte do estudo de caso

</details>

---

> **Note:** This lesson is part of the *AI for Data* course provided by Rocketseat and is documented here for educational purposes only. All original concepts and instructional design are credited to Rocketseat.
