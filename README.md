# Classificação da Qualidade de Vinhos com Machine Learning

Este projeto foi desenvolvido como parte do Tech Challenge da Pós Tech, com o objetivo de aplicar técnicas de análise de dados e Machine Learning para classificar a qualidade de vinhos a partir de características físico-químicas.

## 1. Contexto do Projeto

A avaliação da qualidade de vinhos é tradicionalmente realizada por especialistas, considerando aspectos sensoriais como aroma, sabor, acidez e equilíbrio. Apesar de relevante, esse processo pode ser subjetivo e demandar tempo.

Com o uso de técnicas de ciência de dados e aprendizado de máquina, é possível utilizar informações físico-químicas dos vinhos para apoiar a previsão da qualidade final do produto. Dessa forma, modelos preditivos podem contribuir para decisões mais orientadas por dados no processo produtivo.

## 2. Objetivo

O objetivo deste projeto é desenvolver um modelo de classificação capaz de prever se um vinho pode ser considerado de alta qualidade ou de baixa/média qualidade com base em suas características físico-químicas.

A variável original `quality` foi transformada em uma classificação binária:

* `1` — Alta qualidade: vinhos com nota maior ou igual a 7;
* `0` — Baixa/Média qualidade: vinhos com nota menor que 7.

## 3. Base de Dados

A base utilizada foi o Wine Quality Dataset, contendo informações físico-químicas de amostras de vinho.

As principais variáveis disponíveis são:

* Acidez fixa;
* Acidez volátil;
* Ácido cítrico;
* Açúcar residual;
* Cloretos;
* Dióxido de enxofre livre;
* Dióxido de enxofre total;
* Densidade;
* pH;
* Sulfatos;
* Teor alcoólico;
* Qualidade do vinho.

A base utilizada neste projeto possui 1.143 registros e 13 colunas.

## 4. Estrutura do Projeto

```text
wine-quality-classification/
│
├── data/
│   └── WineQT.csv
│
├── notebooks/
│   └── 01_analise_modelagem_wine_quality.ipynb
│
├── results/
│   ├── resultados_modelos.csv
│   ├── importancia_variaveis_random_forest.csv
│   └── importancia_variaveis_random_forest_executivo.png
│
├── src/
│
├── requirements.txt
└── README.md
```

## 5. Etapas Desenvolvidas

O projeto foi desenvolvido seguindo as seguintes etapas:

1. Compreensão do problema;
2. Análise exploratória dos dados;
3. Transformação da variável alvo em classificação binária;
4. Análise do balanceamento das classes;
5. Pré-processamento dos dados;
6. Treinamento dos modelos de classificação;
7. Avaliação dos modelos;
8. Interpretação dos resultados;
9. Conclusão final.

## 6. Modelos Testados

Foram treinados e comparados dois modelos de classificação:

* Regressão Logística;
* Random Forest.

A Regressão Logística foi utilizada como modelo inicial e interpretável. O Random Forest foi utilizado por sua capacidade de capturar relações mais complexas entre as variáveis.

## 7. Resultados dos Modelos

Os modelos foram avaliados com métricas adequadas para problemas de classificação, especialmente considerando o desbalanceamento entre as classes.

| Modelo              | Acurácia | Precision | Recall | F1-score | ROC-AUC |
| ------------------- | -------: | --------: | -----: | -------: | ------: |
| Regressão Logística |    0.799 |     0.379 |  0.688 |    0.489 |   0.850 |
| Random Forest       |    0.900 |     0.629 |  0.688 |    0.657 |   0.918 |

O Random Forest apresentou o melhor desempenho geral, com maior acurácia, maior precision, maior F1-score e maior ROC-AUC. Além disso, manteve o mesmo recall da Regressão Logística para a classe de alta qualidade.

Isso significa que o Random Forest conseguiu identificar a mesma proporção de vinhos de alta qualidade, mas com menor quantidade de classificações incorretas.

## 8. Principais Variáveis Associadas à Qualidade

A análise de importância das variáveis do modelo Random Forest indicou que os principais fatores associados à classificação da qualidade dos vinhos foram:

1. Teor alcoólico;
2. Sulfatos;
3. Ácido cítrico;
4. Acidez volátil;
5. Densidade;
6. Dióxido de enxofre total.

O teor alcoólico foi a variável com maior importância relativa no modelo, indicando forte associação com vinhos classificados como de alta qualidade.

É importante destacar que a importância das variáveis indica associação estatística dentro da base analisada, mas não deve ser interpretada como causalidade direta.

## 9. Conclusão

O projeto demonstrou que é possível utilizar características físico-químicas dos vinhos para apoiar a classificação de sua qualidade por meio de modelos de Machine Learning.

Entre os modelos testados, o Random Forest apresentou o melhor desempenho geral e foi selecionado como o modelo mais adequado para este problema de classificação.

Do ponto de vista de negócio, o modelo pode apoiar produtores e especialistas na análise inicial da qualidade dos vinhos, contribuindo para decisões mais orientadas por dados durante o processo produtivo. No entanto, ele não substitui a avaliação sensorial realizada por especialistas, devendo ser entendido como uma ferramenta complementar de apoio à tomada de decisão.

## 10. Como Executar o Projeto

Para executar este projeto, é necessário ter o Python instalado e instalar as bibliotecas listadas no arquivo `requirements.txt`.

No terminal, execute:

```bash
pip install -r requirements.txt
```

Depois, abra o notebook localizado na pasta `notebooks/`:

```text
notebooks/01_analise_modelagem_wine_quality.ipynb
```

Execute as células em sequência para reproduzir a análise exploratória, o pré-processamento, o treinamento dos modelos e a avaliação dos resultados.

## 11. Bibliotecas Utilizadas

As principais bibliotecas utilizadas foram:

* pandas;
* numpy;
* matplotlib;
* scikit-learn;
* jupyter.

## 12. Autoria

Projeto desenvolvido por Stephanie Caroline Viana Puccinelli para o Tech Challenge da Pós Tech.
