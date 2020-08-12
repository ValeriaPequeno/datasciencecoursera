# data science (coursera) Quarentena de Dados
[Inicio](#O-que-precisamos)[Aula 1](#Aula-1) [Aula-2](#Aula-2) [Aula 3](#Aula-3) [Aula 4](#Aula-4) [Aula 5](#Aula-5)   
## O que precisamos
Não será preciso fazer qualquer intalação na máquina
Você só precisa acessar o google collaboratory e desenvolver seu projeto.
Para ver os exercícios e todo o conteúdo que foi dado em aula siga os seguites passos:

* Acesse o [notebook da aula01](https://colab.research.google.com/drive/1p69W-kfloWqslpLqwmaOV2GTsqaeWyi0). (Se o link estiver quebrado, acesse [Aula 1](#Aula-1)).
* Na parte superior esquerdo, clique em >File, logo depois em >Save a copy in Drive.
* Se você não estiver logado em uma conta gmail, um pop-up solicitará que você crie ou faça login de em uma conta google.
* Feito o login uma cópia da aula é criada em seu drive (pasta Colab Notebook, criada automaticamente).
* Abra o notebook e boa diversão.

Links das base de dados:

* Base com [títulos e generos do Movie Lens](https://raw.githubusercontent.com/alura-cursos/introducao-a-data-science/master/aula0/ml-latest-small/movies.csv).
* Base de [notas do Movie Lens](https://raw.githubusercontent.com/alura-cursos/introducao-a-data-science/master/aula0/ml-latest-small/ratings.csv).
* Base [IMDB 5000](https://gist.githubusercontent.com/guilhermesilveira/24e271e68afe8fd257911217b88b2e07/raw/e70287fb1dcaad4215c3f3c9deda644058a616bc/movie_metadata.csv).
* Base com [dados do ENEM](https://raw.githubusercontent.com/guilhermesilveira/enem-2018/master/MICRODADOS_ENEM_2018_SAMPLE_43278.csv).
* Estes ficheiros também estão disponíveis localmente na pasta: data

Alguns lembretes e dicas:

* Se tiver dificuldades ao utilizar o Colab, acesse este [artigo da Alura](https://www.alura.com.br/artigos/google-colab-o-que-e-e-como-usar).
* No site do [Movie Lens](https://grouplens.org/datasets/movielens/) você encontra a base completa de filmes.
* No site do [INEP](http://portal.inep.gov.br/web/guest/microdados) você encontra a base completa dos dados do ENEM.
* Faça os desafios deixados no final de cada aula.

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
```
#lendo a documentação de um método/atributo
?filmes.head
```
```
#lendo a documentação do tipo (docstring)
?filmes
```
A base de dados que usamos até o momento contém o nome do filme, ano de lançamento e gêneros. O MovieLens conta com outras informações que estão em bases separadas, uma delas é a de avaliações.

Agora vamos analisar um pouco melhor o dataset de avaliações.
```
avaliacoes = pd.read_csv(filmes = ("https://github.com/alura-cursos/introducao-a-data-science/blob/master/aula0/ml-latest-small/ratings.csv?raw=true")
avaliacoes.head()
)
```
Para visualizar algumas linhas estamos usando o .head(), como ela mostra apenas as 5 primeiras linhas não sabemos qual é a quantidade de linhas que temos. Para descobrir a "forma" dos nossos dados podemos utilizar o avaliacoes.shape, retornando uma [tupla](https://www.alura.com.br/artigos/conhecendo-as-tuplas-no-python), onde o primeiro termo indica o número de linhas e o segundo o número de colunas.
```
avaliacoes.shape
```
```
len(avaliacoes)
```
Vamos substituir os nomes das colunas de inglês para português e entender o que são essas colunas.

usarioId => ID para para usuário que votou em determinado filme.

filmeId => ID para identificar um filme votado.

nota => A nota dada para pelo usuário para o respectivo filme.

momento => A data da votação que não está formatada como data

Como cada linha contém um voto para o respectivo filme é de se esperar que um filme tenha diversos votos, mas repare que nas 5 primeiras linhas temos o filme 1, 3, 6, 47, 50. Mas e se eu quiser analisar apenas as notas do filme 1, como posso separar essa informação?
```
avaliacoes.columns = ["usuarioId","filmeId","nota","momento"]
avaliacoes.head()
```
Uma forma para "separar" as informações apenas do filmeId 1 é chamando o método avaliacaoes.query("filmeId==1"), esse método retornará apenas as linhas para quais a expressão booleana, "filmeId==1", for verdadeira.

Tendo as informações do filmeId 1 podemos chamar o avaliacoes_do_filme_1.describe(), para analisar as estatítiscas gerais dos dados.
```
avaliacoes_do_filme_1 = avaliacoes.query("filmeId==1")
avaliacoes_do_filme_1.head()
```
```
avaliacoes_do_filme_1.describe()
```
Caso queira uma estatística particular, podemos apenas chamar o método desajado, repare abaixo como calculamos apenas a média das avaliações do filmeId 1.
```
avaliacoes_do_filme_1.mean()
```
Calculamos as estatísicas apenas para o filmeId 1, mas também podemos chamar o método .describe() para a base completa (avaliacões).
```
avaliacoes.describe()
```
Ok, nós calculamos um tanto de coisa usando .describe() e .mean(), mas a informação que realmente queremos é a média da nota. Então o ponto é, como calcular a média apenas das notas?

A primeira coisa que precisamos fazer é selecionar apenas as informações de notas. Usando uma estrutura muito parecida com a de [chave-valor dos dicionários python](https://www.alura.com.br/artigos/trabalhando-com-o-dicionario-no-python).

Com o comando avaliacoes["nota"], obtemos os valores da coluna nota (repare que o tipo retornado é uma Série pandas, por isso o index de cada nota é mantido). Para calcular a média de todas as notas executamos avaliacoes["notas"].means()
```
avaliacoes["nota"]
```
```
avaliacoes["nota"].mean()
```
Podemos calcular também na nota média do filmeId 1, repare que o resultado é um pouco maior que a geral. Apenas com essa análise não da para bater o martelo que o filme 1 é acima da média, mas apenas com essa análise conseguimos formular uma primeira hipótese!
```
avaliacoes_do_filme1["nota"].mean()
```
Nós calculamos uma média geral, uma média para o filmeId 1. Agora eu quero calcular a média das notas para todos os filmes, podemos fazer isso usando o método .groupby(filmeId), o parâmetro passado é para indicar qual coluna ele deve utilizar para "agrupar" os dados. Depois só calcular a média como fizemos anteriormente.
```
notas_medias_por_filme = avaliacoes.groupby("filmeId")["nota"].mean()
notas_medias_por_filme.head()
```
Temos as notas médias calculadas, mas agora precisamos juntar as informações de notas médias com a base de dados filmes.

Poderíamos criar uma nova coluna e atribuir a váriável notas_medias_por_filme, de forma direta:
```
filmes["nota_media"] = notas_medias_por_filme
```
Como discutimos em aula, essa não é uma boa prática pois precisamos garantir que a nota média seja do respectivo filme.

Para garantir essa condição vamos utilizar o .join(), criando um novo dataframe (filmes_com_media = filmes.join(notas_medias_por_filme, on="filmeId")).

Veja como fazer, nas células a seguir.
```
filmes
```
```
notas_medias_por_filme
```
```
filmes_com_media = filmes.join(notas_medias_por_filme, on="filmeId")
filmes_com_media.head()
```
Agora que temos as médias, que tal visualizar o nosso dataframe ordenado pela nota de forma decrescente?

```
filmes_com_media.sort_values("nota", ascending=False).head(15)
```
Fizemos um tanto de análise e manipulação de dados interessante, não é?

Mas diz a verdade, você está sentindo falta daquele gráfico que todo cientista de dados adora =D, então bora plotar nosso primeiro gráfico!

O pandas facilita muito o plot de alguns gráficos simples, apenas selecionamos a informação que gostaríamos de visualizar e chamamos o método .plot()
```
avaliacoes.query("filmeId==1")["nota"].plot()
```
Por padrão o método plotou um gráfico de linhas, o que não é adequado para os dados que estamos analisando.

Precisamos mudar o tipo de gráfico para realizar uma análise mais adequada, para fazer isso apenas alteramos o parâmetro kind do método .plot. Vamos plotar um [histograma](https://pt.wikipedia.org/wiki/Histograma) rodando a célula a seguir.
```
avaliacoes.query("filmeId==1")["nota"].plot(kind='hist')
```
Legal, agora temos uma visualização muito mais agradavel de analisar. Compare com o gráfico de linhas, qual você acha melhor para análise?

P.S: Deixar de usar o gráfico de linhas, não significa que sejá uma visualização ruim. Apenas quer dizer que nossos dados não tem características ideias para serem visualizados como um line plot, agora pense em uma [série temporal](https://pt.wikipedia.org/wiki/S%C3%A9rie_temporal). Você acha que o gráfico de linhas ainda seria uma má ideia?

Antes de analisar o histograms de outros filmes, quero colocar um título na imagem. Vamos ver como podemos fazer isso!
```
avaliacoes.query("filmeId==1")["nota"].plot(kind='hist',title="Avaliações do filme Toy Story")
```
Claro que python tem outras ferramentas muito poderosas para manipular gráficos, uma delas é o [matplotlib](https://matplotlib.org/).

Que tal experimentar um pouquinho esta poderosa ferramenta?

Vamos importar a lib e adicionar título no gráfico usando o matplotlib, veja como fica na célula a seguir.
```
import matplotlib as plt

avaliacoes.query("filmeId == 1")["nota"].plot(kind='hist')
plt.title("Avaliações do filme Toy Story")
plt.show()
```
Agora que aprendemos a criar um histograma e manipular os gráficos, vamos plotar informações de outros filmes e realizar uma análise desses gráficos?

Vamos plotar o histograma do filme Jumanji e da animação Liga da justiça: Doom.
```
avaliacoes.query("filmeId == 2")["nota"].plot(kind='hist')
plt.title("Avaliações do filme Jumanji")
```
```
avaliacoes.query("filmeId == 102084")["nota"].plot(kind='hist')
plt.title("Avaliações do filme Justice League: Doom")
```
Agora que temos os gráficos, chegou a hora de analisar.

A primeira coisa que preciso saber é o que cada eixo do meu gráfico significa. Então, eixo **x** mostra a nota, enquanto eixo **y** a frequência das notas (quantas vezes determinada nota foi dada).

Entendido nosso gráfico, vamos contextualizar o cenário que estamos analisando:

Temos 3 filmes, dois muito populares (Toy story e Jumanji) e outro que nenhuma pessoa presente no momento da aula conhecia (animação da liga da justiça). O ponto que chamou a atenção, foi que a animação tinha média de nota maior que dois filmes, aparentemente mais popular, Jumaji e Toy Story. **Será que a animação é um filme tão bom assim?**
Dado esse cenário a primeira coisa que me chama a atenção é a animação da liga da justiça ter média de nota igual a 5. Ao analisar o histograma do respectivo filme, verificamos que ele só teve uma avaliação igual a 5, logo, fica evidente que a **quantidade de votos é um aspecto importante na avaliação das médias**. Com apenas uma avaliação, não conseguimos garantir que o filme é realmente bom, tornando a avaliação muito "volátil". Imagina que Liga da Justiça receba mais uma avaliação, com nota 0, assim a média seria 2.5. Apenas com mais essa avaliação o filme passaria a ser considerada um "pior" que Jumanji e Toy Story.

Outro ponto interessante é comparar o histograma de Toy Story e Jumanji, ambos tem médias "relativamente próximas". Mas repare que a distribuição de notas são diferentes, Toy Story recebe mais notas 5 e 4 que qualquer outra nota, enquanto Jumanji recebe mais notas 4 e 3, assim concluímos que a **distribuição das notas também é um fator importante na avaliação das médias**.(Se ficar alguma dúvida sobre esse tema reveja o exemplo que o instrutor apresenta no final na aula)

Com isso nós fechamos a nossa primeira aula do **#quarentenadados**, viu quanta coisa aprendemos? Que tal colocar isso em prática?

**Crie seu próprio notebook, reproduza nossa aula e resolva os desafios que deixamos para vocês.**

Até a próxima aula!
### Desafios
#### Desafio 1 (do Paulo Silveira)
O Paulo fez uma análise rápida e disse que tem 18 filmes sem avaliações, será que ele acertou?

Determine quantos filmes não tem avaliações e quais são esses filmes.
#### Desafio 2 (do Guilherme Silveira)
Mudar o nome da coluna nota do dataframe filmes_com_media para nota_média após o join
#### Desafio 3 (do Guilherme Silveira)
Colocar o número de avaliações por filme, isto é, não só a média mas o TOTAL de votos por filme.
#### Desafio 4 (do Thiago Gonçalves)
Arredondar as médias (coluna de nota média) para duas casas decimais.
#### Desafio 5 (do Allan Spadini)
Descobrir os generos dos filmes (quais são eles, únicos). (esse aqui o bicho pega)
#### Desafio 6 (do Thais André)
Contar o número de aparições de cada genero.
#### Desafio 7 (do Guilherme Silveira)
Plotar o gráfico de aparições de cada genero. Pode ser um gráfico de tipo igual a barra.
## Aula 2
## Aula 3
## Aula 4
## Aula 5
