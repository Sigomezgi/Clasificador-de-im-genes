![](https://upload.wikimedia.org/wikipedia/commons/5/53/UNAL_Aplicaci%C3%B3n_Medell%C3%ADn.svg)

<center> <h1> Clasificación de imágenes de sujetos con anteojos </h1> </center>
<center> <h4> Juan Daniel Bula Isaza - Bryan Garcia Villa - Simón Gómez Giraldo - Carolina Quintero Osorio </h4> </center>
<center> <h5> 31 de Enero de 2022 </h5> </center>

## Introducción

<p align = "justify"> El hecho de clasificar, consiste en aquel proceso dictómico de distinguir cosas u objetos que poseen cierta característica de aquellos que no la tienen, con el fin de agrupar en una clase aquellos que poseen una característica o propiedad común. El gran objetivo de este trabajo, es la formulación y construcción de un modelo de aprendizaje estadístico, con la finalidad de clasificar imágenes de sujetos con y sin anteojos.  </p>

<p align = "justify"> Con el fin de lograr un adecuado procedimiento, usando técnicas de aprendizaje estadístico, previamente se cuenta con una base de datos de 5.000 imágenes para el estudio, a los que posteriormente se les validará según sea el modelo clasificatorio. </p>


##  Descubrimiento y entendimiento de la base de datos

<p align = "justify"> En primera instancia, se cuenta con un conjunto de datos que pertenecen a un proyecto de Kaggle, la cual es una plataforma web que reune a la comunidad de ciencia de datos más grande del mundo, con más de 536 mil miembros activos en 194 países, dichos datos, fueron trabajados en el curso T81-855: Aplicaciones de aprendizaje profundo en la Universidad de Washington en ST. Louis. Para dicha competencia, los estudiantes debían determinar si una persona usa anteojos o no. Sin embargo, los sujetos de prueba no son personas reales, dado que una red neuronal adversa generativa (GAN) creó a todas las personas que se observan allí.</p>

<p align = "justify"> La red (GAN) crea estas imágenes usando un vector latente de 512 números, donde la asignación de Kaggle, proporciona tanto los vectores latentes como las caras producidas por esos vectores. </p>


## Análisis Descriptivo


<p align = "justify"> En primera instancia, nos interesa analizar como están distribuidos los datos, en relación de cantidades de personas que poseen gafas y las que no hacen uso de ellas, por lo que haremos un pequeño análisis descriptivo de nuestros datos: </p>



![graf1](https://github.com/Sigomezgi/Clasificador-de-im-genes/blob/main/graf1.png)

<p align = "justify"> Del gráfico anterior, se puede evidenciar la superioridad de personas que usan gafas, con un poco mas de mil personas de diferencia. Al enfrentarse a la situación de crear un modelo de clasificación es habitual que las clases no se encuentren balanceadas. Esto es, el número de registros para una de las clases es inferior al resto. Cuando el desequilibrio es pequeño, uno a dos, esto no supone un problema, pero cuando es grande es un problema para la mayoría de los modelos de clasificación. Esta situación se conoce como el Problema del Desequilibrio de Clases.  </p>



![graf2](![graf1](https://github.com/Sigomezgi/Clasificador-de-im-genes/blob/main/graf1.png))


![graf3](![graf1](![graf2](![graf1](https://github.com/Sigomezgi/Clasificador-de-im-genes/blob/main/graf1.png))))


