![](https://upload.wikimedia.org/wikipedia/commons/5/53/UNAL_Aplicaci%C3%B3n_Medell%C3%ADn.svg)

<center> <h1> Clasificación de imágenes de sujetos con anteojos </h1> </center>
<center> <h4> Juan Daniel Bula Isaza - Bryan Garcia Villa - Simón Gómez Giraldo - Carolina Quintero Osorio </h4> </center>
<center> <h5> 31 de Enero de 2022 </h5> </center>

## Introducción

<p align = "justify"> Clasificar consiste en un proceso dictómico de distinguir cosas u objetos que poseen cierta característica de aquellos que no la tienen, con el fin de agrupar en una clase aquellos que poseen una característica o propiedad común. El gran objetivo de este trabajo, es la formulación y construcción de un modelo de aprendizaje estadístico, con la finalidad de clasificar imágenes de sujetos con y sin anteojos.  </p>

<p align = "justify"> Para el estudio se cuenta con una base de datos de 4500 imágenes, a los que posteriormente se les validará según sea el modelo clasificatorio. </p>


##  Descubrimiento y entendimiento de la base de datos

<p align = "justify"> En primera instancia, se cuenta con un conjunto de datos que pertenecen a un proyecto de Kaggle, la cual es una plataforma web que reune a la comunidad de ciencia de datos más grande del mundo, con más de 536 mil miembros activos en 194 países, dichos datos, fueron trabajados en el curso T81-855: Aplicaciones de aprendizaje profundo en la Universidad de Washington en ST. Louis. Para dicha competencia, los estudiantes debían determinar si una persona usa anteojos o no. Sin embargo, los sujetos de prueba no son personas reales, dado que una red neuronal adversa generativa (GAN) creó a todas las personas que se observan allí.</p>

<p align = "justify"> La red (GAN) crea estas imágenes usando un vector latente de 512 números, donde la asignación de Kaggle, proporciona tanto los vectores latentes como las caras producidas por esos vectores. </p>


## Análisis Descriptivo


<p align = "justify"> En primera instancia, interesa analizar como están distribuidos los datos, en relación de cantidades de personas que poseen gafas y las que no hacen uso de ellas, por lo que se realiza un análisis descriptivo de nuestros datos: </p>



![graf1](https://github.com/Sigomezgi/Clasificador-de-im-genes/blob/main/graf1.png) 

<p align = "justify"> A pesar que hay una tendencia en la base de datos a las personas con gafas, dicha diferencia no lleva a considerar algún tipo de pre procesamiento que permita evitar desbalances en la muestra de entrenamiento pues cuando el desequilibrio es pequeño,  de ratio uno a dos, esto no supone un problema pero cuando es grande es un problema para la mayoría de los modelos de clasificación. Esta situación se conoce como el Problema del Desequilibrio de Clases.  </p>



![graf2](https://user-images.githubusercontent.com/94578395/151914148-f40f8e10-1457-41cb-9493-16e8f3976799.JPG)



![graf3](https://user-images.githubusercontent.com/94578395/151914180-1294a998-7258-4f85-8dfe-cd99c2ed4a33.JPG)

## Procesamiento de imágenes

<p align = "justify"> Para el procesamiento de imagenes era necesario realizar una adecuación de cada imagen debido a que todas las imágenes se encontraban en formato RGB, era práctico realizar la respectiva conversión a escala de grises, este cambio de color reduce la cantidad a un tercio de los datos a color. Debido a la alta resolución de las imágenes, se permite la disminución de la resolución a un 5% de la original</p>
<p align = "justify"> La forma con la cual se obtuvo la base de datos permite que todas las imágenes exhiban características similares en cuánto a la resolución y la posición de los rostros, esto reduce un poco la limpieza de los datos y permite plasmar caracteriticas particulares como el que se muestra a continuación como rostro promedio. Sin embargo esto reduce la variabilidad y disminuye de generalización del modelo con esta base de datos</p>

![rostromean](https://user-images.githubusercontent.com/94578395/151915865-dc1e5f60-a810-4ca4-96f3-3ac24aa7f0af.JPG)

La desviación estándar de ese rostro corresponde a:

![std](https://user-images.githubusercontent.com/94578395/151916072-49de80e4-a2d5-484f-918a-600854b0ec8e.JPG)

<p align = "justify">Como se aprecia no hay marcadas escalas de negro en el rostro de desviación estándar</p>

### Análisis de componente principales
<p align = "justify"> El data set final con el cual se entrenará y validará el modelo finalizo con dimensiones de: (4500,2500). Es necesario reducir la dimensionada de dicha base de datos, pues es muy posible la existencia de multicolinealidad en el data set. También es necesario reducir el gasto computacional. </p>

<p align = "justify"> Se realiza una descomposición de los valores singulares de la matriz de varianza del dataset final. Como se observa a continuación el 93% de la variabilidad de los datos originales pueden ser explicados a través de las primeras 81 componentes principales.</p>

![variability](https://user-images.githubusercontent.com/94578395/151917306-7bc09ab8-b607-479e-8e18-6a68564798e7.JPG)

<p align = "justify">Al proyectar los datos sobre estas componentes principales, se observa que los datos que se encontraban en la escala de grises se salen de la misma. A continuación se presetan tres imágenes: La primera imagen corresponde a la imagen real a color en las dimensiones originales, la segunda corresponde a la imagen real a blanco y negro en las dimensiones en la que se procesasn los datos (50 x 50), la tercera corresponde a la proyección de los datos originales en dimensiones 9x9 donde se retiene el 93 % de la variabilidad de la segunda imagen. Es importante mencionar que la imagen resulta a color pues cuando se realiza la proyección sobre las componentes principales se puede salir del rango de la escala de grises</p>

![proyec](https://user-images.githubusercontent.com/94578395/151917743-79f48917-e548-40be-8c55-532237ec7ef3.JPG)




