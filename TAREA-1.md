Trabajo 1
================
Kevin Huanca
17/12/2021

# DESARROLLO DE LA PRACTICA 1

## PRIMERA PARTE

1.  Calcula los valores numéricos aproximados de:

## a

``` r
(0.3*0.15)/(0.3*0.15+0.2*0.8+0.5*0.12)
```

    ## [1] 0.1698113

## b

``` r
(5^6)/factorial(6)*exp(-5)
```

    ## [1] 0.1462228

## c

``` r
(factorial(20))/(factorial(13)*factorial(7))
```

    ## [1] 77520

2.  Realizar la siguiente suma

## a

``` r
a <-seq(1,1000,1) 
sum(a)
```

    ## [1] 500500

## b

``` r
(2^32*2)-1
```

    ## [1] 8589934591

3.  El vector grupo representa el grupo al que pertenece una serie de
    alumnos

## a. ¿Cuántos elementos tiene?

``` r
load(url("https://goo.gl/uDzU8v"))
lista.alumnos<- c(grupo)
length(lista.alumnos)
```

    ## [1] 192

## b. ¿En que posiciones del vector estan la letra A ?

``` r
which(grupo == "A")
```

    ##  [1]   2   8  17  21  28  84 101 108 111 115 123 136 190 192

4.  El vector nota representa la nota de un examen de los alumnos que
    estan en los grupos del vector grupo

## a.¿Cuánto suman todas las notas?

``` r
Vector_nota<- c(nota)
sum(Vector_nota)
```

    ## [1] 962

## b.¿Cual es la media aritmética de todas las notas?

``` r
mean(Vector_nota)
```

    ## [1] 5.010417

## c.¿En qué posiciones están las notas mayores de 7.0?

``` r
which(nota >7.0)
```

    ## [1]  81 103 120 151

## d.Visualiza las notas ordenadas de mayor a menor

``` r
sort(Vector_nota,decreasing=TRUE)
```

    ##   [1] 7.7 7.5 7.4 7.2 7.0 6.9 6.9 6.8 6.8 6.8 6.8 6.8 6.6 6.5 6.4 6.4 6.4 6.4
    ##  [19] 6.3 6.2 6.2 6.2 6.2 6.2 6.2 6.1 6.1 6.1 6.1 6.0 6.0 6.0 6.0 6.0 6.0 5.9
    ##  [37] 5.9 5.9 5.9 5.9 5.9 5.9 5.9 5.9 5.8 5.8 5.8 5.8 5.8 5.7 5.7 5.7 5.7 5.7
    ##  [55] 5.6 5.6 5.6 5.6 5.6 5.6 5.5 5.5 5.5 5.5 5.5 5.5 5.5 5.5 5.5 5.5 5.5 5.5
    ##  [73] 5.5 5.4 5.4 5.4 5.4 5.4 5.4 5.4 5.4 5.3 5.3 5.3 5.3 5.2 5.2 5.2 5.2 5.2
    ##  [91] 5.2 5.2 5.1 5.0 5.0 5.0 5.0 5.0 5.0 5.0 5.0 5.0 4.9 4.9 4.9 4.9 4.9 4.9
    ## [109] 4.8 4.8 4.8 4.8 4.8 4.8 4.7 4.7 4.7 4.7 4.7 4.7 4.7 4.7 4.7 4.7 4.6 4.6
    ## [127] 4.6 4.6 4.5 4.5 4.5 4.5 4.5 4.5 4.4 4.4 4.4 4.4 4.4 4.4 4.4 4.3 4.3 4.3
    ## [145] 4.2 4.2 4.2 4.2 4.2 4.2 4.2 4.2 4.1 4.1 4.1 4.1 4.1 4.0 4.0 4.0 4.0 4.0
    ## [163] 4.0 3.9 3.9 3.8 3.8 3.8 3.7 3.7 3.7 3.7 3.6 3.6 3.6 3.5 3.4 3.4 3.4 3.4
    ## [181] 3.2 3.2 3.2 3.1 3.0 2.9 2.9 2.9 2.7 2.6 2.5 1.7

## e.¿En qué posición están la nota máxima?

``` r
which(nota==7.7)
```

    ## [1] 120

5.  A partir de los vectores grupo y nota definidos

## a.Suma las notas de los 10 primeros alumnos del vector

``` r
sum(Vector_nota[1:10])
```

    ## [1] 51.8

## b.¿Cuántos alumnos hay del grupo C?

``` r
data.1<- data.frame(nota,grupo)
length(which(data.1$grupo == "C"))
```

    ## [1] 39

## c.¿Cuántos alumnos han aprobado?

``` r
length(which(data.1$nota >5.0))
```

    ## [1] 93

## d.Cuántos alumnos del grupo B han aprobado?

``` r
length(which(data.1$grupo =="B" & data.1$nota >5.0))
```

    ## [1] 10

## e.¿Qué porcentaje de alumnos del grupo C han aprobado?

``` r
length(which(data.1$grupo == "C" & data.1$nota >5.0))*100/length(which(data.1$grupo == "C"))
```

    ## [1] 56.41026

## f.¿De qué grupos son la mÃ¡xima y mÃ­nima notas de toda la muestra?

``` r
grupo[120]
```

    ## [1] "E"

``` r
grupo[142]
```

    ## [1] "B"

## g.Nota media de los alumnos de grupo A y B, juntos, considerando sólo a los que han aprobado.

``` r
nota_A.aprobado<- nota[c(2,17,28,108)]

nota_B.aprobado<- nota[c(13,18,65,86,103,148,170,176,186,187)]
sum(nota_A.aprobado)+sum(nota_B.aprobado)/ length(nota_A.aprobado) + length(nota_B.aprobado)
```

    ## [1] 47.075

## 6.Calcula el percentil 66 de las notas de todos los alumnos,y tambien de los alumnos del grupo C.

``` r
66*length(nota)/100
```

    ## [1] 126.72

## 7.Un alumno tiene una nota de 4.9. ¿Qué porcentaje, del total de alumnos, tiene una nota menor o igual que la suya? ¿Y qué porcentaje tiene una nota mayor o igual que la suya?

``` r
length(which(nota <= 4.9))/length(nota)*100
```

    ## [1] 46.875

``` r
length(which(nota >= 4.9))/length(nota)*100
```

    ## [1] 56.25

## 8.Realiza el gráfico de diagramas de caja de las notas de cada grupo, para poder comparar el nivel de cada uno de ellos.

``` r
data.2 <- data.frame(nota,grupo) 

x<- data.2$nota[data.2$grupo== "A"]
y<- data.2$nota[data.2$grupo== "B"]
z<- data.2$nota[data.2$grupo== "C"]
m<- data.2$nota[data.2$grupo== "D"]
n<- data.2$nota[data.2$grupo== "D"]
nombres<- c("GRUPO A","GRUPO B","GRUPO C","GRUPO D","GRUPO E")


boxplot(x,y,z,m,n,names = nombres )
```

![](TAREA-1_files/figure-gfm/unnamed-chunk-22-1.png)<!-- -->

9.  Si la variable conc recoge la concentración de plomo (en ppm) en el
    aire de cierta zona durante un dÃ­a completo

## a.¿ Cuál ha sido la concentración máxima?

``` r
max(conc)
```

    ## [1] 47.34

## b.¿En cuántos de los muestreos se ha superado la concentración de 40.0 ppm?

``` r
length(which(conc >40.0))
```

    ## [1] 61

## c.¿Cuál ha sido la concentración media del día?

``` r
sum(conc)/length(conc)
```

    ## [1] 24.07229

## d. ¿Cuáles fueron las 10 mediciones más bajas del día?

``` r
conc_decrec<- sort(conc)
conc_decrec[1:10]
```

    ##  [1] 0.93 1.07 1.77 2.03 2.58 2.73 2.75 2.88 2.88 2.91

## e. Si la primera medida fue a las 00:00. ¿A qué hora del día se alcanza la concentración máxima?

``` r
max(conc)
```

    ## [1] 47.34

## SEGUNDA PARTE

## 1

``` r
X<- c(1:10)

Y<- c(1,4,6,8,25,36,49,61,81,100)
plot(X,Y)
```

![](TAREA-1_files/figure-gfm/unnamed-chunk-28-1.png)<!-- --> ## 2

``` r
a<- c(1:4)
b<- c(seq(2,8,2))

c<- c(seq(3,12,3))
matriz.A<- matrix(c(a,b,c),ncol = 3,nrow = 4)
matriz.A
```

    ##      [,1] [,2] [,3]
    ## [1,]    1    2    3
    ## [2,]    2    4    6
    ## [3,]    3    6    9
    ## [4,]    4    8   12

## 3

``` r
a1<-c(1,0,0)

a2<- c(0,1,0)
a3<- c(0,0,1)
matriz.I<- cbind(a1,a2,a3)
matriz.I*3
```

    ##      a1 a2 a3
    ## [1,]  3  0  0
    ## [2,]  0  3  0
    ## [3,]  0  0  3

## 4

``` r
matrix(rep(0,16),nrow = 4)
```

    ##      [,1] [,2] [,3] [,4]
    ## [1,]    0    0    0    0
    ## [2,]    0    0    0    0
    ## [3,]    0    0    0    0
    ## [4,]    0    0    0    0

## 5

``` r
matriz.4<- cbind(c(-1,0,0,0),c(0,1,0,0),c(0,0,2,0),c(0,0,0,3))
matriz.B<- matriz.4+diag(4)
matriz.B
```

    ##      [,1] [,2] [,3] [,4]
    ## [1,]    0    0    0    0
    ## [2,]    0    2    0    0
    ## [3,]    0    0    3    0
    ## [4,]    0    0    0    4

## 6

``` r
t(matriz.A)
```

    ##      [,1] [,2] [,3] [,4]
    ## [1,]    1    2    3    4
    ## [2,]    2    4    6    8
    ## [3,]    3    6    9   12

## 7

``` r
d<- c(0,0,0,0)
matriz.A<- matrix(c(a,b,c,d),ncol = 4,nrow = 4)
matriz.A+matriz.B
```

    ##      [,1] [,2] [,3] [,4]
    ## [1,]    1    2    3    0
    ## [2,]    2    6    6    0
    ## [3,]    3    6   12    0
    ## [4,]    4    8   12    4

``` r
matriz.A-matriz.B
```

    ##      [,1] [,2] [,3] [,4]
    ## [1,]    1    2    3    0
    ## [2,]    2    2    6    0
    ## [3,]    3    6    6    0
    ## [4,]    4    8   12   -4

``` r
matriz.B*3
```

    ##      [,1] [,2] [,3] [,4]
    ## [1,]    0    0    0    0
    ## [2,]    0    6    0    0
    ## [3,]    0    0    9    0
    ## [4,]    0    0    0   12

``` r
matriz.A%*%matriz.B
```

    ##      [,1] [,2] [,3] [,4]
    ## [1,]    0    4    9    0
    ## [2,]    0    8   18    0
    ## [3,]    0   12   27    0
    ## [4,]    0   16   36    0

## 8

``` r
#install.packages("Biodem")
#library("Biodem")
matriz.C<- matrix(c(1,-2,1,2,4,0,3,-2,1),nrow = 3,ncol = 3)

#mtx.exp(matriz.C,8)
```

## 9

``` r
a9<- c(3,9,3)
b9<- c(-1,-2,1)
c9<- c(1,1,-2)
A9<- cbind(a9,b9,c9)
B9<- cbind(c(-1,-9,-9))

solve(A9)%*%B9
```

    ##    [,1]
    ## a9   -1
    ## b9    2
    ## c9    4

## 10

``` r
help(eigen)
help(det) 
```

## 11

``` r
m11<- c(1:10)
n11 <-m11*2

n12 <-m11*3
n13 <-m11*4
n14 <-m11*5
A11 <-cbind(m11,n11,n12,n13,n14,nrow = 10,ncol = 5)


f11<- c(0,1,0,0,1,1,0,1,1,0,0,1,0,0,1,1,0,1,0,1,0,1,0,1,0)
B11<- matrix(f11,5)

#A11%*%B11-A11%*%t(B11)
```

## 12

``` r
x12<- matrix(c(1,1,1,1,1,1,-1,0,1,2),nrow = 5)
y12<- matrix(c(0,0,1,1,3),nrow = 5)
solve(t(x12)%*%x12)%*%t(x12)%*%y12
```

    ##           [,1]
    ## [1,] 0.5384615
    ## [2,] 0.7692308

## 13

``` r
means = aggregate(co2, FUN=mean)
year = as.vector(time(means))
co2 = as.vector(means)
```

## 13a

``` r
co2
```

    ##  [1] 315.8258 316.7475 317.4850 318.2975 318.8325 319.4625 319.8725 321.2100
    ##  [9] 322.0200 322.8900 324.4592 325.5175 326.1550 327.2933 329.5117 330.0792
    ## [17] 330.9858 331.9858 333.7300 335.3358 336.6808 338.5150 339.7608 340.9592
    ## [25] 342.6083 344.2467 345.7258 346.9750 348.7508 351.3133 352.7542 354.0367
    ## [33] 355.4783 356.2917 356.9958 358.8800 360.9142 362.6867 363.8175

``` r
year
```

    ##  [1] 1959 1960 1961 1962 1963 1964 1965 1966 1967 1968 1969 1970 1971 1972 1973
    ## [16] 1974 1975 1976 1977 1978 1979 1980 1981 1982 1983 1984 1985 1986 1987 1988
    ## [31] 1989 1990 1991 1992 1993 1994 1995 1996 1997

## 13b

``` r
y13 <-c(0,diff(co2))
y13
```

    ##  [1] 0.0000000 0.9216667 0.7375000 0.8125000 0.5350000 0.6300000 0.4100000
    ##  [8] 1.3375000 0.8100000 0.8700000 1.5691667 1.0583333 0.6375000 1.1383333
    ## [15] 2.2183333 0.5675000 0.9066667 1.0000000 1.7441667 1.6058333 1.3450000
    ## [22] 1.8341667 1.2458333 1.1983333 1.6491667 1.6383333 1.4791667 1.2491667
    ## [29] 1.7758333 2.5625000 1.4408333 1.2825000 1.4416667 0.8133333 0.7041667
    ## [36] 1.8841667 2.0341667 1.7725000 1.1308333

## 13c

``` r
plot(year,y13,type = "o", pch = 20, xlab = "aÃ±os", ylab = " diferencia de [CO2]",
        main = "variacion de CO2 consecutivo", col= "black", font = 2)
```

![](TAREA-1_files/figure-gfm/unnamed-chunk-43-1.png)<!-- -->

## 13d

``` r
plot(year,y13,xlim = c(1959,2020), type = "o", pch = 20, xlab = "Tiempo", ylab = " diferencia de [CO2]",
     main = "variacion de CO2 consecutivo", col= "black", font = 2)
points(2020,2.64, pch = 4, col = "red")
```

![](TAREA-1_files/figure-gfm/unnamed-chunk-44-1.png)<!-- -->
