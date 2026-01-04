# Comparação de Modelos Preditivos para o Mercado Imobiliário (Dataset house_16H)

Este repositório contém os códigos e análises desenvolvidos para a disciplina de **Mineração de Dados Aplicada** do Centro de Informática da Universidade Federal de Pernambuco (CIn-UFPE).

O projeto realiza um estudo comparativo de diversos algoritmos de aprendizado de máquina para classificar o potencial de investimentos imobiliários nos EUA.

## 👥 Autores
* Douglas Araújo
* Hallan Ângelo
* Ingrid Freire
* Katharian Abrahel

## 📄 Descrição do Projeto

O objetivo deste trabalho é aplicar e comparar modelos preditivos capazes de estimar o potencial de investimentos em regiões de habitações com base em dados demográficos e do mercado imobiliário.

Foi utilizada a base de dados **house_16H**, que contém variáveis demográficas e de mercado. O problema foi modelado como uma tarefa de classificação binária (Investimento Positivo 'P' vs. Negativo 'N').

### Metodologia de Avaliação
* **Divisão dos Dados:** 80% Treino / 20% Teste (Estratificado para manter proporção das classes).
* **Validação:** Validação Cruzada Estratificada (k=10).
* **Otimização:** Busca de hiperparâmetros (RandomizedSearchCV) com 20 iterações.
* **Métricas:** Acurácia, Precisão, Recall, F1-Score e AUC-ROC.

## 🚀 Modelos Implementados

Os seguintes algoritmos foram implementados e otimizados em notebooks individuais:

1.  **KNN (K-Nearest Neighbors):** Otimizado para k=41, métrica Manhattan.
2.  **LVQ (Learning Vector Quantization):** Protótipos por classe e ajuste de learning rate.
3.  **Árvore de Decisão:** Critério de entropia com poda (max_depth=7).
4.  **SVM (Support Vector Machine):** Kernel RBF com ajuste de Gamma e C.
5.  **Random Forest:** Ensemble com 200 árvores (bootstrap=True).
6.  **MLP (Multilayer Perceptron):** Rede neural com otimizador Adam e ativação ReLU.
7.  **Comitê de Redes Neurais:** Voting Classifier com 3 melhores arquiteturas de RNA.
8.  **Comitê Heterogêneo (Stacking):** Random Forest, MLP e KNN como base; Random Forest como meta-aprendiz.
9.  **XGBoost:** Boosting baseado em gradiente otimizado.
10. **LightGBM:** Boosting baseado em histogramas (Crescimento folha-a-folha).

## 📊 Resultados Consolidados (Conjunto de Teste)

Abaixo, a performance comparativa dos modelos no conjunto de teste:

| Modelo | Acurácia | Precisão | Recall | F1-Score | AUC-ROC |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **KNN** | 0.7547 | 0.7959 | 0.8754 | 0.8338 | 0.7825 |
| **LVQ** | 0.7762 | 0.8589 | 0.8155 | 0.8558 | 0.7493 |
| **Árvore de Decisão** | 0.8571 | 0.8917 | 0.9070 | 0.8992 | 0.9117 |
| **SVM** | 0.7356 | 0.7376 | 0.9682 | 0.8373 | 0.7905 |
| **Random Forest** | 0.8971 | 0.9158 | 0.9401 | 0.9277 | 0.9528 |
| **MLP** | 0.8944 | 0.9170 | 0.9344 | 0.9256 | 0.9471 |
| **Comitê de RNAs** | 0.7762 | 0.7846 | 0.9394 | 0.8551 | 0.8565 |
| **Stacking** | 0.8670 | 0.9082 | 0.9020 | 0.9051 | 0.9286 |
| **XGBoost** | 0.8964 | 0.9213 | 0.9323 | 0.9268 | 0.9525 |
| **LightGBM** | **0.9026** | **0.9225** | **0.9404** | **0.9314** | **0.9565** |

> **Conclusão:** O **LightGBM** apresentou o melhor desempenho geral, combinando a maior acurácia (90,26%) e AUC-ROC (95,65%) com eficiência computacional, seguido de perto pelo Random Forest e XGBoost.

## 📂 Estrutura do Repositório

```bash
├── data/
│   ├── house_16H.arff
│   ├── test.csv
│   └── train.csv
├── notebooks/
│   ├── 01_separacao_bases.ipynb
│   ├── 02_knn.ipynb
│   ├── 03_lvq.ipynb
│   ├── 04_arvore_decisao.ipynb
│   ├── 05_svm.ipynb
│   ├── 06_random_forest.ipynb
│   ├── 07_mlp.ipynb
│   ├── 08_comite_rna.ipynb
│   ├── 09_stacking.ipynb
│   ├── 10_xgboost.ipynb
│   └── 11_lightgbm.ipynb
└── README.md
```

## 🛠️ Tecnologias Utilizadas

* Python
* Scikit-Learn
* XGBoost
* LightGBM
* Pandas / Numpy
* Matplotlib / Seaborn (Visualização)

## 📚 Referências

* Dataset house_16H (OpenML)
* Documentação do Scikit-Learn
* Relatório Técnico da disciplina (Março, 2025)
