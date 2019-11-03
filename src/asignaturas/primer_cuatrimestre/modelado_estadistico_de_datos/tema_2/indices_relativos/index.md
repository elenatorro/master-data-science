## Riesgo Relativo

El Riesgo relativo es el **cociente** entre el riesgo en el grupo con el factor de exposición o factor de riesgo y el riesgo en el grupo de referencia, que no tiene el factor de exposición. Es un concepto estadístico utilizado como medida de **asociación** entre la variable dependiente y la variable independiente.

El riesgo relativo es válido en estudios prospectivos y el odds ratio en prospectivos, retrospectivos y transversales. A la hora de calcular intervalos de confianza para estos índices habrá que utilizar el teorema de Taylor para variables aleatorias.

|             |  X = 1   |  X = 0   |  Total  |
|-------------|----------|----------|---------|
| Y = 1       | a        | b        |  a + b  |
| Y = 0       | c        | d        |  c + d  |
| Total       | a + c    | b + d    |  N      |

El rr es un índice relativo de asociación entre dos variables dicotómicas y admite, por su definición, una **interpretación directa.** Por ejemplo:

* Si `rr = 3 > 1`, la probabilidad de presencia de Y en los individuos con X = 1 es el triple que la probabilidad
de presencia de Y en los individuos con X = 0.
* Si `rr = 1`, hay la misma probabilidad de presencia de Y en los individuos con X = 1 que en lo individuos
con X = 0.
* Si `rr = 1 / 3`, la probabilidad de presencia de Y en los individuos con X = 1 es un tercio de la probabilidad
de presencia de Y en los individuos con X = 0.

Al ser el riesgo relativo `rr` una v.a. **asimétrica** (su rango es (0, ∞)), su distribución es **no normal**. Es conveniente, por tanto, considerar una transformación que consiga normalidad con media teórica y varianza teórica que se puedan estimar fácilmente. Se puede demostrar que la transformación logaritmo neperiano (Ln) consigue este propósito. A efectos teóricos, ahora es `θ = Ln(rr)`.

Para calcular el valor `z_1-α/2`, se pueden utilizar los siguientes métodos:

* Test z de diferencia de proporciones
* Test de Fisher
* Test χ^2

**Riesgo Relativo:**

```
riesgo_relativo = (a / (a+c)) / (b / (b+d))
```

**Error Estándar:**

```
error_estandar = sqrt((1 / a) - (1 / (a+c)) + (1 / b) - (1 / (b+d)))
```

**Intervalo de Confianza:**

```
IC(1 − α)%(riesgo_relativo) = (exp(Ln(riesgo_relativo) +- z_1-α/2 * error_estandar))
```

### Contraste de hipótesis

```
H0 : riesgo_relativo = 1
H1 : riesgo_relativo != 1
```

## Odds Ratio

En general, dada π una proporción (probabilidad) cualquiera, se define el parámetro poblacional `o`, odds de una proporción, como el cociente de las probabilidades complementarias.

Es decir, `o = π / 1−π`, con lo que `o ∈ (0, ∞)`. En el caso de considerar el odds de enfermedad, su valor se interpreta de la forma siguiente:

* Si `o = 3 > 1`, se tiene que la probabilidad de estar enfermo es el **triple** de la de estar sano, o lo que es lo mismo que `P(Y = 1) = 3 / 3+1 = 0.75 y P(Y = 0) = 0.25.`
* Si `o = 1`, hay la misma probabilidad de estar enfermo que de estar sano.
* Si `o = 1 / 3`, se tiene que la probabilidad de estar enfermo es **un tercio** de la de estar sano, o lo que es lo mismo que `P(Y = 1) = (1/3) / (1/3+1) = 0.25 y P(Y = 0) = 0.75.`.

Utilizando el teorema de Bayes, es fácil ver que `orX = orY` , es decir que el odds ratio de presencia de Y respecto a X es el mismo que el odds ratio de presencia de X respecto a Y . Por ello, se puede hablar simplemente de odds ratio, `or`, y se puede calcular en todo tipo de estudios.

Por consiguiente:

```
or = (ad / bc)
```

> Nota: por esto al odds ratio también se le llama razón de productos cruzados.

El or es un índice relativo de asociación entre dos variables dicotómicas y se puede demostrar los siguientes tres casos:

* `or > 1 ⇔ P(Y = 1|X = 1) > P(Y = 1|X = 0)`, por lo que la presencia de X favorece la presencia de Y.
* `or = 1 ⇔ P(Y = 1|X = 1) = P(Y = 1|X = 0)`, por lo que la presencia de X ni favorece ni desfavorece la presencia de Y.
* `or < 1 ⇔ P(Y = 1|X = 1) < P(Y = 1|X = 0)`, por lo que la presencia de X desfavorece la presencia de Y.

Lo que se traduce a:

En el caso de que Y sea la variable “Enfermedad” codificada con 1 en el caso de “Sí enfermo” y con 0 en el caso de “No enfermo” y que X sea la variable “Exposición” codificada con 1 en el caso de “Sí expuesto” y con 0 en el caso de “No expuesto”, la interpretación anterior del or se puede hacer de forma más clara:

* Si `or > 1 ⇔ X` es un factor de riesgo.
* Si `or = 1 ⇔ X` no es ni un factor de riesgo ni un factor protector
* Si `or < 1 ⇔ X` es un factor protector.

Al ser el riesgo relativo `or` una v.a. **asimétrica** (su rango es (0, ∞)), su distribución es **no normal**. Es conveniente, por tanto, considerar una transformación que consiga normalidad con media teórica y varianza teórica que se puedan estimar fácilmente.  Se puede demostrar que la transformación logaritmo neperiano (Ln) consigue este propósito. A efectos teóricos, ahora es `θ = Ln(or)`.

### Intervalo de confianza

_Nota: no sigue una distribución normal_

**Odds Ratio:**

```
odds_ration = ad / bc
```

**Error Estándar:**

```
error_estandar = sqrt(1/a + 1/b + 1/c + 1/d)
```

Dado una significancia de α, calculamos el intervalo de confianza al `(1 - α)%`:

**Intervalo de Confianza:**

```
IC(1 − α)%(ad / bc) =  exp(Ln(odds_ratio) +- z_1-α/2 * error_estándar))
```

### Contraste de hipótesis

```
H0 : odds_ratio = 1
H1 : odds_ratio != 1
```