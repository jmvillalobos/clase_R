# clase_R
Clase para Universidad Michoacana
### by José Manuel Villalobos Escobedo

## En este curso veremos el uso de la herramienta R, en la cual podemos hacer desde calculos matematicos simples, hasta analisis estadisticos altamente complejos. Este programa usa un leguaje de programación con objetos y funciones. Para entender la logica del programa en la siguiente liga encontraras ejercicios y una descripción detallada del programa y el uso de la herramienta RStudio.

# Lección 1
por Manuel Villalobos

Introducción a R
En esta parte quiero mostrarles que es R para aquellos que no han tenido un acercamiento a esta herramienta. R es un programa libre ## para hacer estadística mucho más poderosa que Excel. La gran ventaja de R es que es completamente gratuito y cualquier usuario puede ## desarrollar herramientas y posteriormente liberarlas. Es por esta razón que R se ha convertido en una manera sencilla de compartir
 código para análisis de datos masivos.


 Tu puedes escribir en la parte de código en RStudio las siguientes instrucciones y al dar enter, estas se ejecutarán y se verán la 
 parte inferior de tu pantalla. En estos ejercicios tu veras dos recuadros, uno con las instrucciones a ejecutar y otro el resultado 
 anteponiéndose el símbolo [1].

 Copia y pega en R las instrucciones y ve si las puedes ejecutar
 para ubicarte en una dirección dentro de tu sistema puedes usar:

setwd("~/Desktop/Curso")

Para imprimir un texto en pantalla usamos la siguiente instrucción. 

print("Nosotros estamos aprendiendo a trabajar en R")    #copien y peguen esta instrucción en R y vean que sucede.
 [1] "Nosotros estamos aprendiendo a trabajar en R"
Para saber qué hace y cómo opera una función en R, puedes obtener ayuda usando la siguiente sintaxis.

?print

La ayuda en RStudio aparecerá en la parte izquierda de tu pantalla.

Para salir del programa que estamos haciendo en R usamos la siguiente instrucción:
  
quit()

R preguntara si deseas guardar tu trabajo y puedes o no hacerlo dependiendo de lo que desees. 
Usando a R como calculadora y declarando variables:
Aquí haremos operaciones matemáticas básicas.

4+6

 [1] 10
 
5-3

 [1] 2
 
30/6

 [1] 5
 
8 * sqrt (4)

 [1] 16
 
Prueben ahora las que ustedes deseen.

R nos da la capacidad de declarar variables y guardar en ellas valores o resultados de los procesos ejecutados previamente. 

x = 3 + 5

impacto=21

Para ver lo que contiene la variable en pantalla, simplemente escribimos la variable y damos enter:

impacto

 [1] 21
 
Esto nos ayuda a mantener estas variables y llamarlas en cualquier otra operación posterior.

impacto * x

 [1] 168
 
En R podemos crear objetos que contengan varios valores, estos son llamados vectores y se declaran usando la función c().  

impactos= c(10, 40, 12, 3, 5, 21, 8)

Escriban la variable para visualizar los valores que contiene

impactos
 [1]  10  40  12   3   5  21   8
 
podemos hacer diferentes operaciones con este objeto y estas afectarán a todos los valores contenidos en él.

impactos + 1

 [1]  11  41  13   4   6  22   9
 
impactos * 2

 [1]  20  80  24   6  10  42  16
 
impactos / 2

 [1]   5.0  20.0   6.0   1.5   2.5  10.5   4.0
 
Pueden probar cosas como:

impactos2= impactos * 2

impactos * impactos2

[1]   200  3200   288    18    50   882   128

Existen en R muchas funciones interesantes para realizar análisis estadísticos sobre datos masivos, tales como encontrar el promedio de los datos, el valor máximo o mínimo, etc. 


mean(impactos)

 [1] 14.14286
 
sum(impactos)

 [1] 99
 
max(impactos)

 [1] 40
 
min(impactos)

 [1] 3
 
range(impactos)

 [1]  3 40
 
sort(impactos)

 [1]  3  5  8 10 12 21 40
 
unique(impactos)

 [1] 10 40 12  3  5 21  8
 
Ejercicio

¿Qué hace la función “range”?

Tipos de objetos

En R, al igual que en otros lenguajes de programación, podemos no solo guardar objetos que contengan valores numéricos, si no también cadenas que contengan texto:

revistas = c ("PNAS", "Nature", "PBiology", "Pone", "Pgenetics", "NatureP", "Development")


Ahora podemos etiquetar los valores del anterior vector, usando el nuevo

names(impactos) = revistas 


ahora visualicen impactos!! ¿Qué ven?


En ocasiones no queremos aplicar las operaciones a todos los valores contenidos en un vector y en R podemos especificar qué posición del vector queremos alterar. 


impactos[1]

 PNAS 
 
   10
   
¿para visualizar el tercer elemento?



Pero dado que nuestro vector "impactos"" ya tiene nombres, podemos también hacer uso de estos:


impactos["Nature"]

 Nature 
 
     40
     
#también puedes pedir varios elementos del objeto:


impactos[c(1,5)]

      PNAS Pgenetics 
      
        10         5
        
#podemos eliminar elementos del vector:


impactos[-c(1,5)]

      Nature    PBiology        Pone     NatureP Development 
      
          40          12           3          21           8
          
Ejercicio

¿Cuál es la revista que tiene menor impacto?

¿Pueden crear un nuevo vector que ya no contenga a Nature y hacer otro vector nuevo y saber además cuál es el promedio de impactos, sin esta revista?

Operaciones racionales

Al hacer comparaciones entre datos, necesitamos usar funciones que nos digan, por ejemplo, si cierto gen pasa un número de lecturas o no. Para este tipo de preguntas usamos las siguientes funciones:

impactos > 21

        PNAS      Nature    PBiology        Pone   Pgenetics     NatureP 
        
       FALSE        TRUE       FALSE       FALSE       FALSE       FALSE 
       
 Development 
 
       FALSE
       
#podemos preguntar cuáles son menores, mayores o iguales a cierto valor


impactos < 21

        PNAS      Nature    PBiology        Pone   Pgenetics     NatureP 
        
        TRUE       FALSE        TRUE        TRUE        TRUE       FALSE 
        
 Development 
 
        TRUE
        
impactos <=21

        PNAS      Nature    PBiology        Pone   Pgenetics     NatureP 
        
        TRUE       FALSE        TRUE        TRUE        TRUE        TRUE 
        
 Development 
 
        TRUE
        
impactos == 21

        PNAS      Nature    PBiology        Pone   Pgenetics     NatureP 
        
       FALSE       FALSE       FALSE       FALSE       FALSE        TRUE 
       
 Development 
 
       FALSE

En todos los casos R nos da un vector de FALSE/TRUE (valores lógicos) y son útiles para muchos casos, en donde queremos saber cosas de los objetos que cumplen cierta condición:

¿Cuantas revistas tienen más de 10 de impacto?

sum(impactos > 10)

 [1] 3
 
Ejercicio

¿cómo podemos ver las revistas que tienen un impacto mayor al promedio de todas?

Generación de sucesiones

En R existen varias funciones para generar sucesiones numéricas. Por ejemplo:

1:30

  [1]   1   2   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17  18  19  20  21  22  23
  
 [24]  24  25  26  27  28  29  30
 
El operador ’dos puntos’ tiene máxima prioridad en una expresión, así, por ejemplo:

2*1:15 

 [1]   2   4   6   8  10  12  14  16  18  20  22  24  26  28  30
 
La función seq() permite generar sucesiones más complejas.


seq(-5, 5, by=.2)

  [1]  -5.0  -4.8  -4.6  -4.4  -4.2  -4.0  -3.8  -3.6  -3.4  -3.2  -3.0  -2.8  -2.6  -2.4
  
 [15]  -2.2  -2.0  -1.8  -1.6  -1.4  -1.2  -1.0  -0.8  -0.6  -0.4  -0.2   0.0   0.2   0.4
 
 [29]   0.6   0.8   1.0   1.2   1.4   1.6   1.8   2.0   2.2   2.4   2.6   2.8   3.0   3.2
 
 [43]   3.4   3.6   3.8   4.0   4.2   4.4   4.6   4.8   5.0
 
Haciendo gráficas en R

Esta parte es la mejor de R, podemos generar una gran cantidad de gráficos que expresen de una manera interesante nuestros datos:
plot(impactos)


barplot(impactos)


pie(impactos)


hist(impactos)


#Usando las instrucciones en la opción de ayuda para cada gráfico y herramientas en la web, podemos construir gráficos cada vez más sofisticados:


hist(impactos, col= "red", main = "Revistas científicas", ylab= "revistas")



#esta imagen la podemos guardar directamente desde RStudio o dar una instrucción:


pdf("histograma_revistas.pdf")


hist(impactos, col= "red", main = "Revistas científicas", ylab= "revistas")

dev.off()

 quartz_off_screen 
                 2
                 
Ahora bien podemos comenzar a jugar con algunos datos más reales, para esto vamos a cargar una tabla de datos en R. Esta tabla vive en:

## https://github.com/jmvillalobos/clase_R/blob/master/tabla.txt

Descarga el archivo y guardalo en una carpeta (ve a raw, y dale guardar como).

tab = read.table("tabla.txt")

tab

        cond1 cond2 cond3
        
 gene1    252   233   182
 
 gene2    141   179   216
 
 gene3    165   195   175
 
 gene4    174   190   188
 
 gene5    192   231   194
 
 gene6    225   142   197
 
 gene7    176   190   218
 
 gene8    191   210   175
 
 gene9    229   162   191
 
 gene10   170   112   192

#Ahora podemos visualizar estos datos usando la función boxplo():

boxplot(tab)


#Lo podemos visualizar más bonito:

boxplot(tab, col=c("blue", "red", "green"))


#Ahora como vimos antes, podemos extraer de esta tabla los valores que queramos, por ejemplo:


tab[c(1,6,10), c(1,3)]

        cond1 cond3
        
 gene1    252   182
 
 gene6    225   197
 
 gene10   170   192
 
#Y también podemos seleccionar los valores ya sea por columnas o por filas:


tab[c(1,6,10 ), ]

        cond1 cond2 cond3
        
 gene1    252   233   182
 
 gene6    225   142   197
 
 gene10   170   112   192
 
tab[, c(1,3)]

        cond1 cond3
        
 gene1    252   182
 
 gene2    141   216
 
 gene3    165   175
 
 gene4    174   188
 
 gene5    192   194
 
 gene6    225   197
 
 gene7    176   218
 
 gene8    191   175
 
 gene9    229   191
 
 gene10   170   192
 

#y podemos utilizar nuestras funciones para sucesiones:

tab[c(1:20), ]

        cond1 cond2 cond3
        
 gene1    252   233   182
 
 gene2    141   179   216
 
 gene3    165   195   175
 
 gene4    174   190   188
 
 gene5    192   231   194
 
 gene6    225   142   197
 
 gene7    176   190   218
 
 gene8    191   210   175
 
 gene9    229   162   191
 
 gene10   170   112   192
 
 gene11   125   194   215
 
 gene12   229   179   188
 
 gene13   176   267   201
 
 gene14   190   201   199
 
 gene15   189   295   171
 
 gene16   239   222   192
 
 gene17   170   202   228
 
 gene18   233   288   231
 
 gene19   180   276   201
 
 gene20   219   180   185
