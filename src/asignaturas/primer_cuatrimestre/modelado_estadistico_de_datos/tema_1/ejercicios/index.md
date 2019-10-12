# Tema 1 - Ejercicios R

## Respuesta Dicotómica

### z diferencia de dos proporciones

```r
# 1. Remove all objects from the current workspace
rm(list=ls())

# 2. Read the data from the d_d_1.txt file
data = read.table("d_d_1.txt", header=T)
attach(data)

# Note: exp = x variable, rta = y variable

data_table = table(-rta, exp);

# 3. Assign the indices:
values_variable_x1 = which(exp==1);
values_variable_x2 = which(exp==2);

values_variable_y1_x1=which(rta==1 & exp==1);
values_variable_y1_x2=which(rta==1 & exp==2);

# 4. Assign the samples length
answer1_num_values = length(rta[values_variable_y1_x1]);
answer2_num_values = length(rta[values_variable_y1_x2]);
sample1_num_values = length(rta[values_variable_x1]);
sample2_num_values = length(rta[values_variable_x2]);

# 5. Assign the alpha value
alpha=0.05

# 6. Calc proportions
proportion_1 = answer1_num_values / sample1_num_values;
proportion_2 = answer2_num_values / sample2_num_values;

proportion_difference = proportion_1 - proportion_2;

# 7. Calc probabilty success
p = (answer1_num_values + answer2_num_values) / (sample1_num_values + sample2_num_values); # success
q = 1 - probability_success; # fail

# 8. Calc deviation

variance1 = p * q / sample1_num_values;
variance2 = p * q / sample2_num_values;

deviation = sqrt(variance1 + variance2)

# 9. Calc z

z0 = pnorm(1 - alpha)
z = proportion_difference / deviation
p_value = 2 * (1 - pnorm(abs(z)))
```

### Exacta de Fisher

```r
```

## Respuesta Continua

### t de Student

```r
```

### ANOVA de un factor

```r
```

## Respuesta Nominal

### χ2 de homogeneidad

```r
```

## Respuesta Ordinal

### U d eMann-Whitney
### W de Wilcoxon
### H de Kruskal-Wallis