# Tech Challenge 1: Previsão de Custos de Seguro de Saúde

Este repositório contém o desenvolvimento de um modelo de Machine Learning para o Tech Challenge da Fase 1, focado em prever custos de seguro de saúde, conforme proposto no documento do desafio.

---

## 🎯 Objetivo do Projeto

O objetivo principal, conforme o problema proposto, é:

> Desenvolver um modelo preditivo de regressão para prever o valor dos custos médicos individuais cobrados pelo seguro de saúde.

---

## 👥 Equipe do Projeto (Grupo 28)

* Alano Coelho Mauriz Menezes (alano.menezes@hotmail.com)
* Gustavo Duran Domingues (gustavo.duran2011@gmail.com)
* Rodrigo Mendes de Faria (rodrigo.pechi@gmail.com)
* Hiran Tassinari Costa de Azevedo (hiran.tassinari@gmail.com)
* Ana Thais Senger (anathaissenger@hotmail.com)

---

## 📊 O Dataset

Foi utilizado o dataset **"US Health Insurance Dataset"**, disponível na plataforma Kaggle, para este desafio. Este conjunto de dados contém 1338 registros e 7 colunas,
que incluem características numéricas e categóricas dos segurados:

* **age**: Idade do beneficiário.
* **sex**: Gênero do contratante.
* **bmi**: Índice de Massa Corporal (IMC).
* **children**: Número de dependentes.
* **smoker**: Status de fumante (sim/não).
* **region**: Região de residência nos EUA.
* **charges**: **(Variável Alvo)** Custos médicos individuais.

---

## ⚙️ Metodologia Aplicada

O projeto foi estruturado seguindo as tarefas sugeridas no desafio para garantir robustez e clareza na análise e modelagem:

1. **Exploração de Dados (EDA):** 

   * Carregamento e exploração das características da base de dados.
   * Análise de estatísticas descritivas e visualização das distribuições relevantes.
   * Criação de um mapa de calor para entender a correlação entre as variáveis.
   * Visualização das relações entre as características mais importantes (`age`, `bmi`, `smoker`) e a variável alvo (`charges`).
   * Análise de outliers com box plots ("antes e depois" da limpeza).
2. **Pré-processamento de Dados:** 

   * Limpeza dos dados, incluindo tratamento de assimetria da variável alvo (`charges`) com transformação logarítmica e tratamento de outliers na variável `bmi`.
   * Conversão de variáveis categóricas (`sex`, `smoker`, `region`) em formato numérico usando One-Hot Encoding.
3. **Validação Estatística:** 

   * Uso da biblioteca `statsmodels` para realizar uma Regressão de Mínimos Quadrados (OLS).
   * Análise da significância estatística de cada variável (p-value) e interpretação dos coeficientes do modelo linear. 
4. **Modelagem e Otimização:** 

   * Os dados foram divididos em conjuntos de treino (80%) e teste (20%).
   * As variáveis numéricas foram padronizadas (`StandardScaler`).
   * Foram treinados três modelos de regressão: `Regressão Linear`, `Random Forest` e `Gradient Boosting`.
   * O `GridSearchCV` foi utilizado para encontrar os melhores hiperparâmetros para os modelos `Random Forest` e `Gradient Boosting`.
5. **Avaliação dos Modelos:**

   * Os modelos foram avaliados no conjunto de teste usando as métricas R² (Coeficiente de Determinação) e RMSE (Raiz do Erro Quadrático Médio).
   * Os resultados foram comparados para selecionar o modelo com melhor desempenho preditivo.
   * Apresentação de resultados visuais, como gráficos de previsões vs. valores reais. 

---

## 📈 Resultados e Conclusão

Após a avaliação, o modelo **Random Forest (otimizado)** apresentou o melhor desempenho, com o maior valor de R² e o menor RMSE. 
Este modelo demonstrou ser mais eficaz em capturar as relações complexas entre as características do segurado e seus custos médicos, atendendo à expectativa de previsões confiáveis.

Portanto, o **Random Forest** é o modelo recomendado para a tarefa de predição de custos de seguro de saúde.

---

## 🚀 Como Executar o Projeto

### Pré-requisitos

Certifique-se de ter o Python 3 instalado. As principais bibliotecas utilizadas no projeto são:

* pandas
* numpy
* scikit-learn
* matplotlib
* seaborn
* statsmodels

Você pode instalar todas as dependências com o seguinte comando (idealmente, crie um arquivo `requirements.txt` com estas bibliotecas):
`pip install pandas numpy scikit-learn matplotlib seaborn statsmodels jupyterlab`

### Estrutura do Repositório

.
├── tech_challenge_final_v3.ipynb   # O notebook Jupyter com todo o código e análise.
├── insurance.csv                   # O arquivo de dados (deve ser baixado e colocado aqui).
└── README.md                       # Este arquivo.
