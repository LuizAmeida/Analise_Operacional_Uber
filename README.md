# **Analise_Operacional_Uber**
## **Análise de dados de viagens da Uber para identificar fatores de falha e sucesso.**



## 📄 Visão Geral do Projeto (Project Overview)

A eficiência operacional é um pilar fundamental para o sucesso de empresas de ride-sharing como a Uber. Cada corrida não completada — seja por cancelamento, falta de motoristas ou problemas técnicos — representa não apenas uma perda de receita, mas também um ponto de fricção na experiência do cliente e do motorista.

Este projeto realiza uma análise profunda em um conjunto de **150.000 solicitações de corrida** para diagnosticar os principais fatores que impactam a taxa de sucesso das operações. O objetivo é ir além da análise superficial e transformar dados brutos em insights estratégicos e recomendações de negócio acionáveis.

## 📊 O Conjunto de Dados (The Dataset)

O estudo foi baseado em um conjunto de dados público disponível na plataforma Kaggle. Ele contém informações detalhadas sobre as corridas, incluindo:

* **Dados Temporais:** Data e hora da solicitação.
* **Dados de Status:** O resultado final da solicitação (`Completed`, `Cancelled by Driver`, etc.).
* **Dados Geográficos:** Locais de partida e destino.
* **Dados do Serviço:** Tipo de veículo solicitado (eBike, Sedan, Auto, etc.).
* **Métricas Operacionais:** Distância da corrida, avaliações, valor da corrida, entre outros.

## ⚙️ Metodologia e Processo de Análise

A análise foi estruturada em um processo de ponta a ponta, seguindo as melhores práticas de projetos de Ciência de Dados:

#### 1. Limpeza e Pré-processamento dos Dados
A primeira etapa consistiu em preparar os dados para a análise. As colunas de data e hora foram unificadas em um único campo `datetime` para permitir análises temporais. Foi realizada uma investigação aprofundada dos valores ausentes, revelando que a maior parte deles não era aleatória, mas sim estrutural (ex: uma corrida cancelada não possui `Ride Distance`).

#### 2. Engenharia de Features
Para extrair o máximo de valor dos dados, novas features (variáveis) foram criadas a partir dos dados existentes. As mais importantes foram:
* `hour_of_day`, `day_of_week`, `month`: Para analisar padrões de sazonalidade e demanda.
* `status_group`: Uma variável binária (`Success`/`Failure`) que simplificou a análise e serviu como variável-alvo para entender os fatores de falha.

#### 3. Análise Exploratória de Dados (EDA)
Com os dados limpos e enriquecidos, uma série de visualizações foi criada para descobrir padrões e validar hipóteses. A análise se concentrou em responder às seguintes perguntas:
* **QUANDO** os problemas ocorrem? (Análise por hora e dia da semana)
* **O QUÊ** está falhando? (Análise por tipo de veículo)
* **ONDE** estão os maiores desafios? (Análise por local de partida)

## 💡 Principais Descobertas e Insights

A análise revelou três conclusões principais e surpreendentes:

#### Insight 1: O problema é temporal, mas não semanal.
A taxa de falha acompanha diretamente os picos de demanda, sendo significativamente maior durante os horários de pico da manhã (7h-10h) e, principalmente, da noite (17h-20h). Isso sugere uma sobrecarga da rede. Curiosamente, o dia da semana não demonstrou ter um impacto relevante na eficiência.

#### Insight 2: O fator geográfico é o mais crítico.
A análise identificou "hotspots" de ineficiência. Certos locais de partida não apenas concentram um alto volume de falhas, mas possuem taxas de falha alarmantes, provando que o problema é sistêmico em áreas específicas. Os casos mais graves são:
* **Vinobapuri:** 45.32% de taxa de falha.
* **Akshardham:** 43.86% de taxa de falha.
* **Badshahpur:** 41.71% de taxa de falha.

#### Insight 3: O tipo de serviço não é o vilão.
Embora a hipótese inicial pudesse ser que serviços específicos (como eBikes) fossem menos confiáveis, os dados provaram o contrário. Todos os tipos de veículos operam com uma taxa de falha notavelmente similar (entre 37% e 38.5%), indicando que o desafio é sistêmico da plataforma e da logística, não de uma categoria de serviço.

## 🚀 Recomendações Estratégicas

Com base nos insights, as seguintes recomendações foram formuladas para a Uber:

1.  **Implementar um Plano de Ação Geograficamente Focado:** Em vez de ações de marketing ou incentivos generalizados, a empresa deve focar seus recursos nos "hotspots" de alta falha. Ações como **surge pricing dinâmico e direcionado** para motoristas nessas áreas durante os horários de pico podem ajudar a equilibrar a oferta e a demanda onde é mais necessário.

2.  **Realizar Investigação de Causa Raiz nos Hotspots:** Os dados mostram "onde" o problema está, mas não o "porquê" final. Uma investigação de campo ou análise qualitativa é recomendada para entender os motivos específicos da alta taxa de falha em locais como Vinobapuri (ex: trânsito excessivo, falta de locais seguros para embarque, problemas de GPS na região).

## 🛠️ Tecnologias e Bibliotecas Utilizadas
* **Linguagem:** `Python`
* **Bibliotecas Principais:** `Pandas` (Manipulação de dados), `Matplotlib` e `Seaborn` (Visualização de dados).
* **Ambiente:** O projeto foi desenvolvido integralmente em um `Kaggle Notebook`.

## 🔄 Como Reproduzir o Projeto
1.  Faça o clone deste repositório.
2.  Baixe o conjunto de dados original a partir do [link no Kaggle](https://www.kaggle.com/datasets/yashdevladdha/uber-ride-analytics-dashboard).
3.  Coloque o arquivo de dados `.csv` no mesmo diretório do notebook.
4.  Execute o notebook em um ambiente Python compatível.

## 🔗 Links Relevantes
* **[Análise Completa no Kaggle Notebook](https.www.kaggle.com/code/luizalmeida84/an-lise-da-efici-ncia-operacional-da-uber)**
* **[Conjunto de Dados Original](https://www.kaggle.com/datasets/yashdevladdha/uber-ride-analytics-dashboard)**
