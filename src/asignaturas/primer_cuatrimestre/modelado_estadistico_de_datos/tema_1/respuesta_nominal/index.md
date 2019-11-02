# Respuesta Nominal

Se está intentando explicar la variable respuesta `Y` nominal a través de la variable explicativa `X` nominal.
Se da, por ejemplo, cuando se quiere estudiar si distintos tipos de efectos adversos están influidos por distintos tipos de dieta.

Para ello se realiza un estudio en n individuos a los que se les asigna, por ejemplo, la dieta 1 (codificada
con 1 en la variable dieta) a n1 individuos, la dieta 2 (codificada con 2), la dieta 3 (codificada con 3) a n3
individuos, con n = n1 + n2 + n3 y se observa qué tipo de efecto adverso presenta (por ejemplo, 1, 2, 3  o 4).

> Nota: Una respuesta dicotómica es una respuesta nominal de dos valores

**Contraste de Hipótesis**

La pregunta de si X influye en Y se traduce en realizar el contraste de hipótesis

* H0 : No diferencia en los grupos
* H1 : Sí diferencia en los grupos

## χ2 de homogeneidad

_χ2 = chi cuadrado_

**Valores**

|       |       |       |       |   |
|-------|-------|-------|-------|---|
|       | X = 1 | X = 2 | X = 3 |   |
| Y = 1 | n11   | n12   | n13   |r1 |
| Y = 2 | n21   | n22   | n23   |r2 |
| Y = 3 | n31   | n32   | n33   |r3 |
| Y = 4 | n41   | n42   | n43   |r4 |
|       | c1    | c2    | c3    |n  |

1. Calcular χ2: 

```
e_ij = r_i * c_j / n
```

```
χ2 = (n_ij - e_ij) ^ 2 / e_ij
```

2. Calcular p_valor (buscando en la tabla):

_(tabla pchisq = tabla chi cuadrado)_

```
p_valor = 1 − pchisq(χ2, grado_de_libertad)
```