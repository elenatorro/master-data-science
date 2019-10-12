# Tema 1 - Principales Técnicas Estadísticas

## Introducción

### Distribuciones Teóricas de Probabilidad

* Distribución: reparto de elementos / individuos de un grupo / población según una característica

> Ejemplo: **Distribución de caramelos con azúcar y sin azúcar en una bolsa de caramelos.** Tenemos una bolsa de caramelos donde hay una mezcla de caramelos con azúcar y caramelos sin azúcar. Si existe el mismo número de caramelos con y sin azúcar, diríamos que es una distribución **uniforme**. La probabilidad de sacar un caramelo sin azúcar de la bolsa es 0,5.

#### Distribución de Frecuencias vs Distribución de Probabilidad

* Distribución de Frecuencias: Reparto empírico _(empírico = basado en la observación)_ observado en una **colección de datos.** Agrupación de datos en categorías mutuamente excluyentes _(caramelos con o sin azúcar)_ que indican el número de observaciones en cada categoría.

* Distribución de Probabilidad: Reparto teórico de la población, una función matemática. La distribución de probabilidad está definida sobre el **conjunto** de todos los sucesos, y cada uno de los sucesos es el **rango de valores** de la **variable aleatoria**. Describe cómo se espera que varíen los resultados.

* Variable Aleatoria: Función que asigna un valor, usualmente numérico, al resultado de un experimento aleatorio. Por ejemplo, los posibles resultados de sacar tres caramelos de la bolsa de caramelos.

> Ejemplo:
  * **Conjunto de Datos:** Bolsa con N caramelos (donde N puede ser cualquier número de caramelos) donde hay dos tipos de caramelos: con y sin azúcar.
  * **Variable Aleatoria:** sacar tres caramelos de la bolsa de caramelos
  * **Posibles resultados:** [con, sin, sin], [sin, con, sin], [sin, sin , sin]...

### Tipos de Variables

* **Variable aleatoria:** Es aquella cuyo valor es el resultado de un evento aleatorio. Lo que quiere decir que son los resultados que se presentan al azar en cualquier evento o experimento.
  * **Variable aleatoria discreta:** Es aquella que solo toma ciertos valores y que resulta principalmente del conteo realizado. Por ejemplo, que los caramelos sean con o sin azúcar.
  * **Variable aleatoria continua:** Es aquella que resulta generalmente de la medición y puede tomar cualquier valor dentro de un intervalo dado. Por ejemplo, si nuestra bolsa de caramelos contiene caramelos redondos que pueden tener tamaños distintos, desde ser una bolita "pequeña" hasta una bolita "grande", pasando por todos los tamaños intermedios.

Otros datos importantes:

* **Covarianza**: valor que indica el grado de variación conjunta de dos variables aleatorias respecto a sus medias.
    * Cuando los valores altos de una de las variables suelen mayoritariamente corresponderse con los valores altos de la otra, y lo mismo se verifica para los pequeños valores de una con los de la otra, se corrobora que tienden a mostrar comportamiento similar lo que se refleja en un valor positivo de la covarianza1​
    * Por el contrario, cuando a los mayores valores de una variable suelen corresponder en general los menores de la otra, expresando un comportamiento opuesto, la covarianza es negativa.
    * El signo de la covarianza, por lo tanto, expresa la tendencia en la relación lineal entre las variables.

## Respuesta Dicotómica

Intenta dar una respuesta a una variable dicotómica a través de otra variable dicotómica.

En la lógica tradicional, la dicotomía es el desglose o fraccionamiento de un concepto genérico en uno de sus conceptos específicos y su negación. El concepto se refiere asimismo a la ley que establece que ninguna proposición puede ser verdadera y falsa al mismo tiempo.

> Ejemplo: un caramelo puede ser con o sin azúcar, pero no puede ser con y sin azúcar al mismo tiempo.

Un grupo de peces tiene una misma enfermedad. Hay dos tratamientos: A y B. A un grupo de peces se les administra el tratamiento A, y al otro grupo el tratamiento B. Se observa qué peces se curan (CURADOS) y qué peces no se curan (NO CURADOS).

| Tratamiento | Curación |
|-------------|-----------|
| A | CURADO |
| A | NO CURADO |
| B | CURADO |
| A | CURADO |
| ... | ... |
| B | NO CURADO |
| B | NO CURADO |
| A | NO CURADO |
| B | CURADO |
| A | CURADO |

> La pregunta es, ¿influye el **tratamiento** en la **curación**? Para ello, hay que comparar la proporción de los peces curados con el tratamiento A con la proporción de los peces curados con el tratamiento B.

**Nota: El Teorema Central del Límite al Rescate**: Este método se utiliza con tamaños de muestra **grandes**. Es decir, en el ejemplo anterior, tener pocos pececillos enfermos no es suficiente para conocer cuál es el tratamiento adecuado para que se curen los pobrecillos. Si tenemos muchos peces, el resultado será más fiable, y esto lo conocemos gracias al **Teorema Central del Límite**.

- **Teorema Central del Límite**: Indica que, en condiciones muy generales, si la suma de n variables aleatorias independientes y cuya dispersión se puede cuantificar, entonces la función de distribución de Sn _«se aproxima bien»_ a una **distribución normal** (también llamada distribución gaussiana, curva de Gauss o campana de Gauss).

- **Distribución Normal**: Esta distribución es muy utilizada en estadística ya que permite representar numerosos fenómenos, como por ejemplo, el de los pececillos enfermos, pero también muchos otros de caracteres naturales, sociales, psicológicos, etc. La distribución normal se basa en la justificación de que una observación, o resultado final, se puede obtener como la suma de causas pequeñas independientes. La distribución normal es la más extendida en estadística y muchos tests estadísticos están basados en una "normalidad" más o menos justificada de la variable aleatoria bajo estudio.

**Explicación**

> Esta es la comprobación matemática de que nos podemos fiar de un conjunto lo suficientemente grande de datos para dar una respuesta a un problema. Por ejemplo, supongamos que el problema de los peces ocurre en un lago en el que hay millones de peces que han sufrido una enfermedad debido a unos vertidos tóxicos. No necesitamos hacer el estudio con todos los millones de peces del lago para conocer qué tratamiento es necesario aplicar, sino que nos bastaría con una muestra de peces grande (que no te vale con diez pececillos, vaya.)

### Método 1: z diferencia entre dos proporciones

El objetivo de estas pruebas es evaluar las afirmaciones con respecto a una proporción de población. Las pruebas se basan en la premisa de que una proporción muestral será igual a la proporción verdadera de la población si se toman márgenes o tolerancias para la variabilidad muestral (**teorema central del límite**). Las pruebas suelen enfocarse en la diferencia entre un número esperado de ocurrencias, suponiendo que una afirmación es verdadera, y el número observado realmente.

El **nivel de significancia** es el valor que queremos establecer al formular la pregunta para poder afirmar la hipótesis final. Es decir, un número que al final lo utilizamos para hacer una comparativa. La significancia la obtenemos de la distribución z normal (de ahí que este método se llame "z diferencia"). Dicho valor lo podemos obtener automáticamente si estamos programando, o manualmente en esta tabla, Donde, por ejemplo:

Una significancia de `0.025` tiene un valor z de `-1.96` (fila 1.9, columna 0.06 )

```
z	    .00	    .01	    .02	    .03	    .04	    .05	    .06	    .07	    .08	    .09
-4.0	0.00003	0.00003	0.00003	0.00003	0.00003	0.00003	0.00002	0.00002	0.00002	0.00002
-3.9	0.00005	0.00005	0.00004	0.00004	0.00004	0.00004	0.00004	0.00004	0.00003	0.00003
-3.8	0.00007	0.00007	0.00007	0.00006	0.00006	0.00006	0.00006	0.00005	0.00005	0.00005
-3.7	0.00011	0.00010	0.00010	0.00010	0.00009	0.00009	0.00008	0.00008	0.00008	0.00008
-3.6	0.00016	0.00015	0.00015	0.00014	0.00014	0.00013	0.00013	0.00012	0.00012	0.00011
-3.5	0.00023	0.00022	0.00022	0.00021	0.00020	0.00019	0.00019	0.00018	0.00017	0.00017
-3.4	0.00034	0.00032	0.00031	0.00030	0.00029	0.00028	0.00027	0.00026	0.00025	0.00024
-3.3	0.00048	0.00047	0.00045	0.00043	0.00042	0.00040	0.00039	0.00038	0.00036	0.00035
-3.2	0.00069	0.00066	0.00064	0.00062	0.00060	0.00058	0.00056	0.00054	0.00052	0.00050
-3.1	0.00097	0.00094	0.00090	0.00087	0.00084	0.00082	0.00079	0.00076	0.00074	0.00071
-3.0	0.00135	0.00131	0.00126	0.00122	0.00118	0.00114	0.00111	0.00107	0.00103	0.00100
-2.9	0.00187	0.00181	0.00175	0.00169	0.00164	0.00159	0.00154	0.00149	0.00144	0.00139
-2.8	0.00256	0.00248	0.00240	0.00233	0.00226	0.00219	0.00212	0.00205	0.00199	0.00193
-2.7	0.00347	0.00336	0.00326	0.00317	0.00307	0.00298	0.00289	0.00280	0.00272	0.00264
-2.6	0.00466	0.00453	0.00440	0.00427	0.00415	0.00402	0.00391	0.00379	0.00368	0.00357
-2.5	0.00621	0.00604	0.00587	0.00570	0.00554	0.00539	0.00523	0.00508	0.00494	0.00480
-2.4	0.00820	0.00798	0.00776	0.00755	0.00734	0.00714	0.00695	0.00676	0.00657	0.00639
-2.3	0.01072	0.01044	0.01017	0.00990	0.00964	0.00939	0.00914	0.00889	0.00866	0.00842
-2.2	0.01390	0.01355	0.01321	0.01287	0.01255	0.01222	0.01191	0.01160	0.01130	0.01101
-2.1	0.01786	0.01743	0.01700	0.01659	0.01618	0.01578	0.01539	0.01500	0.01463	0.01426
-2.0	0.02275	0.02222	0.02169	0.02118	0.02067	0.02018	0.01970	0.01923	0.01876	0.01831
-1.9	0.02872	0.02807	0.02743	0.02680	0.02619	0.02559	0.02500	0.02442	0.02385	0.02330
-1.8	0.03593	0.03515	0.03438	0.03362	0.03288	0.03216	0.03144	0.03074	0.03005	0.02938
-1.7	0.04456	0.04363	0.04272	0.04181	0.04093	0.04006	0.03920	0.03836	0.03754	0.03673
-1.6	0.05480	0.05370	0.05262	0.05155	0.05050	0.04947	0.04846	0.04746	0.04648	0.04551
-1.5	0.06681	0.06552	0.06425	0.06301	0.06178	0.06057	0.05938	0.05821	0.05705	0.05592
-1.4	0.08076	0.07927	0.07780	0.07636	0.07493	0.07353	0.07214	0.07078	0.06944	0.06811
-1.3	0.09680	0.09510	0.09342	0.09176	0.09012	0.08851	0.08691	0.08534	0.08379	0.08226
-1.2	0.11507	0.11314	0.11123	0.10935	0.10749	0.10565	0.10383	0.10204	0.10027	0.09852
-1.1	0.13566	0.13350	0.13136	0.12924	0.12714	0.12507	0.12302	0.12100	0.11900	0.11702
-1.0	0.15865	0.15625	0.15386	0.15150	0.14917	0.14686	0.14457	0.14231	0.14007	0.13786
-0.9	0.18406	0.18141	0.17878	0.17618	0.17361	0.17105	0.16853	0.16602	0.16354	0.16109
-0.8	0.21185	0.20897	0.20611	0.20327	0.20045	0.19766	0.19489	0.19215	0.18943	0.18673
-0.7	0.24196	0.23885	0.23576	0.23269	0.22965	0.22663	0.22363	0.22065	0.21769	0.21476
-0.6	0.27425	0.27093	0.26763	0.26434	0.26108	0.25784	0.25462	0.25143	0.24825	0.24509
-0.5	0.30853	0.30502	0.30153	0.29805	0.29460	0.29116	0.28774	0.28434	0.28095	0.27759
-0.4	0.34457	0.34090	0.33724	0.33359	0.32997	0.32635	0.32276	0.31917	0.31561	0.31206
-0.3	0.38209	0.37828	0.37448	0.37070	0.36692	0.36317	0.35942	0.35569	0.35197	0.34826
-0.2	0.42074	0.41683	0.41293	0.40904	0.40516	0.40129	0.39743	0.39358	0.38974	0.38590
-0.1	0.46017	0.45620	0.45224	0.44828	0.44433	0.44038	0.43644	0.43250	0.42857	0.42465
-0.0	0.50000	0.49601	0.49202	0.48803	0.48404	0.48006	0.47607	0.47209	0.46811	0.46414
```

Ejemplo:

Queremos saber si los caramelos de fresa suelen ser los preferidos, con respecto a los caramelos de limón, entre los **Jugadores de Rugby Americanos** y los **Jugadores de Rugby Australianos**, con un valor de significancia de 0.07. Se han tomado los siguientes datos:

- Dada una muestra de 200 jugadores americanos, se obtuvo que 56 de ellos prefieren los caramelos de fresa.
- Dada una muestra de 150 jugadores australianos, se obtuvo que, por el contrario, 29 de ellos prefieren los caramelos de limón.

1. Hipótesis:

- Hipótesis 0: Ni fu ni fa
- Hipótesis 1: Hay una diferencia de proporción

Es **muy importante** enfatizar en que partimos de la premisa de que la hipótesis 0 es verdadera, y que por esto utilizaremos la **proporción combinada** para descartar dicha hipótesis (si la hipótesis 0 es verdadera, no hay diferencia entre las proporciones)

1. Diferencia de proporciones:

Proporción de caramelos de fresa de la primera muestra: 56 / 200 = 0.28
Proporción de caramelos de limón de la segunda muestra: 29 / 150 = 0.193

Como 0.28 es mayor que 0.193, queremos probar hipótesis de que prefieren la fresa.

`diferencia_de_proporciones` = 0,28 - 0,193 = 0,087

2. Proporción combinada: Probabilidad de que la hipótesis 0 sea correcta (o probabilidad de 'éxito' de nuestra hipótesis)

probabilidad éxito (p) = 56 + 29 / 200 + 150 = 0,2429
probabilidad de fracaso (q) = 1 - p = 0,7571

3. Calcular la varianza de ambas muestras (a partir de las probabilidades de éxito y fracaso)

p * q = 0,18389959

varianza muestra 1: p * q / 200 = 0,00091949795
varianza muestra 2: p * q / 150 = 0,001225997266667

4. Calcular la desviación estandar de la distribución muestral de las diferencias de las proporciones muestrales

Por definición, la varianza teórica de las dos muestras está dada por: La varianza de la muestra 1 más la varianza de la muestra 2 por la **covariancia** de ambas muestras por dos.

Por lo tanto, la desviación estandar (la 'z' que queremos comparar con la significancia) será la raíz cuadrada de la suma de la varianza de la muestra 1 con la varianza de la muestra 2:

`desviación_estándar` = `raíz_cuadrada(varianza_muestra_1 + varianza_muestra_2)` = 0,046319490677975

5. Calcular el valor z:

`diferencia_de_proporciones` / `desviación_estándar` = 1,878258994790041

6. Comparar la z obtenida a través de la significancia con la z obtenida a través de la diferencia de proporciones

z0 = 0.07 --> 1,48
z1 = 1,88

> Como 1,88 es mayor de 1,48, rechazamos la primera hipótesis (ni fu ni fa) y podemos concluir que, con un 7% de significancia, hay una diferencia de proporción entre pertenecer al equipo americano y preferir los caramelos de fresa.

### Método 2: Exacta de Fisher

Este método se utiliza para tamaños de muestra **pequeños**. Se utiliza, para ello, una tabla de contingencia que relaciona las variables de las dos muestras.

1. Cálculo del p-valor

El p-valor consiste en calcular la probabilidad exacta de observar un conjunto concreto de cuatro frecuencias: a, b, c y d. Con el ejemplo de los jugadores de rugby, sería:

Jugador de Rugby Americano
Jugador de Rugby Australiano
Prefiere los caramelos de fresa
Prefiere los caramelos de limón

| Jugador / Caramelo       | Preferencia Fresa        | Preferencia Limón        | Total                    |
|--------------------------|--------------------------|--------------------------|--------------------------|
| Americano                |            a             |            b             |          a + b           |
| Australiano              |            c             |            d             |          c + d           |
| Total                    |          a + c           |          b + d           |            n             |

`p_valor` = (a+b)!(a+c)!(b+d)!(c+d)! / n!a!b!c!d!

2. Comparar `p_valor` con el nivel de significancia alfa.

* p < alfa, se rechaza la hipótesis
* p >= alfa, se acepta la hipótesis

> Ejemplo

  Tenemos una muestra de 35 jugadores: 17 jugadores americanos y 18 australianos. De americanos, 10 de ellos prefieren los caramelos de fresa, y los 7 restantes los de limón. Por otro lado, 5 de los australianos prefieren los caramelos de fresa y 13 los de limón.

La **variable explicativa** es la nacionalidad del equipo, y la **variable respuesta** la preferencia de sabor (fresa o limón)

Tabla:

| Jugador / Caramelo       | Preferencia Fresa        | Preferencia Limón        | Total                    |
|--------------------------|--------------------------|--------------------------|--------------------------|
| Americano                |            10            |            7             |           17             |
| Australiano              |             5            |           13             |           18             |
| Total                    |            15            |           20             |           35             |

`p_valor` = 17!18!15!20! / 35!10!7!5!13! = 0,092

Como 0,092 es menor que el valor de significancia, no se rechaza la hipótesis nula ya que no hay evidencia para concluir que la variable explicativa influya en la variable respuesta de forma significativa. Es decir, no es significante la nacionalidad del equipo para que prefiera los caramelos de fresa sobre los de limón.

## Respuesta Continua

La variable respuesta es una variable que puede tomar valores continuos.

#### t de Student

Se está intentando explicar la variable respuesta continua a trav éss de la variable explicativa dicotómica.

Imaginemos a nuestros pobres pececillos del lago. Ahora, en lugar de estar curados o no en base a un tratamiento, digamos que estos peces tienen un gen mutante. Este gen mutante puede adquirir multitud de valores, pero estos valores pueden depender del tratamiento que se le suministre al pez. Como estamos probando dos tratamientos, queremos conocer qué tratamiento produce según qué valores del gen.

## Respuesta Nominal
## Respuesta Ordinal

## Bibliografía

- [El test z para comparar dos proporciones (umh2072 2013-14)](https://www.youtube.com/watch?v=HMuS0VYMR6Y)
- [Distribución Normal - Wikipedia](https://es.wikipedia.org/wiki/Distribuci%C3%B3n_normal)
- [MaximaFormacion - Diferencias entre las proporciones de 2 poblaciones diferentes](https://www.maximaformacion.es/blog-dat/diferencias-entre-las-proporciones-de-2-poblaciones-diferentes/)
- [Prueba hipótesis z diferencia de dos proporciones](https://www.youtube.com/watch?v=vTYYEXG0jWo)
- [Apuntes](https://revistaseden.org/files/11-CAP%2011.pdf)
- [Prueba exacta de Fisher](https://www.youtube.com/watch?v=A6XJjFUNeYM)