<h1 align="center"> Aprendizado de Máquina </h1>

<p align="center">
<img src="http://img.shields.io/static/v1?label=STATUS&message=EM%20DESENVOLVIMENTO&color=GREEN&style=for-the-badge"/>
</p>

Sobre
=================

<h3>Esse é um projeto que visa o aprendizado de máquina(Machine Learning), portanto foi feito em prol didático. Feito por um grupo de 4 estudantes da Ilum   Escola de Ciência.</h3>

O projeto se baseia na adquirição de um dataset de interesse dos mais diversos bancos de API's existentes, para que possamos construir um algorítmo que aprenda sobre os dados e possa prever um alvo que lhe foi passado. A máquina, a partir do algorítmo implantado, irá se basear em diversos métodos para tentar encontrar semelhanças e correlações entre os dados, podendo assim retornar um valor aproximado ao nosso alvo.
O dataset que escolhemos foi o *Minerals Database*, que contém diversos tipos de minerais e suas propriedades fisico-químicas, onde nossa finalidade é de prever através do algorítmo de aprendizagem de máquinas o *índice de refração* de um mineral baseado em suas outras propriedades.

Tabela de Conteudo
=================
- [x] **Bloco 1: DataBase (Coleta e Preparação)**
   
  * O primeiro bloco consiste na coleta dos dados, sua conversão para um Dataframe e seu ajuste (remoção de dados incompletos, nulos e NaN e conversão de dados categóricos). Definem-se, então, os atributos que serão utilizados para a previsão do nosso alvo, e em seguida, é realizada a divisão deste Dataframe em dados de treino e teste, para que o computador possa realizar previsões do alvo que queremos prever, baseado no conjunto de dados treino. Por fim, análises estatísticas dos dados (variância, média, moda, desvio padrão, etc...) e graficações são computadas para melhor entendimento do comportamento dos dados que serão utilizados.

- [x] **Bloco 2: Métodos de regressão**
   - `Método`: K-NN vizinhos
   - `Método`: Regressão Linear
   - `Método`: Árvore de Decisão
   - `Método`: Floresta Aleatória
   - `API`: Classificação
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
