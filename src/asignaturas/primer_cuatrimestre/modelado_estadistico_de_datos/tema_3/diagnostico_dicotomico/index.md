## Introducción

* X = 1 indica que la prueba diagnóstica afirma que el individuo **está enfermo**
* X = 0 indica que la prueba diagnóstica afirma que el individuo **está sano**
* Y = 1 indica que la prueba diagnóstica afirma que el individuo **está realmente enfermo**
* Y = 0 indica que la prueba diagnóstica afirma que el individuo **está realmente sano**

|             | X = 1                  | X = 0                  |  Total  |
|-------------|------------------------|------------------------|---------|
| Y = 1       | a = Verdadero Positivo | b = Falso Negativo     |  a + b  |
| Y = 0       | c = Falso Positivo     | d = Verdadero Negativo |  c + d  |
| Total       | a + c                  | b + d                  |  N      |

En el caso de índices de riesgo, se indicaría si el individuo está expuesto o no a un índice de riesgo.

## Sensibilidad y especificidad

La sensibilidad y especificidad son **proporciones poblacionales** (por lo tanto, comprendidas entre 0 y 1)

* Sensibilidad: _"Acierto en enfermos”_. Está dado por `P(X = 1|Y = 1)`

```
sensibilidad = a / a + c
```

* Especificidad: _"Acierto en sanos"_. Está dado por `P(X = 0|Y = 0)`

```
especificidad = d / b + d
```

* Fracción de verdaderos positivos = sensibilidad = `P(X = 1|Y = 1)`
* Fracción de falsos positivos = 1 - especificidad = 1 - `P(X = 0|Y = 0)` = `P(X = 1|Y = 0)`

> Se puede comprobar que se y es no dependen de la prevalencia (la probabilidad de enfermedad, `π = P(Y = 1)`), por lo que son útiles para reflejar la bondad de una prueba diagnóstica

**Índice de Youden:**

```
youden = se + es − 1
```

**Eficacia**

```
eficacia = πse + (1 − π)es
```

## Valor predictivo

> La principal diferencia de los valores predictivos con respecto a la sensibilidad y especificidad, es que los valores predictivos **sí dependen de la prevalencia** (la probabilidad de enfermedad, `π = P(Y = 1)`), por lo que **no son útiles** para reflejar la bondad de una prueba diagnóstica

### Positivo

**Parámetro poblacional** que indica el acierto en los individuos positivos según la prueba diagnóstica

```
valor_predictivo_positivo = π11 = P(Y = 1|X = 1) = a / a + c
```

### Negativo

**Parámetro poblacional** que indica el acierto en los individuos negativos según la prueba diagnóstica

```
valor_predictivo_negativo = π00 = P(Y = 0|X = 0) = d / b + d
```

## Razón de verosimilitud

Las razones de verosimilitud no son proporciones sino **razones** (un cociente de proporciones, en este caso) y que están comprendidos en el intervalo `(0, ∞)`. Por su definición, al ser en términos de sensibilidad y especificidad, no dependen de la prevalencia.

Al estar comprendidas en el intervalo `(0, ∞)`, su distribución **no es normal**. Por esto, utilizamos la transformación logaritmo neperiano (Ln) para conseguir normalidad con **media** y **varianza** teóricas que se puedan estimar fácilmente.

### Positiva

**Parámetro poblacional** que representa la ganancia de información cuando la prueba diagnóstica da positivo. Si `razon_verosimilitud_positiva > 1`, es más probable que un resultado positivo en la prueba diagnóstica se dé en un sujeto enfermo que en uno sano.

```
razon_verosimilitud_positiva = π11 / π10 =  P(Y = 1|X = 1) /  P(Y = 1|X = 0) = sensibilidad / 1 - especificidad
```

**Error Estimado:**

```
error = Ln(sensibilidad / 1 - especificidad)
```

```
error_estimado = sqrt(
  ((1 / (a+b)) * (1 - sensibilidad / sensibilidad))
  +
  ((1 / (c+d)) * (especificidad / 1 - especificidad))
)
```

**Intervalo de confianza:**

```
IC = exp(Ln(sensibilidad / 1 - especificidad)) +- z_1−α/2 * error_estimado
```

### Negativa

**Parámetro poblacional** que representa la ganancia de información cuando la prueba diagnóstica da negativo. Si `razon_verosimilitud_negativa < 1`, es más probable que un resultado negativo en la prueba diagnóstica se dé en un sujeto enfermo que en uno sano.

```
razon_verosimilitud_negativa = π11 / π10 =  P(Y = 0|X = 1) /  P(Y = 0|X = 0) = 1 - sensibilidad / especificidad
```

```
error = Ln(1 - sensibilidad / especificidad)
```

```
error_estimado = sqrt(
  ((1 / (a+b)) * (especificidad / 1 - especificidad))
  +
  ((1 / (c+d)) * (1 - sensibilidad / sensibilidad))
)
```
