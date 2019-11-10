# Tasa de error

La precisión de un modelo depende tanto del ajuste de la regresión, como el caso del _trade-off_ de sesgo y varianza, pero también depende la clasificación.

Supongamos que queremos estimar `f` basándonos en los datos de entrenamiento `{(x1, y1),...,(xn, yn)}` donde `y1,...,yn` son **cualitativos**. La aproximación más compún para cuantificar la aproximación de `f'` es el _training error rate_, la proporción de errores que haremos si aplicamos `f'` a los datos de entrenamiento:

```
training_error_rate = 1 / n * [I(y0 != y'0), ..., I(yn != y'n)]
```

Donde:
* `y'i`: categoría que predecimos de yi utilizando f'
* `I(yi != y'i)`: **indicador** que será `1` si  `yi != y'i`, es decir, si son **distintos**, y `0` en caso contrario, si `yi == y'i`, es decir, si son **iguales**. Si es `0` quiere decir que se ha clasificado **correctamente**.

Por lo que el **training_error_rate** es la fracción de las categorías incorrectamente clasificadas.

El `test error rate` será la media de aplicar el clasificador, donde un buen clasificador es aquel con el menor test error rate:

```
test_error_rate = Ave(I(y0 = y'0))
```

# Clasificador Bayesiano

<iframe width="560" height="315" src="https://www.youtube.com/embed/949tYJgRvRg" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# K-Nearest Neighbors

<iframe width="560" height="315" src="https://www.youtube.com/embed/ENSHwuJU5sU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>