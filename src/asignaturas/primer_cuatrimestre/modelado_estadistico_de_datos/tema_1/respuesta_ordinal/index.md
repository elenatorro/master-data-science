# Respuesta Ordinal

Una respuesta ordinal es aquella que puede obtener valores dentro de un rango numérico ordenado. En esta sección se ven tres métodos:

> **Nota:** En los siguientes tests, también vale para una variable respuesta Y **nominal** si dicha variable respuesta Y **no es normal** en cada categoría.

- A través de una variable X explicativa dicotómica:

* U de Mann-Whitney
* W de Wilcoxon

_Nota: ambos tests son **equivalentes**_

- A través de una variable X explicativa nominal:

* H de Kruskal-Wallis

**Metáfora de los peces mutantes**

Supongamos que clasificamos a los peces según un grado de mutación que puede variar del 1 al 5, siendo 1 poco mutante y 5 muy mutante.

## U de Mann-Whitney

En este caso, tendremos 2 tratamientos y analizaremos 2 muestras de peces.

**Formulación de la hipótesis:**

- `H0 : F1 = F2`
- `H1 : F1 != F2`

**Valores:**

* Número de valores por muestra: n1 y n2
* Número total de valores: n
* Mediana de cada muestra: m1 y m2
* Rango intercuartílico de cada muestra: r1 y r2
* Número de valores **distintos** que se produce para cada valor de la variable respuesta sin distinguir grupos: `k`
* Número de empates desde j = 1 hasta j = k: `d_1 ... d_k`

```
sumatorio j=1, k ==> d^3 - d
U = sqrt((1 / 12) * ((n1 * n2)/n(n - 1)) * (n^3 - n - sumatorio))
```

## W de Wilcoxon

## H de Kruskal-Wallis

**Formulación de la hipótesis:**

```
H0 : F1 = F2 = F3 = ... = Fn
H1 : Alguna Fi distinta
```

![Kruskal-Wallis formula](../../../../../assets/img/kruskal-wallis.svg)