# Diferencia de Riesgos válida en estudios prospectivos

El **riesgo** es un parámetro poblacional.

El **riesgo absoluto** mide la **incidencia de un evento** en la **población total**: es la **probabilidad** que tiene un **sujeto** de sufrir un **evento** a lo largo de **cierto tiempo**.

De lo anterior se desprende que **la incidencia de un evento** en una **población** se denomina **riesgo absoluto**.

Se pueden utilizar los siguientes métodos:

* Test z de diferencia de proporciones
* Test de Fisher
* Test χ^2

Para estimar el parámetro `dr` (_diferencia de riesgos_) se considera el estadístico Θ dado por la variable aleatoria (v.a.) `Π11 − Π10`, siendo `Π11` _(Y = 1, X = 1)_ e `Π10` _(Y = 1, X = 0)_ las proporciones muestrales
entendidas como v.a. ya que variar ́an de muestra a muestra Viene dado por:

```
riesgo = θ = dr = π11 − π10 = P(Y = 1|X = 1) − P(Y = 1|X = 0)
```

|             |  X = 1   |  X = 0   |  Total  |
|-------------|----------|----------|---------|
| Y = 1       | a        | b        |  a + b  |
| Y = 0       | c        | d        |  c + d  |
| Total       | a + c    | b + d    |  N      |

** Metáfora de los peces mutantes**


|    Peces    |  Mutante |  Normal  |  Total  |
|-------------|----------|----------|---------|
| Expuestos   | a        | b        |  a + b  |
| No expuestos| c        | d        |  c + d  |
| Total       | a + c    | b + d    |  N      |

### Intervalo de confianza

_Nota: sigue una distribución normal_

**Varianza Teórica:**

```
Varianza Teórica =
  (π11(1 - π11) / (a + c))
  +
  (π10(1 - π10) / (b + d))
```

**Error Estándar:**

```
Error Estándar =  
  sqrt(Varianza Teórica) =

  sqrt(
    (π11(1 - π11) / (a + c))
    +
    (π10(1 - π10) / (b + d))
  )
```

Dado una significancia de α, calculamos el intervalo de confianza al `(1 - α)%`:

```
IC dr = (a / a + c) - (b / b + d) ∓ z_1-α/2 * sqrt((ac / (a+c)^3) + ((bd / (b+d)^3)))
```

### Contraste de hipótesis

```
H0 : dr = 0
H1 : dr != 0
```