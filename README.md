<p align="center">
  <img src="https://raw.githubusercontent.com/arvieira/bootcamp_projeto_final/main/images/covid.jpg" width = 70%>
</p>

# Projeto: Criando um Modelo de Machine Learning para Previsão do Uso de CTI por Pacientes de COVID-19 Utilizando Dados Clínicos do Hospital Sírio-Libanes.
##### Aluno: André R. Vieira
---
- # Da Introdução:

A pandemia do novo coronavirus COVID-19 teve início na cidade de Wuhan na provincia de Hubei na República Popular da China em Dezembro de 2019. 
Desde então, esforços mundiais unificados vem sendo realizados para prover suporte a sistemas de saúde, desenvolver tratamentos consistentes, evitar a proliferação da doença, desenvolvimento de vacinas entre outros. 
Este trabalho propõe a construção de um novo modelo de Machine Learning, avaliando diversos algoritmos diferentes com comparação por métricas estatísticas, para a previsão precoce da necessidade de internações em CTIs. 
A base de dados utilizada será a provida pelo Hospital Sírio-Libanês da cidade de São Paulo no Brasil. 
Como resultado, pretende-se obter um modelo que atinja valores de AUC acima 0.7.

---
- # Do Referencial Teórico:

Este trabalho apresenta uma pesquisa sistemática na ferramenta de busca "Google Scholar".
Foram selecionados quatro trabalhos relacionados diretamente à temática principal do trabalho.
A análises dos artigos encontrados apresentou um processo geral comum de trabalho de bases de dados de pacientes e criação de modelos de *Machine Learning*.
Pontos de influencia de dados clínicos e demográficos na evolução de pacientes de COVID-19 foram levantados e posteriormente analisados para a base utilizada neste trabalho.

---
- # Dos Dados:

A base de dados utilizada para este trabalho é aquela fornecida pelo Hospital Sírio-Libanês da cidade de São Paulo no Brasil.
O conjunto de dados é composto por 231 colunas, sendo composta por 54 características clínicas e demográficas de pacientes de COVID-19.
Os dados se encontram em linhas que representam janelas de horas na evolução dos quadros dos referidos pacientes.
Há uma coluna que indica se até o momento o paciente enviado para tratamento intensivo em CTI.

---

- # Da Proposta e Metodologia Utilizada:

Este trabalho propõe a criação de um modelo de *Machine Learning* para evolução do quadro de pacientes de COVID-19.
Baseado em janelas de quadros clínicos, busca-se treinar um modelo para prever a necessidade futura de tratamento intensivo em CTIs.
Previamente à construção do modelo, os dados foram limpos e tratados.
Assim como, as características demográficas/clínicas apontadas nos trabalhos relacionados selecionados foram analisadas com visualizações de dados para buscar por influências nos quadros dos pacientes.

Para a análise dos dados e criação do modelo mais adequado, assim como para a avaliação e validação do que foi construído, foram adotadas as seguintes etapas:
  - Limpeza dos dados
  - Separação de variáveis contínuas e categóricas
  - Retirada de variáveis com altas correlações
  - Criação de um conjunto de modelos
  - Divisão dos dados em treino, validação e teste
  - Realização de Cross-validation
  - Seleção do melhor algoritmo com métricas ROC-AUC, precision, recall, f1-score e acurácia
  - Otimização dos hiperparâmetros por buscas em Grid e aleatória
  - Validação do modelo
  - Avaliação dos resultados

---
- # Da Conclusão

Este trabalho tem como objetivo a criação de um modelo de *Machine Learning* para a previsão da evolução do quadro de pacientes de COVID-19.
A base de dados utilizada foi fornecida pelo Hospital Sírio-Libanês da cidade de São Paulo no Brasil.
Foi realizada uma pesquisa sistemática na literatura por trabalhos semelhantes, buscando apresentar um cenário mais adequado do estado da arte para a elaboração do trabalho.
Como resultado, foram encontrados algoritmos mais adequados e possíveis dados clínicos/demográficos que influenciariam a evolução dos pacientes de COVID-19.
Os dados clínicos encontrados foram analisados, indicando que pessoas mais idosas tendem a ter uma pior evolução da doença.
Do mesmo modo, foi encontrado um desbalanceamento entre gêneros, mas não foi possível identifica qual gênero evolui pior em virtude da anonimização dos dados da base utilizada.
Quanto aos demais dados clínicos, não foi possível retirar conclusões.
Suspeita-se de que a normalização dos dados entre -1 e 1, realizada pela fonte dos dados, acabou por suavizar parâmetros de variação muito sensível.

A criação do modelo utilizou o algoritmo chamado "eXtreme Gradient Boosting (XGBoost)", o qual retornou os melhores resultados nos trabalhos analisados.
Foi realizada a comparação do modelo obtido pelo algoritmo citado com outros 3 modelos: "DummyClassifier", "LogisticRegression" e "DecisionTreeClassifier".
Em seguida, foi realizada uma otimização de hiperparâmetros do melhor modelo com duas buscas, sendo a primeira em Grid e a segunda aleatória.
Como resultado, foi obtido um modelo com as seguintes métricas:
- AUC Médio: 0.980
- Desvio padrão: 0.008
- Intervalo de confiança a 95%: 0.964 a 0.997

Em seguida, o modelo foi salvo em arquivo para sua utilização quando necessário.
Uma matriz de confusão e um relatório de *Precision*, *Recall* e *F1-score* foram emitidos.
Pode-se apontar um *Recall* de 0.94 para o índice 1, o que é de extremamente otimista para o uso do modelo em questão, uma vez que essa métrica representa aqueles pacientes que precisariam de CTI, mas foi indicado o contrário.
