# DIO-adb notebook exercise
Exercise of DIO Azure DataBricks course

# Introdução
No Microsoft Learn existe varios exercicios, como por exemplo o "Exlpore Azure DataBricks", 
como a imagem abaixo:
<img src="img/exercise1.png">

Nesse exercicio foi carregado um ficheiro "producs.csv" para o catalog, e no notebook em uma das celulas fizemos 
uma consulta SQL, e criamos uma visualização com o resultado.  
Na outra célula foi carregado um dataframe, e executada uma operação de filtro.   
  
Agora iremos fazer o Exercicio: https://microsoftlearning.github.io/mslearn-databricks/Instructions/Exercises/LA-02-Explore-data.html  

#  Criando o Cluster

<img src="img/create-cluster.PNG">
No DataBricks comunity é mais simplificado as opções disponiveis para criar um Cluster, basicamente nome, versão, e podendo adicionar algumas configurações adicionais do spark.  
Mas, no Azure DataBricks temos mais opções relevantes a preencher, como por exmplos:  

Policy: Unrestricted
Cluster mode: Single Node
Access mode: Single user (with your user account selected)
Use Photon Acceleration: Selected
Node type: Standard_D4ds_v5
Terminate after 20 minutes of inactivity

Estas opções definirão o comoportamento do cluster, como opção "Single Node" útil para pequenos projectos, e custer de desenvolvimento pois todo spark rodara em apenas um nó tendo um desempenho baixo para volumes grande ou analíse complexas.  
Também a última das opções define um tempo de desligamento a pois inatividade do cluster, evitando custo com o cluster activo sem uso.  

<img src="img/confgure-cluster.PNG">
A pois o cluster criado podemos rever e alterar, algumas definições.  

#  Importandos os ficheiros
<img src="img/confgure-cluster.PNG">
existem diversas formas de importar ficheiro csv, neste exercicio temos três url de ficheiro url:  
O primeiro foi importado pelo Pandas e depois convertido em dataframe do spark,
os outros via spark, mas com sintaxe ligeiramente diferente. Poderias-se simplificar fazendo a importação dos ficheiro em lotes, otimizando o proceso com menos codigo e o processo agil e de mais facil manutenção, detalhes que se devem ter em conta, mais para fins educacionais foi explorada algumas da diversas formas de o fazer...



# Analizando o exercicio

Apois a importação dos dados, para criar consultas SQL, poderiamos carregar os dados directamente via catalog, mas a opção utilizada foi carregar directamente em dataframe, logo é
<img src="img/create-sql-visualisation.PNG">
apois uma consuta SQL podemos criar uma visualização pela UI,  
<img src="img/matplotlib.PNG">
Para usar o matplotlib, é necessario converter o nosso dataframe para um Pandas dataframe:
df_sales = df_spark.toPandas()
Com matplotlib é possivel criar varios de gráficos, pois é uma biblioteca pythom para criação de visualições para dados estátisticos.
<img src="img/seaborn.PNG">
A seaborn, também biblioteca python, também permite criar gráficos do matplotlib, Mas oferece uma abstrai alguma complexidade na criação dos mesmos gráficos.

O exercicio analisa a faturação nos anos 2019 à 2021, Veja o notebook completo: <a href="notebooks/Explore data with Azure Databricks.ipynb">




