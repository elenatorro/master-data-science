# Introducción

Vamos a ver dos maneras de obtener una variable respuesta **continua**:

- A través de una variable explicativa **dicotómica**: t de Student
- A través de una variable explicativa **nominal**: Análisis de la varianza (ANOVA)

### Grados de libertad

Definiciones:

1. “El valor de los grados de libertad se relaciona con el **número de veces** que se usa la información de la muestra”.
2. “Se definen como el **número de valores** que podemos **escoger libremente**”.
3. “Los grados de libertad de una prueba estadística son el número de datos que son **libres de variar** cuando se calcula tal prueba”.

> Lectura recomendada: [Grados de Libertad](https://www.redalyc.org/pdf/2031/203129458002.pdf)

### Homocedasticidad y heterocedasticidad

En estadística se dice que un modelo predictivo presenta **homocedasticidad** cuando la varianza del error condicional a las variables explicativas **es constante** en todas las observaciones realizadas. La homocedasticidad es una propiedad fundamental del modelo de regresión lineal general y está dentro de sus supuestos clásicos básicos.

En estadística se dice que un modelo de regresión lineal presenta **heterocedasticidad** cuandola varianza del error condicional **no es constante** en todas las observaciones realizadas.

En el contraste de hipótesis, hay que considerar también los supuestos de homocedasticidad y heterocedasticidad.

## Método 1: t de Student

Intenta explicar la variable respuesta **continua** a través de la variable explicativa **dicotómica.** La variable respuesta es una variable que puede tomar valores continuos.

**Metáfora de los Peces Mutantes**

Imaginemos a nuestros pobres pececillos del lago. Ahora, en lugar de estar curados o no en base a un tratamiento, digamos que estos peces tienen un **gen mutante**. Este gen mutante puede adquirir multitud de valores, pero estos valores pueden depender del tratamiento que se le suministre al pez. Como estamos probando dos tratamientos, queremos conocer qué tratamiento produce según qué valores del gen.

La distribución t o `t de Student` es una distribución de probabilidad que surge del problema de estimar la **media** de una población **normalmente distribuida** cuando el tamaño de muestra es **pequeño**.

Para usar este método, tenemos que saber cuál es el **Grado de Libertad** que vamos a manejar. En este método, sabemos cuál es la probabilidad de que una variable con ν grados de libertad sea mayor que una variable t, y tenemos que calcular el valor de la variable t. Los grados de libertad y el nivel de confianza α nos sirven para calcular el valor de _t_ que queremos comparar en la [tabla](http://www-eio.upc.edu/teaching/estad/MC/taules/TStud.pdf).

_(ν = grado de libertad)_

```
ν    0,6   0,75  0,9   0,95  0,975  0,99   0,995  0,9975  0,999   0,9995
---+----------------------------------------------------------------------
1  | 0,325 1,000 3,078 6,314 12,706 31,821 63,656 127,321 318,289 636,578
2  | 0,289 0,816 1,886 2,920 4,303  6,965  9,925  14,089  22,328  31,600
3  | 0,277 0,765 1,638 2,353 3,182  4,541  5,841  7,453   10,214  12,924
4  | 0,271 0,741 1,533 2,132 2,776  3,747  4,604  5,598   7,173   8,610
5  | 0,267 0,727 1,476 2,015 2,571  3,365  4,032  4,773   5,894   6,869
6  | 0,265 0,718 1,440 1,943 2,447  3,143  3,707  4,317   5,208   5,959
7  | 0,263 0,711 1,415 1,895 2,365  2,998  3,499  4,029   4,785   5,408
8  | 0,262 0,706 1,397 1,860 2,306  2,896  3,355  3,833   4,501   5,041
9  | 0,261 0,703 1,383 1,833 2,262  2,821  3,250  3,690   4,297   4,781
10 | 0,260 0,700 1,372 1,812 2,228  2,764  3,169  3,581   4,144   4,587
11 | 0,260 0,697 1,363 1,796 2,201  2,718  3,106  3,497   4,025   4,437
12 | 0,259 0,695 1,356 1,782 2,179  2,681  3,055  3,428   3,930   4,318
13 | 0,259 0,694 1,350 1,771 2,160  2,650  3,012  3,372   3,852   4,221
14 | 0,258 0,692 1,345 1,761 2,145  2,624  2,977  3,326   3,787   4,140
15 | 0,258 0,691 1,341 1,753 2,131  2,602  2,947  3,286   3,733   4,073
16 | 0,258 0,690 1,337 1,746 2,120  2,583  2,921  3,252   3,686   4,015
17 | 0,257 0,689 1,333 1,740 2,110  2,567  2,898  3,222   3,646   3,965
18 | 0,257 0,688 1,330 1,734 2,101  2,552  2,878  3,197   3,610   3,922
19 | 0,257 0,688 1,328 1,729 2,093  2,539  2,861  3,174   3,579   3,883
20 | 0,257 0,687 1,325 1,725 2,086  2,528  2,845  3,153   3,552   3,850
21 | 0,257 0,686 1,323 1,721 2,080  2,518  2,831  3,135   3,527   3,819
22 | 0,256 0,686 1,321 1,717 2,074  2,508  2,819  3,119   3,505   3,792
23 | 0,256 0,685 1,319 1,714 2,069  2,500  2,807  3,104   3,485   3,768
24 | 0,256 0,685 1,318 1,711 2,064  2,492  2,797  3,091   3,467   3,745
25 | 0,256 0,684 1,316 1,708 2,060  2,485  2,787  3,078   3,450   3,725
26 | 0,256 0,684 1,315 1,706 2,056  2,479  2,779  3,067   3,435   3,707
27 | 0,256 0,684 1,314 1,703 2,052  2,473  2,771  3,057   3,421   3,689
28 | 0,256 0,683 1,313 1,701 2,048  2,467  2,763  3,047   3,408   3,674
29 | 0,256 0,683 1,311 1,699 2,045  2,462  2,756  3,038   3,396   3,660
30 | 0,256 0,683 1,310 1,697 2,042  2,457  2,750  3,030   3,385   3,646
40 | 0,255 0,681 1,303 1,684 2,021  2,423  2,704  2,971   3,307   3,551
60 | 0,254 0,679 1,296 1,671 2,000  2,390  2,660  2,915   3,232   3,460
120| 0,254 0,677 1,289 1,658 1,980  2,358  2,617  2,860   3,160   3,373
∞  | 0,253 0,674 1,282 1,645 1,960  2,326  2,576  2,807   3,090   3,290
```
De nuestro enorme lago de peces, vamos a tomar dos muestras (las muestras son **aleatorias** e **independientes**):
- A la muestra 1, formada por _n1_ peces, se le ha suministrado el tratamiento 1
- A la muestra 2, formada por _n2_ peces, se le ha suministrado el tratamiento 2

Por lo tanto, el número total de peces que hemos tratado será _n_ = _n1_ + _n2_. Para saber si el **tipo del tratamiento** influye en el **gen mutante**, vamos a comparar las medias de ambas muestras, tenemos que ver cuál de los siguientes casos ocurre: si hay o no hay diferencia significativa comparando los intervalos de confianza:

_**Leyenda**_
* μ = media de la muestra
* |-------- μ --------| = Intervalo de Confianza
* s = Cuasivarianza
* α = nivel de confianza

Caso 1: No hay diferencia significativa

```
|-------- μ1 --------|
           |-------- μ2 --------|
```

Caso 2: Sí hay diferencia significativa

```
|-------- μ1 --------|
                         |-------- μ2 --------|
```

Plantearemos, lo primero, las hipótesis, siendo H0 la hipótesis nula:

* `H0: μ1 - μ1 = 0`
* `H1: μ1 - μ1 != 0`

Después, hay que considerar los casos de **homocedasticidad** y **heterocedasticidad**

* **Homocedasticidad**: Cuando la varianza del error condicional es constante:
_**Nota**: `s` es la varianza de una de las muestras_

1. Calcular t

```
t = μ1 - μ1 / sqrt( s * (1/n1 + 1/n2))
```

2. Buscar el valor de t en la tabla para la confianza α y con n1 + n2 − 2 grados de libertad

```
t_ = (1 − α) / 2, n1 + n2 − 2
```

3. Comparar

```
|t| > t_
```

* **heterocedasticidad**: Cuando la varianza del error condicional **no** es constante:
_**Nota**: `s1` es la varianza de la muestra 1 y `s2` es la varianza de la muestra 2_

1. Calcular t

```
t = μ1 - μ1 / sqrt( s1/n1 + s2/n2)
```

2. Buscar el valor de t en la tabla para la confianza α y con n1 + n2 − 2 grados de libertad

```
t_ = (1 − α) / 2, n1 + n2 − 2
```

3. Comparar

```
|t| > t_
```

## Método 2: Análisis de la Varianza

Este análisis permite averiguar si el resultado de un experimento es significativo, es decir: saber si hay que descartar la hipótesis nula o aceptar la hipótesis alternativa. Está indicado para variables y normales con igual varianza (homocedasticidad).

Usamos ANOVA de un factor cuando queremos saber si las medias de una variable son diferentes entre los niveles o grupos de otra variable.

**Condiciones:**

* En ANOVA de un factor solo se relacionan dos variables: una variable dependiente (o a explicar) y una variable independiente (que en esta técnica se suele llamar factor)
* La variable dependiente es cuantitativa (escalar) y la variable independiente es categórica (nominal u ordinal).
* Se pide que las variables sigan la distribución normal, aunque como siempre esto es difícil de cumplir en investigaciones sociales.
* También que las varianzas (es decir, las desviaciones típicas al cuadrado) de cada grupo de la variable independiente sean similiares (homocedasticidad). Aunque esto es lo ideal, en la realidad cuesta de cumplir, e igualmente se puede aplicar ANOVA

**El estadístico F o F-test (se llama F en honor al estadístico Ronald Fisher) se obtiene al estimar la variación de las medias entre los grupos de la variable independiente y dividirla por la estimación de la variación de las medias dentro de los grupos. Si hacemos varios análisis de ANOVA de un factor, aquel con F más alto indicará que hay más diferencias y por tanto una relación más fuerte entre las variables. Cuanto más difieren las medias de la variable dependiente entre los grupos de la variable independiente, más alto será el valor de F.**

**Metáfora de los Peces Mutantes**

Vamos a suponer que tenemos tres lagos de peces mutantes. Debido a la mutación, los peces pueden tener números distintos de ojos (en concreto, de 1 a 10 ojos). En cada lago hay un tipo de mutación distinta, y queremos saber cómo influye el tipo de mutación en el número de ojos de los peces mutantes. Se establece una **variable explicativa** que, será el **número de ojos** por pez.

En este caso, diríamos que la hipótesis nula es que la media de ojos es la misma en los tres lagos y que, por lo tanto, no influye el tipo de mutación en el número de ojos de los peces mutantes. La hipótesis alternativa es que la media de ojos es distinta y sí que influye.

**Valores necesarios:**

* media de las tres muestras: `m`
* media de cada una de las muestras: `m1`, `m2`... `m_n`
* número total de valores: `n`
* número de valores de cada muestra:  `n1`, `n2`... `n_n`
* número de muestras: r

1. Creamos la tabla ANOVA, donde

* SCE: Suma de Cuadrados de la variable Explicativa
```
SCE = n1(m1 - m)^2 + n2(m2 - m)^2 + .. + n_n(m_n - m)^2
```
* SCR: Suma de Cuadrados de la variable Residual
```
SCR = (m1 - m)^2 + (m2 - m)^2 + .. + (m_n - m)^2
```
* SCT: Suma de Cuadrados Total = SCE + SCR
* GLE: Grados de Libertad de la parte Explicativa = `r − 1`
* GLR: Grados de Libertad de la parte Residual = `n − r`
* GLT: Grados de Libertad Totales = GLE + GLR
* CME: Cuadrado Medio Explicado = SCE / GLE
* CMR: Cuadrado Medio Residual = SCR / GLR
* F = CME / CMR
* CMT: Cuadrado Medio Total

|             | Suma Cuadrados | Cuadrados Medios | Grados Libertad |   F   | p - valor |
|-------------|----------------|------------------|-----------------|-------|-----------|
| Explicativa |      SCE       |        CME       |       GLE       |   F   | p - valor |
| Residual    |      SCR       |        CMR       |       GLR       |       |           |
| Total       |      SCT       |        CMT       |       GLT       |       |           |
