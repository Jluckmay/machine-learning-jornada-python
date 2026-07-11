<!-- Language Selection -->
<div align="center">
  <a href="#-português">🇧🇷/🇵🇹 Português</a> | <a href="#-english">🇺🇸/🇬🇧 English</a>
</div>

---

# 📊 Análise de Risco de Crédito (Credit Score Analysis)

<h2 id="-português">🇧🇷/🇵🇹 Versão em Português</h2>

Um projeto completo de Ciência de Dados de ponta a ponta: desde o tratamento e modelagem preditiva em Python até o deploy de um modelo de Machine Learning diretamente no navegador web.

O objetivo deste projeto é analisar o histórico e as características financeiras de clientes para prever a sua pontuação de crédito (**Good**, **Standard** ou **Poor**), auxiliando na tomada de decisão para concessão de crédito.

## ✨ Funcionalidades Principais

* **Pré-processamento de Dados:** Tratamento de valores nulos, conversão de variáveis categóricas (Label Encoding) e normalização de variáveis numéricas (StandardScaler).
* **Particionamento Estratificado:** Divisão dos dados em Treino e Teste garantindo a proporção exata das classes alvo, evitando viés no aprendizado.
* **Treinamento e Avaliação de Modelos:** Comparação de performance entre três arquiteturas poderosas:
    * Random Forest (Melhor Modelo: **82.5% de Acurácia**)
    * XGBoost
    * TabNet
* **Dashboard Interativo Web:** Uma interface responsiva construída com HTML/CSS e `Plotly.js` para visualização dos resultados, incluindo suporte a **Dark/Light Mode** e **Bilingue (PT/EN)**.
* **Inferência em Tempo Real (Browser-side):** Utilização da biblioteca `m2cgen` para exportar o modelo Random Forest treinado em Python para JavaScript nativo. O utilizador pode fazer o upload de um ficheiro `.csv` e obter as previsões instantaneamente no front-end, sem necessidade de um servidor backend.

## 🛠️ Tecnologias Utilizadas

**Ciência de Dados (Python):**
* `pandas` e `numpy` (Manipulação de dados)
* `scikit-learn` (Machine Learning, Preprocessing, Métricas)
* `xgboost` (Modelagem avançada)
* `pytorch-tabnet` (Deep Learning para dados tabulares)
* `m2cgen` (Exportação do modelo para JavaScript)

**Front-End (Web):**
* HTML5 / CSS3 / Vanilla JavaScript
* `Plotly.js` (Visualização de dados interativa)

## 🚀 Como Executar o Projeto

### 1. Treinamento do Modelo (Python)
No seu ambiente Jupyter Notebook ou script Python:
1. Carregue o conjunto de dados original.
2. Execute as etapas de limpeza e transformação (LabelEncoder, StandardScaler).
3. Treine os modelos e avalie as métricas.
4. Exporte o melhor modelo (Random Forest) para JavaScript utilizando o `m2cgen`:

```python
!pip install m2cgen

import m2cgen as m2c

# 1. Traduz o modelo do scikit-learn para uma função JavaScript pura
codigo_js = m2c.export_to_javascript(arvore)

# 2. Salva esse código num ficheiro
with open("modelo_rf.js", "w") as f:
    f.write(codigo_js)
```

### 2. Executando o Dashboard Web Localmente
1. Certifique-se de que o ficheiro gerado `modelo_rf.js` está na mesma pasta que o ficheiro `index.html`.
2. Dê um duplo clique no ficheiro `index.html` para abri-lo no seu navegador (não é necessário servidor local).
3. Navegue pelos gráficos interativos de análise de estratificação e desempenho.

### 2.1. Dashboard Web Online
Interface web disponível em: [jluckmay.github.io/machile-learning-jornada-python](https://jluckmay.github.io/machile-learning-jornada-python)

### 3. Realizando Previsões em Tempo Real
Para testar a inteligência artificial diretamente no site:
1. No Python, exporte os dados de teste já **pré-processados** (100% numéricos, com codificação e na ordem correta de 23 colunas) para um ficheiro CSV. 
   * *Atenção: O CSV não deve conter textos, apenas os valores numéricos gerados após o tratamento.*
2. No Dashboard, vá até à secção **Inferência em Tempo Real**.
3. Clique em "Escolher Ficheiro .CSV" e selecione o seu ficheiro de teste.
4. Clique em "Rodar Random Forest". A tabela exibirá o ID do cliente e a classificação prevista instantaneamente!

## 📁 Estrutura do Projeto

```text
📦 credit-risk-analysis
 ┣ 📜 final.ipynb             # Notebook com toda a análise e modelagem em Python
 ┣ 📜 index.html              # Dashboard interativo com interface web
 ┣ 📜 modelo_rf.js            # Modelo Random Forest convertido para JavaScript
 ┣ 📜 clientes.csv            # Dataset original (dados brutos)
 ┣ 📜 novos_clientes.csv      # Dataset para teste 
 ┗ 📜 README.md               # Documentação do projeto
```

## 📈 Resultados Alcançados

A normalização dos dados e a estratificação durante o particionamento demonstraram ser etapas cruciais. O modelo **Random Forest** obteve o melhor desempenho na identificação de clientes com "Score Poor", minimizando o risco financeiro em potenciais concessões de crédito. A integração do modelo no navegador via `m2cgen` provou ser uma solução extremamente leve e eficiente para deploy em aplicações serverless.

## 📄 Licença

Este projeto está licenciado sob a licença **MIT** - consulte o ficheiro [LICENSE](LICENSE) para obter mais detalhes. Fique à vontade para utilizar, modificar e distribuir este código.

<br>

---

<h2 id="-english">🇺🇸/🇬🇧 English Version</h2>

A complete end-to-end Data Science project: from data preprocessing and predictive modeling in Python to deploying a Machine Learning model directly in the web browser.

The goal of this project is to analyze the historical and financial characteristics of customers to predict their credit score (**Good**, **Standard**, or **Poor**), assisting in decision-making for credit concessions.

## ✨ Main Features

* **Data Preprocessing:** Handling null values, categorical variable conversion (Label Encoding), and numerical variable normalization (StandardScaler).
* **Stratified Splitting:** Dividing the data into Train and Test sets while ensuring the exact proportion of target classes, avoiding learning bias.
* **Model Training and Evaluation:** Performance comparison between three powerful architectures:
    * Random Forest (Best Model: **82.5% Accuracy**)
    * XGBoost
    * TabNet
* **Interactive Web Dashboard:** A responsive interface built with HTML/CSS and `Plotly.js` for result visualization, including **Dark/Light Mode** and **Bilingual (PT/EN)** support.
* **Real-Time Inference (Browser-side):** Using the `m2cgen` library to export the Python-trained Random Forest model to native JavaScript. Users can upload a `.csv` file and get predictions instantly on the front-end, with no backend server required.

## 🛠️ Technologies Used

**Data Science (Python):**
* `pandas` and `numpy` (Data manipulation)
* `scikit-learn` (Machine Learning, Preprocessing, Metrics)
* `xgboost` (Advanced modeling)
* `pytorch-tabnet` (Deep Learning for tabular data)
* `m2cgen` (Exporting the model to JavaScript)

**Front-End (Web):**
* HTML5 / CSS3 / Vanilla JavaScript
* `Plotly.js` (Interactive data visualization)

## 🚀 How to Run the Project

### 1. Model Training (Python)
In your Jupyter Notebook environment or Python script:
1. Load the original dataset.
2. Run the cleaning and transformation steps (LabelEncoder, StandardScaler).
3. Train the models and evaluate the metrics.
4. Export the best model (Random Forest) to JavaScript using `m2cgen`:

```python
!pip install m2cgen

import m2cgen as m2c

# 1. Translates the scikit-learn model to a pure JavaScript function
codigo_js = m2c.export_to_javascript(arvore)

# 2. Saves this code to a file
with open("modelo_rf.js", "w") as f:
    f.write(codigo_js)
```

### 2. Running the Web Dashboard Locally
1. Make sure the generated `modelo_rf.js` file is in the same folder as the `index.html` file.
2. Double-click the `index.html` file to open it in your browser (no local server needed).
3. Navigate through the interactive charts for stratification and performance analysis.

### 2.1. Online Web Dashboard
Web interface available at: [jluckmay.github.io/machile-learning-jornada-python](https://jluckmay.github.io/machile-learning-jornada-python)

### 3. Making Real-Time Predictions
To test the artificial intelligence directly on the website:
1. In Python, export your **pre-processed** test data (100% numerical, properly encoded, and following the exact order of the 23 columns) to a CSV file. 
   * *Note: The CSV must not contain any strings, only the numerical values generated after processing.*
2. On the Dashboard, scroll to the **Real-Time Inference** section.
3. Click "Choose .CSV File" and select your test file.
4. Click "Run Random Forest". The table will display the customer ID and the predicted classification instantly!

## 📁 Project Structure

```text
📦 credit-risk-analysis
 ┣ 📜 final.ipynb             # Notebook with the full analysis and modeling in Python
 ┣ 📜 index.html              # Interactive dashboard with web interface
 ┣ 📜 modelo_rf.js            # Random Forest model converted to JavaScript
 ┣ 📜 clientes.csv            # Original dataset (raw data)
 ┣ 📜 novos_clientes.csv      # Test dataset 
 ┗ 📜 README.md               # Project documentation
```

## 📈 Results Achieved

Data normalization and stratification during data splitting proved to be crucial steps. The **Random Forest** model performed best in identifying customers with a "Poor" score, minimizing financial risks in potential credit concessions. Integrating the model into the browser via `m2cgen` proved to be an extremely lightweight and efficient solution for deploying in serverless applications.

## 📄 License

This project is licensed under the **MIT** License - see the [LICENSE](LICENSE) file for more details. Feel free to use, modify, and distribute this code.