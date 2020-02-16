# Predicción

La estimación permite predecir un valor `Y` en aquellas situaciones donde tenemos información disponible sobre `X`, pero no es tan sencillo obtener `Y`.

Supongamos que `X1, ...Xp` son características de una muestra de sangre de un paciente que se pueden medir fácilmente en un laboratorio. `Y` es la variable que codifica el riesgo del paciente de tener una reacción adversa a un medicamento. Lo natural es buscar cómo precedir `Y` utilizando `X`, ya que podemos **no dar el medicamento** en cuestión a los pacientes que tienen un alto riesgo de tener una reacción adversa, es decir, pacientes para los que **la estimación de `Y` es alta**.

---

* `f'`: representa la estimación de `f`
* `Y'`: representa la predicción **resultante** de `Y`

```
Y' = f'(X)
```

Normalmente `f'`, actúa como una **caja negra** (es decir, no sabemos lo que _hace dentro_, sino que solo sabemos el input y el output) Decimos que hay un error porque, realmente, `f'` no va actuar exactamente como `f`. Encontraremos dos tipos de errores:

* Error reducible: Podemos conseguir que `Y'` se parezca más a `Y` modificando `f'`, obteniendo así un mejor resultado tras cada modificación.
* Error irreducible: Por mucho que modifiquemos, optimicemos y mejoremos `f'`, siempre habrá, por definición, algo de error, ya que por definición, decimos que es **imposible** predecir `Y`.

> No matter how well we estimate `f`, we cannot reduce the error introduced by `e`

Sobre el error irreducible, sabemos que:

* Tiende a `0`, es decir, siempre es mayor que `0`
* `e` puede contener variables que no pueden ser medidas, pero que pueden ser útiles para predecir `Y`. Pero como no podemos medirlas, `f` no puede usarlas en la predicción.
* `e` puede contener variaciones que no tampoco pueden ser medidas, como por ejemplo, el riesgo de que un medicamento provoque una reacción en un paciente, pudiendo variar esta reacción de un día a otro en relación al estado anímico de éste.

```
expected_value = E(Y - Y')^2 = E(f(X) + e - f'(x))^2 = E(f(X) - f'(x))^2 + Var(e)
```

dónde:

```
error_reducible = E(f(X) - f'(x))^2
error_irreducible =  Var(e) = varianza asociada con e
```

**Ejemplo:**

Consideremos que una compañía esta interesada en conducir una campaña de marketing. El objetivo es identificar a personas que vayan a responder de manera positiva a un correo, basándonos en observaciones de variables demográficas medidas en cada una de esas personas. En este caso, las **variables demográficas** se pueden utilizar como **indicadores**, y la respuesta a la campaña de márketing (positiva o negativa) se utiliza como dato de **salida**. La compañía no está interesada en tener un conocimiento profundo de la relación entre los indicadores de cada persona y la respuesta, sino que simplemente quiere un modelo preciso para predecir la respuesta utilizando los indicadores.

# Inferencia

Nos interesa saber de qué manera le afecta a `Y` los distintos valores que puede tomar `X`. En esta situación, aunque queremos estimar `f`, el verdadero objetivo no es hacer predicciones de `Y`. En lugar de eso, queremos entender la **relación** entre `X` e `Y` o, para ser más específicos, entender cómo cambia `Y` en función de `X1, ....XP`. En este caso, **no podemos tratar** a `f'` como una **caja negra**, ya que **necesitamos saber qué hace**.

* **¿Qué indicadores (_predictors_) están relacionados con la respuesta?**

Es muy común el caso en el que sólo una pequeña porción de los indicadores disponbiles están relacionados con `Y` considerablemente.
Identificar qué indicadores son los **importantes** entre un gran número de variables posibles puede ser increíblemente **útil** dependiendo de la aplicación.

* **¿Cuál es la relación entre la respuesta y cada indicador?**

Algunos indicadores pueden tener una relación positiva con `Y`, en el sentido de que incrementar el indicador está asociado con incrementar los valores de `Y`.

Otros indicadores pueden tener una relación contraria.

Dependiendo de la complejidad de `f`, la relación entre la respuesta y un indicador puede también depender de los valores de otros indicadores.

* **¿Puede la relación entre `Y` y cada indicador abreviarse correctamente utilizando una ecuación lineal, o es más complicado?**

La mayoría de métodos para estimar `f` toman una forma lineal. En algunas situaciones, este supuesto o hipótesis es razonable o incluso deseable, pero es muy posible que la relación sea mas complicada, en cuyo caso, el modelo lineal puede no darnos una representación precisa de esta relación entre input y output.

**Ejemplo:**

Queremos modelar la marca de un producto que un consumidor puede comprar basándonos en variables como el **precio**, la **ubicación de la tienda**, los **niveles de descuento** o el **precio de la competencia**. En esta situación estaríamos más interesados en cómo cada una de las variables individuales afectan a la probabilidad de que se produzca una compra. Por ejemplo, ¿qué efecto tiene el cambio del precio de un producto con respecto a las ventas?

---

En algunos casos, es posible que un modelo se utilice tanto para predicción como para inferencia de datos. Dependiendo de si el objetivo final es predicción, inferencia o una combinación de ambos, se utilizarán diferentes métodos para estimar `f`. Por ejemplo, los modelos lineales son relativamente simples para calcular inferencia, pero pueden no ser tan precisos para hacer predicciones como otras aproximaciones.
