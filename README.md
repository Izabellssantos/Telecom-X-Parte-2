# 📊 Projeto Telecom X - Parte 2

## 🔎 Propósito do Projeto
O objetivo principal desta análise é **prever a evasão de clientes (Churn)** em uma empresa de telecomunicações.  
A partir de variáveis demográficas, contratuais e de uso de serviços, buscamos identificar **quais fatores mais influenciam a saída de clientes** e propor **estratégias de retenção**.

---

## 📂 Estrutura do Projeto
- `notebooks/`  
  - `TelecomX_Parte2.ipynb` → Notebook principal com toda a análise (pré-processamento, EDA, modelagem e avaliação).  
- `data/`  
  - `/content/dados_tratados3.csv` → Base de dados já tratada e pronta para modelagem.  
- `visualizations/`  
  - Gráficos e visualizações geradas durante a análise exploratória.  
- `README.md` → Este documento de descrição do projeto.

---

## ⚙️ Preparação dos Dados
### Classificação das Variáveis
- **Categóricas:** gênero, contrato, método de pagamento, serviços contratados etc.  
- **Numéricas:** tempo de permanência (tenure), mensalidade (MonthlyCharges), gasto total (TotalCharges).  

### Etapas Realizadas
1. **Tratamento de valores ausentes e inconsistentes** – remoção/ajuste de entradas inválidas.  
2. **Codificação de variáveis categóricas** – aplicação de **OneHotEncoder** e `pd.get_dummies()`.  
3. **Normalização dos dados** – aplicada apenas em modelos que exigem (ex.: Regressão Logística, KNN).  
4. **Divisão dos dados** – em treino e teste (70/30), para avaliar desempenho em dados não vistos.

---

## 🤖 Modelagem Preditiva
Foram testados diferentes modelos para prever o churn:

- **Regressão Logística**  
  - Exige normalização.  
  - Fácil interpretação dos coeficientes, permitindo explicar variáveis críticas.  

- **Random Forest (com e sem SMOTE)**  
  - Não exige normalização.  
  - Captura melhor a relação entre variáveis complexas.  
  - Apresentou melhor recall para identificar clientes que realmente cancelam.  

---

## 📈 Análise Exploratória de Dados (EDA)
Durante a EDA, alguns padrões importantes foram identificados:

- Clientes com **contrato mensal** têm maior probabilidade de churn.  
- **Baixo tempo de permanência (tenure)** está fortemente associado à evasão.  
- Clientes com **serviços de suporte (TechSupport, OnlineSecurity)** tendem a permanecer mais.  
- **Mensalidades altas (MonthlyCharges)** aumentam as chances de cancelamento.  

### Exemplos de Visualizações
- **Boxplot:** Tempo de contrato × Churn.  
- **Boxplot:** Total gasto × Churn.  
- **Heatmap:** Correlação entre variáveis numéricas.  
- **Matriz de confusão:** Avaliação dos modelos de classificação.

---

## 🚀Conclusões Gerais

O Random Forest com SMOTE foi o modelo com maior capacidade de prever clientes que iriam cancelar.
A evasão está principalmente associada a contratos mensais, baixo tempo de permanência e custos elevados.
Estratégias de retenção devem focar em programas de fidelização, pacotes de serviços de segurança e suporte, e revisão de preços para clientes novos.

