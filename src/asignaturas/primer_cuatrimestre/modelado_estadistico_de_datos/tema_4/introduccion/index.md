> [An Introduction to Statistical Learning](http://faculty.marshall.usc.edu/gareth-james/ISL/), _Gareth James • Daniela Witten • Trevor Hastie Robert Tibshirani_

El aprendizaje estadístico supervisado consiste, en general, en construir un modelo estadístico para predecir o estimar unos **datos de salida** (output) basados en uno o más **datos de entrada** (input).

Por ejemplo, en campos como los negocios, la medicina o la astrofísica. El aprendizaje estadístico no supervisado, sí que existen datos de entrada pero no se tienen en cuenta los datos de salida. Sin embargo, se pueden establecer relaciones de esos datos.

Imaginemos que trabajamos en un departamento de ventas y queremos conocer la relación entre publicidad y ventas, para saber ajustar presupuestos publicitarios (el dinero destinado a publicidad) e incrementar las ventas. Nuestro objetivo sería desarrollar un modelo preciso que pueda precedir las ventas dados tres tipos de medios: televisión, radio y periódico.

Los **datos de entrada** son conocidos por: variables de entrada (_input variables_), variables independientes, (_independent variables_) características (_features_) o simplemente variables (_variables_)

Los **datos de salida** son conocidos por: variable de salida (_output variable_), respuesta (_response_), o variable dependiente (_dependent variable_)

* input
    * X1: presupuesto para televisión
    * X2: presupuesto para radio
    * X3: presupuesto para periódico
* output
    * Y: ventas

Generalmente hablando, si observamos una respuesta `Y` y un número _p_ de de variables independientes (`X1, X2... Xp`), asumimos que hay una relación entre `Y` y `X = (X1, X2,...,Xp)`:

```
Y = f(X) + e
```

* `e` sería el _error_, que es **independiente de `X`** y cuya media es 0
* `f` representa la información _sistemática_ que `X` nos da sobre `Y`

En esencia, el aprendizaje estadístico se refiere en las aproximaciones para estimar `f`. Por esto, veremos:

* Conceptos teóricos a la hora de estimar `f`
* Herramientas para evaluar las estimaciones obtenidas