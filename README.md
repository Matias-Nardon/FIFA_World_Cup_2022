![Imagen](https://www.jumpdesign.co.uk/wp-content/uploads/2021/02/BANNER-LOGO-1024x288.jpg)
# FIFA World Cup 2022 Dashboard

## 🎯Descripción general
Este repositorio contiene un dashboard realizado en Power BI sobre el Mundial de la FIFA Qatar 2022. Incluye un análisis que se ejecutó con Jupyter Notebook en el que se realizó el procesamiento de datos con Python en el cual se pudo adaptar la información para obtener mejores conclusiones y información especifica que facilite la toma de decisiones.

## ⚙️Tech Stack
- Power BI
- DAX
- Jupyter Notebook
- Python library: Pandas
- Excel

## 📊Data Sources
Para alimentar el dashboard se utilizaron 3 archivos:

#### 1) **WorldCup2022.csv**

Este archivo se generó con el Jupyter Notebook [ETL_FIFA_World_Cup_2022.ipynb](https://github.com/Matias-Nardon/FIFA_World_Cup_2022/blob/main/ETL_FIFA_WORLD_CUP_2022.ipynb).
El objetivo de este análisis en Jupyter Notebook es generar un CSV que pueda alimentar un dashboard de Power BI con todos los datos correspondientes a cada partido de la Copa Mundial de la FIFA 2022.

Para lograr esto se utilizaron dos conjuntos de datos diferentes:
1) El conjunto de datos principal es el siguiente conjunto de datos de Kaggle: [Conjunto de datos principal](https://www.kaggle.com/datasets/die9origephit/fifa-world-cup-2022-complete-dataset)
2) El conjunto de datos secundario es el siguiente conjunto de datos de Kaggle: [Conjunto de datos secundario](https://www.kaggle.com/datasets/swaptr/fifa-world-cup-2022-match-data)

Usando **Pandas**, se tomaron algunas características del conjunto de datos secundario para tener un conjunto de datos más completo y se realizaron las transformaciones necesarias para tener el conjunto de datos con un formato adecuado para alimentar el dashboard de Power BI.

#### 2) **Teams.csv**

Este archivo contiene información general de cada equipo del torneo como ID del equipo, país, valor de mercado, confederación, bandera, mejor resultado y participaciones en anteriores Copas Mundiales de la FIFA. Se realizó tomando datos de diferentes fuentes:

- Valor de mercado de cada equipo: [CIES Football Observatory - Weekly Post 397](https://football-observatory.com/IMG/sites/b5wp/2022/wp397/en/)
- ID del equipo: Creación propia
- Resto de datos: [Wikipedia](https://www.wikipedia.org/)

#### 3) **Squads.xlsx**

Este archivo contiene datos sobre los jugadores de cada equipo en el torneo, como número, posición, nombre, edad, ID del equipo, partidos internacionales, goles, club y liga en la que juega.

Fuente: [Plantillas de la Copa Mundial de la FIFA 2022](https://en.wikipedia.org/wiki/2022_FIFA_World_Cup_squads)

## 📶 Preparación de datos 

- Para WorldCup2022.csv, las principales transformaciones se realizaron con Pandas y su explicación está en [ETL_FIFA_World_Cup_2022.ipynb](https://github.com/Matias-Nardon/FIFA_World_Cup_2022/blob/main/ETL_FIFA_WORLD_CUP_2022.ipynb)
- Para Teams.csv y Squads.xlsx, dada la simplicidad de los datos, se procesaron en Microsoft Excel.

## 📊Dashboard en Power BI

Para hacerlo más ameno para la persona que visita este repositorio, evitando instalar Power BI en su computadora y descargar el archivo de Power BI, a continuación dejo el link para poder acceder al tablero en donde se va a poder interactuar con el mismo: [DASHBOARD_FIFA_WORLD_CUP_2022](https://app.powerbi.com/view?r=eyJrIjoiMTk4ODk5NGQtNDAzMS00OWE5LWJiNjAtZjNmMWQzMTc4N2JjIiwidCI6IjU3NzE3ODA5LWQwYzQtNDliYS05MjIxLWI1ZGRmZGJiZjRhMSIsImMiOjR9)

### Resumen por confederación

En esta visualización podemos ver una visión general del torneo en su conjunto o por confederaciones.

Algunos datos a destacar:
- Vemos que **Inglaterra** es el equipo con mayor valor de mercado, seguido de **Brasil** y **Francia**. En 6º puesto se encuentra **Alemania** con un valor de mercado de 1.020M€, que fue eliminada en la fase de grupos.
- **Irán** tiene la media de edad más alta de todo el torneo.
- Vemos que las cinco grandes ligas europeas (**Inglaterra**, **España**, **Alemania**, **Italia** y **Francia**) aportan el 54,87% de los jugadores del torneo, siendo la liga inglesa la que mayor participación tiene con un 19,74% y 164 jugadores.
- **Barcelona**, **Bayern Múnich** y **Manchester City** son los equipos que más jugadores aportan al torneo con 17, 16 y 16 respectivamente.
- En cuanto a la distribución por edad, podemos observar que la mayoría de jugadores tienen entre 24 y 30 años.

https://github.com/user-attachments/assets/7cf00670-94e6-4b4a-b37d-c9dae8708289

### Resumen por equipo

En esta visualización podemos ver un resumen de cada equipo en el torneo.

Algunos datos a destacar:
- En **Argentina**:
- **Lionel Messi** es por lejos el jugador con más goles e internacionalidades, seguido de **Ángel Di María**.
- 19 de los 26 jugadores juegan en las ligas de **España**, **Inglaterra** e **Italia**.

- En **Alemania**:
- **Thomas Müller** y **Manuel Neuer** son por lejos los jugadores con más internacionalidades.
- 20 de los 26 jugadores juegan en la liga alemana.
- **Bayern Munich** es el club que más jugadores aporta con 7.

- En **Portugal**:
- **Cristiano Ronaldo** es por lejos el jugador con más goles e internacionalidades.
- Su propia liga tiene una importante aportación de jugadores al equipo con 7.
- Tiene un valor de mercado de 1.154M€, uno de los más altos del torneo.

https://github.com/user-attachments/assets/463d0f9f-406d-4bd3-a321-7af26137f089

### Eficiencia defensiva y ofensiva

En esta visualización podemos ver un gráfico de cuadrantes, que muestra la eficiencia defensiva y ofensiva de cada equipo.

Para representar la eficiencia defensiva se utilizará como variable la ***eficiencia defensiva en quiebres de línea***, es decir, cuando el equipo recibe un ataque del rival, cuál es el porcentaje de éxito de la defensa frustrando intentos de quiebre de línea.

Para representar la eficiencia ofensiva se utilizará como variable el ratio ***Intentos a portería / Intentos totales***, es decir, cuando el equipo ataca y remata, cuál es el porcentaje de remates colocados hacia el arco. Esta medida proporciona la efectividad del equipo al completar los ataques.

Como complemento, este dashboard cuenta con un gráfico de barras con la media de pases completados por equipo.

Algunos insights a destacar:

- Considerando solo los partidos correspondientes a la fase de grupos y octavos de final:
- **Argentina**, **Inglaterra**, **Brasil**, **Croacia** y **Portugal** fueron los equipos con mejor eficiencia defensiva y ofensiva. - **España**, el equipo con mayor promedio de pases completados, mostrando un gran control del balón y la fluidez del juego, pagó caro su baja eficacia ofensiva, cercana al 30%, quedando eliminado en octavos de final.
- **Francia**, uno de los mejores equipos del torneo, tuvo un rendimiento cercano a la media.
- Las grandes decepciones del torneo fueron **Alemania** y **Bélgica**, quienes si bien tuvieron un alto promedio de pases completados, mostrando un buen control del balón y la fluidez del juego, debido a su baja eficacia defensiva y ofensiva no lograron pasar de la fase de grupos.
- **México** es un caso atípico, con casi un 70% de eficacia defensiva y una eficacia ofensiva cercana a la media, no logró pasar de la fase de grupos. La contraparte es **Polonia**, con quien compartió el grupo C, que tuvo una de las peores eficacias defensivas y ofensivas del torneo pero aun así logró pasar de la fase de grupos. - **Costa Rica** y **Camerún** también son casos atípicos, se puede apreciar una alta eficiencia ofensiva pero si nos fijamos en los pases completados podemos ver que estos fueron muy bajos (no se aprecia en el vídeo), por lo que podemos concluir que estos equipos tuvieron poco el balón, llegando apenas al arco rival, pero en las ocasiones que patearon, los remates fueron al arco.

https://github.com/user-attachments/assets/defe74df-d1c2-4c35-8945-334ae9af6442
