<h1 align="center"> Aprendizado de Máquina </h1>

<p align="center">
<img src="http://img.shields.io/static/v1?label=STATUS&message=EM%20DESENVOLVIMENTO&color=GREEN&style=for-the-badge"/>
</p>

Sobre
=================

<h3>Esse é um projeto que visa o aprendizado de máquina(Machine Learning), portanto foi feito em prol didático. Feito por um grupo de 4 estudantes da Ilum   Escola de Ciência.</h3>

O projeto se baseia na adquirição de um dataset de interesse dos mais diversos bancos de API's existentes, para que possamos construir um algorítmo que aprenda sobre os dados e possa prever um alvo que lhe foi passado. A máquina, a partir do algorítmo implantado, irá se basear em diversos métodos para tentar encontrar semelhanças e correlações entre os dados, podendo assim retornar um valor aproximado ao nosso alvo. Também são analisados os erros entre os dados originais e a previsão do modelo, com gráficos deixando mais visíveis estas margens de erro.
O dataset que escolhemos foi o *Minerals Database*, que contém diversos tipos de minerais e suas propriedades fisico-químicas, onde nossa finalidade é de prever através do algorítmo de aprendizagem de máquinas o *índice de refração* de um mineral baseado em suas outras propriedades.


**Bibliotecas utilizadas no projeto**

`pandas, sklearn, seaborn, matplotlib, numpy, scipy, statsmodels, itertools, lmfit`

Tabela de Conteudo
=================
- [x] **Bloco 1: DataBase (Coleta e Preparação)**
   
  * O primeiro bloco consiste na escolha do dataset a ser utilizado, na coleta dos dados deste dataset, sua conversão para um Dataframe e seu ajuste (remoção de dados incompletos, nulos e NaN e conversão de dados categóricos). É uma etapa de extrema importância pois assim utilizaremos apenas os dados necessários e relevantes para conseguirmos realizar a previsão de nosso alvo.
  * Utilizamos a correlação de Pearson e de Spearman para visualizarmos como os dados se correlacionam
  ![Pearson](https://github.com/TiagoMarquesHxH/ImagensML/blob/main/Pearson.png?raw=true )
  ![Spearman](https://github.com/TiagoMarquesHxH/ImagensML/blob/main/Spearman.png?raw=true)

- [x] **Bloco 2: Métodos de regressão**

  * Neste segundo bloco, iremos testar a eficiência do nosso modelo de previsões para identificarmos se possuímos de fato um bom modelo. Para um modelo bom, o viés e variância dos dados originais com os previstos devem ser equilibrados. Definem-se, então, os atributos que serão utilizados para a previsão do nosso alvo, e em seguida, é realizada a divisão deste Dataframe em dados de treino e teste, para que o computador possa realizar previsões do alvo que queremos prever, baseado no conjunto de dados treino. Após esta divisão, podemos treinar nosso algoritmo com diversos métodos de regressão, definir conjuntos de hiperparâmetros (que são atributos dos métodos que podemos alterar, a fim de uma melhora do treinamento do modelo), e para alguns casos realizar a normalização logarítmica ou escalonada. Por fim, análises estatísticas dos dados (variância, média, moda, desvio padrão, etc...), métricas de erros como RMSE e Quadrados Mínimos, e graficações, são computadas para melhor entendimento do comportamento dos dados que serão utilizados. 
   - **Modelos de regressão supervisionados:**
   - [x] `Método`: Baseline (Dummy Regressor)
      * Modelo mais simples, que realiza a previsão da média dos valores do target. É um modelo de extrema importância pois é um modelo de base, e será utilizado para ter seu erro comparado com os demais métodos.
      * Aplicando este método em nosso dataset, foi retornado um RMSE de 0.669 para o target de índice refrativo, o que era de se esperar pois este modelo apenas seleciona um dado aleatoriamente para tomar como base.
      
   - [x] `Método`: Regressão Linear
      * Também é um modelo simples e é fácil de ser analizado, pois traça apenas uma linha sobre os dados. Ainda terá um erro menor que o modelo baseline, pois haverá dados onde o modelo estará bem ajustado.
      * Quando aplicado em nosso dataset, vimos que o RMSE foi de 0.363, mostrando uma melhora no treino.
      ![Regressão linear aplicada ao Dataset](https://github.com/TiagoMarquesHxH/ImagensML/blob/main/regressao.png?raw=true)
      
   - [x] `Método`: K-NN vizinhos
      * Este já é um modelo de mais precisão e confiabilidade, e é relativamente simples de se entender, pois seu método relaciona que dados similares ocupam regiões próximas umas das outras. Neste método, podem ser definidos hiperparâmetros que podem auxiliar na diminuição do erro, tornando o método mais eficiente.
      * Alterando apenas o hiperparâmetro de vizinhos _k_, o RMSE aumentava conforme _k_ era maior
      `k = 5 --> RMSE: 0.487`
      `k = 20 --> RMSE: 0.567`
      `k = 200 --> RMSE: 0.661`
      * O que sugere fortemente que os dados mais relacionados se encontram próximos
      ![Como o número de vizinhos K afeta o RMSE](https://github.com/TiagoMarquesHxH/ImagensML/blob/main/knn.png?raw=true)
      * Definindo um conjunto de hiperparãmetros que leva em consideração a definição de visinhos mais próximos terem maior peso, vimos que um número de K vizinhos ideal seria em torno de 5, pois apresentou menor RMSE de 0.469
      ![Número ideal de K-vizinhos](https://github.com/TiagoMarquesHxH/ImagensML/blob/main/kideal.png?raw=true)
      
   - [x] `Método`: Árvore de Decisão
      * Árvores de decisão são como grafos, possuindo vértices como sua raiz, decisão de vértices, e folhas. Nos vértices raiz e de decisão, condicionais são aplicados, gerando um valor de resultado nos vértices de folha. Este método gera um modelo mais fácil de ser explicado do que melhor performance de aprendizagem de máquina, pois os passos realizados para ser feita a previsão são bem explícitos. Também possui hiperparâmetros que podem ser alterados para se diminuir o erro, como o número de ramificações e o número de folhas.
      * Foram analisados a influência de alguns hiperparâmetros considerados relevantes no RMSE
      ![Influência do número de folhas](https://github.com/TiagoMarquesHxH/ImagensML/blob/main/arvfolhas.png?raw=true)
      ![Profundidade](https://github.com/TiagoMarquesHxH/ImagensML/blob/main/arvprofundidade.png?raw=true)
      ![E S-Split](https://github.com/TiagoMarquesHxH/ImagensML/blob/main/arvssplit.png?raw=true)
      * E, a partir desta análise, foi montado um conjunto de hiperparâmetros contendo 5 folhas, 5 de profundidade, e 55 S-Split, resultando em um RMSE de 0.358
      
   - [x] `Método`: Floresta Aleatória
      * Florestas aleatórias são conjuntos de árvores de decisão, onde cada árvore de decisão irá realizar uma previsão, e comparando as decisões, o valor mais retornado será dado como a previsão final do algorítmo. O processo é aleatório pois o processo de se construir as árvores de decisão que compõem esta floresta envolve amostras dos exemplos e dos atributos. É um modelo impreciso que funciona bem com dados que lhe foram passados, mas não é flexível para trabalhar com novas amostras de dados. Além dos mesmos hiperparâmetros do modelo de Árvore de Decisão, temos o hiperparâmetro conhecido como **num_estimators**, que irá definir a quantidade de árvores de decisão que constituirão nossa floresta. Podemos definir a importância de um atributo a partir de **impureza**, que representam o quão bem os dados são divididos entre as árvores, e pelas árvores, sendo utilizado para a indução de árvores de decisão sem ser necessário o teste de todas as possibilidades.
      * Para este método, foi observado que não havia uma relação consistente da interferência dos hiperparâmetros de N° de folhas e N° de árvores com o RMSE, mas os hiperparâmetros de _Valor mínimo de split_ e _Valor mínimo de folhas mostraram que há uma redução no RMSE conforme estes aumentam, retornando um RMSE de 0.3475
      
      
   - [x] `Classificação`:
      * A classificação consiste na separação de dados em grupos, e a partir destes treinar o modelo para classificar os itens destes grupos, que já possuem classes pré-definidas. Logo, é um processo semelhante à regressão, só que invés de termos os valores pré-definidos, temos as classes.
      Os modelos de classificação podem ser aplicados aos métodos anteriores para treinarmos o algorítimo, como o método _K-nn_ mas não prevendo valores e sim classes/grupos

- [x] **Bloco 3 - Aprendizado de máquina não-supervisionado**

   * No terceiro bloco, realizamos a aprendizagem não-supervisionada dos nossos dados, um método que não exige dados rotulados para que possamos analisá-los.
   Este tipo de aprendizagem envolve métodos como Clusterizações dos dados, Reduções de suas dimensionalidades e a detecção de outliers, que serão explicados abaixo.

   - [x] `Método`: Redução de dimensionalidade (PCA)
      
      * Quando dados são agrupados, formando clusters, podemos ter uma visualização de como estes dados se relacionam, mas em muitas das vezes, se temos muitos dados estes agrupamentos se tornam difícieis de serem visualizados. Para evitar esta dificuldade, seria necessário reduzir a dimensão do sistema, ou seja, combinar vários atributos e visualizar este gráfico em três dimensões. Para isso, podemos realizar uma análise dos componentes principais do conjunto de dados, conhecido também como PCA.
     * A redução de dimensionalidade do PCA se baseia em uma matriz onde as colunas são os atributos, estes são normalizados e desta matriz é obtida a matriz de covariância. Após isso, a matriz é diagonalizada e então os autovetores dos maiores autovalores são multiplicados pela matriz de atributos que foi escolhida inicialmente, fazendo assim a redução de dimensão.
     * Foram escolhidos 5 Features principais, retornando um gráfico como:
      ![PCA com 5 Features](https://github.com/TiagoMarquesHxH/ImagensML/blob/main/pca5ft.png?raw=true)
      
   - [x] `Método`: Clustering K-means
      
        Este método utiliza as médias e variância de cada cluster para conseguir reconhecer cada grupo, e para isso, o algorítimo seleciona 3 pontos quaisquer dos dados, com __n__ centroides iniciais. Então, a partir do cálculo da distância de cada ponto com cada centróide, o que ele tiver menor distância Euclidiana ao quadrado, será o cluster o qual ele será atribuido. Este processo será realizado com novos centróides para cada cluster, a partir da posição de todos os pontos atribuido a cada centróide.
      Podemos identificar o número de clusters ideais através do Within-Cluster-Sum of Squared Errors (WSS) que calcula a distância entre todos os pontos do cluster com todos os outros pontos do cluster, mostrando o quão compacto ele é.
    - [x] `Método`: Clustering Hierárquico
        
        * Este método de agrupamento de dados consiste em unir pares de dados usando uma distância de linkagem. A análise gráfica foi realisada pela plotagem de um dendrograma. Um dendrograma é uma estrutura em formato de árvore, que explica a relação entre cada ponto de dado de um Dataset
        ![Cluster hierárquico](https://github.com/TiagoMarquesHxH/ImagensML/blob/main/HIERARQUIA.png?raw=true)
   
   - [x] `Método`: Valores anômalos
      
      * Em um conjunto de dados, podemos ter valores que estão "fora da reta", ou seja, diferenciando-se do comportamento dos outros dados. Estes tipos de valores são chamados de valores anômalos, que podem atrapalhar a aplicação do modelo para casos mais gerais pois aparentam ser inconsistentes.
      Podemos detectar estes valores para sua análise através de duas estratégias de detecção, onde uma consiste na identificação de valores anômalos dentro de um conjunto já existente (detecção de outliers), e outro na identificação de valores anômalos em dados novos com relação a um conjunto já existente (detecção de novidade).
      Existem algorítimos que implementam esta detecção em dados, e o primeiro deles é o algorítimo **Local Outlier Factor (LOF)**, que realiza o cálculo a distância entre os pontos para detectá-los, semelhante ao método K-NN.
      O segundo dos algorítimos é o Isolation Forest (IF), que, utilizando uma floresta de árvores de decisão, realiza a detecção. Este algorítimo parte da ideia que é mais fácil de se isolar um valor anômalo que valores não-anômalos.
      As árvores desta floresta irão isolar todos os pontos do conjunto de dados, ou seja, cada folha da árvore terá somente uma amostra do dataset ou amostras iguais, ou até mesmo nenhuma amostra.

- [x] Bloco 4: Validação Cruzada
   
   * A validação cruzada se baseia em encontrar um bom conjunto de hiperparâmetros para se treinar um modelo. Também se utiliza uma parte dos dados de treino para a validação deste, a fim de ser obtido uma estatística do processo de validação.
   
   - [x] `Validação`: K-fold
      
      * Neste método de validação, o conjunto de treino dos dados é dividido em _k_ conjuntos de dados de tamanho igual, e assim, este modelo será treinado um número _k_ de vezes, com cada treino sendo realizado com k-1 dos conjuntos de dados. Ao final, é medido a performance do modelo no conjunto de validação (parte do conjunto de treino não utilizado no processo de treino).
      Com a validação cruzada, algorítimos diferentes ou com cconjuntos de hiperparâmetros diferentes podem ser comparados a fim de encontrarmos aqueles com as melhores métricas.
      Após este processo, treinamos um modelo semifinal, que envolve a utilização do algorítimo com melhor métrica e todo o conjunto de dados de treino, e através deste modelo, conseguiremos prever os dados de teste.
      Se após a análise do modelo semifinal tivermos dados aceitáveis, podemos partir para a montagem do modelo final, onde utilizaremos todos os dados de treino e teste, e através deste, será possível realizar a previsão para qualquer dataset.

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
   * Tiago Marques (Programador: Regressão Linear, Baseline e K-NN, Splitting dos dados de treino e teste, PCA para Regressão com Florestas aleatórias, Método de clustering hierárquico, Desenvolvimento e Edição do README).
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
