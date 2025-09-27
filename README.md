# **Analise_Operacional_Uber**
**Análise de dados de viagens da Uber para identificar fatores de falha e sucesso.**

## 🎯 1. Objetivo do Projeto
Analisar um conjunto de dados de 150.000 corridas da Uber para identificar os principais fatores que levam a falhas operacionais (corridas não completadas), com o objetivo de propor recomendações estratégicas para melhorar a taxa de sucesso da plataforma.

## 📈 2. Principais Descobertas (Insights)

* **Fator Temporal (O "Quando"):** A análise confirmou que as falhas estão diretamente correlacionadas com os horários de pico da demanda, com o maior volume ocorrendo no pico noturno (17h-20h), sugerindo uma sobrecarga do sistema.

* **Fator Geográfico (O "Onde"):** Este se revelou o fator mais crítico. A análise identificou "hotspots" de ineficiência, como **Vinobapuri (45.32% de taxa de falha)** e **Akshardham (43.86%)**, provando que o problema é altamente concentrado geograficamente.

* **Fator de Serviço (O "O Quê"):** Contrariando a hipótese inicial, a análise mostrou que o tipo de veículo **não é um fator determinante**. Todos os serviços operam com uma taxa de falha muito similar (entre 37% e 38.5%).

## 💡 3. Recomendações de Negócio

1.  **Implementar Ações Geograficamente Focadas:** Priorizar os "hotspots" de alta falha (Vinobapuri, Akshardham) com ações como **incentivos financeiros direcionados para motoristas** durante os horários de pico.
2.  **Investigar a Causa Raiz nos Hotspots:** Aprofundar a investigação para entender por que essas localidades específicas têm taxas de falha tão altas (ex: problemas de GPS, trânsito, falta de locais de embarque).

## 🛠️ 4. Ferramentas Utilizadas
* **Linguagem:** Python
* **Bibliotecas:** Pandas, Matplotlib, Seaborn
* **Ambiente:** Kaggle Notebooks

## 🔗 5. Links
* **[Clique aqui para ver a análise completa no Kaggle Notebook](https://www.kaggle.com/code/luizalmeida84/an-lise-da-efici-ncia-operacional-da-uber)**
* **[Clique aqui para acessar o Conjunto de Dados Original](https://www.kaggle.com/datasets/yashdevladdha/uber-ride-analytics-dashboard)**

* ## ⚙️ 6. Como Reproduzir o Projeto
1.  Faça o clone deste repositório.
2.  Baixe o conjunto de dados original a partir do [link no Kaggle](https://www.kaggle.com/datasets/yashdevladdha/uber-ride-analytics-dashboard).
3.  Coloque o arquivo de dados `.csv` no mesmo diretório do notebook.
4.  Execute o notebook em um ambiente com Python, Jupyter, Pandas e as outras bibliotecas listadas.
