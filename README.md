# Detecção de Fraudes em Transações Financeiras
Projeto de Ciência de Dados e Machine Learning desenvolvido para identificar transações potencialmente fraudulentas. O trabalho utiliza dados históricos de 2025 para análise e treinamento e aplica a solução a transações de janeiro de 2026.

# Objetivo
Explorar padrões de fraude, realizar engenharia de atributos, comparar algoritmos supervisionados e aplicar o modelo selecionado a novas transações.

# Metodologia
  1. Análise Exploratória de Dados (EDA)
Foram investigadas a qualidade dos dados, a distribuição desbalanceada das classes, os valores das transações e os padrões associados a horários, dispositivos, estabelecimentos e localidades.

 2. Engenharia de atributos
O modelo utiliza 14 variáveis preditoras:
- Financeiras: valor_transacao, score_interno, log_valor;
- Temporais: hora_sin, hora_cos, dia_semana, fim_semana, turno;
- Dispositivos e interações: device_type, is_new_device, noite_dispositivo_novo;
- Contexto: nome_estabelecimento, tipo_estabelecimento, cidade.
O pré-processamento utiliza Pipeline e ColumnTransformer do scikit-learn, com imputação, padronização numérica e OneHotEncoder para variáveis categóricas.

3. Machine Learning
Foram comparados Regressão Logística, KNN, SVM, Árvore de Decisão, Random Forest e Gradient Boosting, com ajuste de hiperparâmetros via GridSearchCV e validação cruzada temporal com TimeSeriesSplit (4 divisões).
*A Random Forest foi selecionada com prioridade para o recall da classe fraude.*

## Estrutura do repositório

```text
.
├── EDA.ipynb
├── Engenharia_de_Atributos.ipynb
├── Previsao_Fraude_2026.ipynb
├── previsoes_fraude_janeiro_2026.csv
└── README.md
```

# Como executar
1. Obtenha os arquivos de entrada transacoes_historico_2025.csv e transacoes_jan2026.csv.
2. Abra os notebooks no Google Colab ou em um ambiente Jupyter com as bibliotecas necessárias.
3. Ajuste os caminhos dos arquivos: os notebooks originais usam caminhos absolutos, como /transacoes_historico_2025.csv.
4. Execute na ordem: EDA → Engenharia de Atributos → Previsão de 2026.
5. Para executar somente a inferência, disponibilize o arquivo random_forest_final_limiar_053.joblib e a base de janeiro de 2026.

# Tecnologias
Python · Pandas · NumPy · Matplotlib · Seaborn · scikit-learn · Joblib · Jupyter Notebook · Google Colab
