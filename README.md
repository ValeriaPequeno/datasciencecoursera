# data science (coursera) Quarentena de Dados
[Aula 1](#Aula-1) [Aula-2](#Aula-2) [Aula 3](#Aula-3) [Aula 4](#Aula-4) [Aula 5](#Aula-5)   

## Aula 1
### Objetivos
Nesta aula vamos realizar nossa primeira análise de dados e no final já seremos capazes de tirar algumas conclusões.
### Introdução
Nós estaremos desenvolvendo nosso projeto aqui no google colaboratory, assim podemos mesclar células contendo textos em formato markdown e células de código, além disso você não precisar instalar nada na sua máquina. Então que tal começar testando algumas linhas de código.

Nesta primeira célula estamos realizando um print(), lembre-se que esta função python imprime a string que estamos passando como parâmetro, então o retorno é exibido logo abaixo da célula com código.
```
Nesta primeira célula estamos realizando um print(), lembre-se que esta função python imprime a string que estamos passando como parâmetro, então o retorno é exibido logo abaixo da célula com código.
print("Guilherme Silveira")
print("Paulo Silveira")

Guilherme Silveira
Paulo Silveira
```
Agora vamos analisar a proxima célula de código.

Aqui estamos fazendo uma atribuição de variável, conforme dito em aula, as atribuições não tem retorno, assim, diferente da célula anterior não temos um output logo abaixo do código.
```
print(nome_do_filme)
Totoro, o filme
```
```
nome_do_filme
'Totoro, o filme'
```
### Lendo os dados do MovieLens
Nosso primeiro passo foi conhecer e realizar um "hello-world" no colab, agora chegou a hora de importar os dados para o notebook e começar as análises.

Vamos importar a biblioteca [pandas](https://pandas.pydata.org/), um poderoso projeto open source para análise de manipulação de dados. O primeiro passo é ler uma base de dados e podemos fazer isso com o comando pd.read_csv().

Estamos lendo um arquivo CSV (Comma-separated values), neste tipo de arquivo os valores são separados por vírgulas e podem ser abertos em outras ferramentas como excel e google-sheet. CSV não é o único formato lido pelo pandas, temos o pd.read_excel() que lê arquivos xlsx entre diversos outros formatos, você pode encontrar mais informações na seção de [input/output da documentação](https://pandas.pydata.org/pandas-docs/stable/reference/io.html).

Depois de ler o dataset, nós trocamos os nomes das colunas pelos termos em português, logo em seguida utilizamos o método filmes.head() para visualizar as primeiras 5 linhas do nosso dataframe. Outra forma de visualizar as informações dos dados é utilizando o método filmes.sample(), se você tentar, vai verificar que ele retorna uma linha aleatória do seus dados. Para escolher aleatoriamente mais de 1 linha, por exemplo 5, é só passar esse valor desejado como parâmetro (filmes.sample(5)).
```
import pandas as pd
```
```
filmes = pd.read_csv("https://raw.githubusercontent.com/alura-cursos/introducao-a-data-science/master/aula0/ml-latest-small/movies.csv")
# filmes é um DataFrame
filmes.columns = ["filmeId", "titulo", "generos"]
filmes.head()
```
Há pouco falamos para consultar a documentação para obter mais informações, mas será que é realmente preciso sair do notebook para tirar algumas dúvidas mais simples?

Os notebooks facilitam a nossa vida podendo consultar o docstring das funções e métodos, rodando a célula com um ? na frente da chamada, uma view é aberta com as informações resumidas. Veja a seguir alguns exemplos.
## Aula 2
## Aula 3
## Aula 4
## Aula 5
