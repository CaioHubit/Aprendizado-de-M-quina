<h1 align="center"> Aprendizado de Máquina </h1>

<p align="center">
<img src="http://img.shields.io/static/v1?label=STATUS&message=EM%20DESENVOLVIMENTO&color=GREEN&style=for-the-badge"/>
</p>

Sobre
=================

<h3>Esse é um projeto que visa o aprendizado de máquina(Machine Learning), portanto foi feito em prol didático. Feito por um grupo de 4 estudantes da Ilum   Escola de Ciência.</h3>

O projeto se baseia na adquirição de um dataset de interesse dos mais diversos bancos de API's existentes, para que possamos construir um algorítmo que aprenda sobre os dados e possa prever um alvo que lhe foi passado. A máquina, a partir do algorítmo implantado, irá se basear em diversos métodos para tentar encontrar semelhanças e correlações entre os dados, podendo assim retornar um valor aproximado ao nosso alvo. Também são analisados os erros entre os dados originais e a previsão do modelo, com gráficos deixando mais visíveis estas margens de erro.
O dataset que escolhemos foi o *Minerals Database*, que contém diversos tipos de minerais e suas propriedades fisico-químicas, onde nossa finalidade é de prever através do algorítmo de aprendizagem de máquinas o *índice de refração* de um mineral baseado em suas outras propriedades.

Tabela de Conteudo
=================
- [x] **Bloco 1: DataBase (Coleta e Preparação)**
   
  * O primeiro bloco consiste na escolha do dataset a ser utilizado, na coleta dos dados deste dataset, sua conversão para um Dataframe e seu ajuste (remoção de dados incompletos, nulos e NaN e conversão de dados categóricos). É uma etapa de extrema importância pois assim utilizaremos apenas os dados necessários e relevantes para conseguirmos realizar a previsão de nosso alvo.

- [x] **Bloco 2: Métodos de regressão**

  * Neste segundo bloco, iremos testar a eficiência do nosso modelo de previsões para identificarmos se possuímos de fato um bom modelo. Para um modelo bom, o viés e variância dos dados originais com os previstos devem ser equilibrados. Definem-se, então, os atributos que serão utilizados para a previsão do nosso alvo, e em seguida, é realizada a divisão deste Dataframe em dados de treino e teste, para que o computador possa realizar previsões do alvo que queremos prever, baseado no conjunto de dados treino. Após esta divisão, podemos treinar nosso algoritmo com diversos métodos de regressão, definir conjuntos de hiperparâmetros (que são atributos dos métodos que podemos alterar, a fim de uma melhora do treinamento do modelo), e para alguns casos realizar a normalização logarítmica ou escalonada. Por fim, análises estatísticas dos dados (variância, média, moda, desvio padrão, etc...), métricas de erros como RMSE e Quadrados Mínimos, e graficações, são computadas para melhor entendimento do comportamento dos dados que serão utilizados. 
   - **Modelos de regressão supervisionados:**
   - [x] `Método`: Baseline (Dummy Regressor)
      * Modelo mais simples, que realiza a previsão da média dos valores do target. É um modelo de extrema importância pois é um modelo de base, e será utilizado para ter seu erro comparado com os demais métodos.
      
   - [x] `Método`: Regressão Linear
      * Também é um modelo simples e é fácil de ser analizado, pois traça apenas uma linha sobre os dados. Ainda terá um erro menor que o modelo baseline, pois haverá dados onde o modelo estará bem ajustado.
      
   - [x] `Método`: K-NN vizinhos
      * Este já é um modelo de mais precisão e confiabilidade, e é relativamente simples de se entender, pois seu método relaciona que dados similares ocupam regiões próximas umas das outras. Neste método, podem ser definidos hiperparâmetros que podem auxiliar na diminuição do erro, tornando o método mais eficiente.
      
   - [x] `Método`: Árvore de Decisão
      * Árvores de decisão são como grafos, possuindo vértices como sua raiz, decisão de vértices, e folhas. Nos vértices raiz e de decisão, condicionais são aplicados, gerando um valor de resultado nos vértices de folha. Este método gera um modelo mais fácil de ser explicado do que melhor performance de aprendizagem de máquina, pois os passos realizados para ser feita a previsão são bem explícitos. Também possui hiperparâmetros que podem ser alterados para se diminuir o erro, como o número de ramificações e o número de folhas.
      
   - [x] `Método`: Floresta Aleatória
      * Florestas aleatórias são conjuntos de árvores de decisão, onde cada árvore de decisão irá realizar uma previsão, e comparando as decisões, o valor mais retornado será dado como a previsão final do algorítmo. O processo é aleatório pois o processo de se construir as árvores de decisão que compõem esta floresta envolve amostras dos exemplos e dos atributos. É um modelo impreciso que funciona bem com dados que lhe foram passados, mas não é flexível para trabalhar com novas amostras de dados. Além dos mesmos hiperparâmetros do modelo de Árvore de Decisão, temos o hiperparâmetro conhecido como **num_estimators**, que irá definir a quantidade de árvores de decisão que constituirão nossa floresta. Podemos definir a importância de um atributo a partir de **impureza**, que representam o quão bem os dados são divididos entre as árvores, e pelas árvores, sendo utilizado para a indução de árvores de decisão sem ser necessário o teste de todas as possibilidades.
      
   - [x] `Classificação`:
      * A classificação consiste na separação de dados em grupos, e a partir destes treinar o modelo para classificar os itens destes grupos, que já possuem classes pré-definidas. Logo, é um processo semelhante à regressão, só que invés de termos os valores pré-definidos, temos as classes.
      Os modelos de classificação podem ser aplicados aos métodos anteriores para treinarmos o algorítimo, como o método _K-nn_ mas não prevendo valores e sim classes/grupos
      
   - `API`: Redução de dimensionalidade
   - `API`: Agrupamento (clustering)
   - `API`: Detecção de outliers

   * [Como usar](#como-usar)
      * [Instalação](#instalacao)
      * [Pre Requisitos](#pre-requisitos)
      * [Local files](#local-files)
      * [Remote files](#remote-files)
      * [Multiple files](#multiple-files)
      * [Combo](#combo)
   * [Resultados](#resultados)
<!--te-->

## Colaboradores✨
<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
<table>
  <tr>
    <td align="center"><a href="https://github.com/TiagoMarquesHxH"><img src="https://avatars.githubusercontent.com/u/106617887?v=4" width="100px;" alt=""/><br /><sub><b>Tiago Marques</b></sub></a><br />Programmer</td>
    <td align="center"><a href="https://github.com/Gbeneti"><img src="https://avatars.githubusercontent.com/u/107064808?v=4" width="100px;" alt=""/><br /><sub><b>Gustavo Beneti</b></sub></a><br />Programmer</td>
    <td align="center"><a href="https://github.com/CaioHubit"><img src="https://avatars.githubusercontent.com/u/110487580?v=4" width="100px;" alt=""/><br /><sub><b>Caio Eduardo</b></sub></a><br />Programmer</td>
    <td align="center"><a href="https://github.com/raphaella220046"><img src="https://avatars.githubusercontent.com/u/107066990?v=4" width="100px;" alt=""/><br /><sub><b>Raphaella Tamyres</b></sub></a><br />Programmer</td>
  </tr>
</table>


Tabela de Funções
=================
   * Caio Eduardo Palatin de Souza (Programador: Docstring, Organização, Construção do método de clustering hierárquico).
   * Gustavo Alves Beneti (Programador: Terminou a Floresta, Comparação de Desempenho e Classificação, Agrupamento K-means, Análise PCA).
   * Raphaella Tamyres Siqueira (Programadora: Construção da regressão Florestas aleatórias e Detecção de outliers (Isolation Forest e Local Outlier Factor).
   * Tiago Marques (Programador: Regressão Linear, Baseline e K-NN, Splitting dos dados de treino e teste, PCA para Regressão com Florestas aleatórias, Método de clustering hierárquico).
<!-- markdownlint-enable -->

## Mentores✨
<!-- ALL-MENTORES-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
<table>
  <tr>
    <td align="center"><a href="https://github.com/drcassar"><img src="https://avatars.githubusercontent.com/u/9871905?v=4" width="100px;" alt=""/><br /><sub><b>Daniel R. Cassar</b></sub></a><br />Professor</td>
    <td align="center"><a href="https://github.com/jamesmalmeida"><img src="https://avatars.githubusercontent.com/u/108157661?v=4" width="100px;" alt=""/><br /><sub><b>James Moraes de Almeida</b></sub></a><br />Professor</td>
  </tr>
</table>
<!-- markdownlint-enable -->
