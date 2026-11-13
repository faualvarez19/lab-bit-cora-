## Clase 7 

# Carga y manejo de datos
library(tidyverse)
library(here)

datos <- read_csv(
  here("clases", "clase7", "archivo.csv")
)

Funciones importantes de dplyr:
select(datos, variable1, variable2)
filter(datos, variable1 > 20)
mutate(datos, nueva = variable1 * 2)
arrange(datos, variable1)
group_by(datos, grupo)
summarise(datos, media = mean(variable1, na.rm = TRUE))


# Estadística descriptiva
- La media es el promedio de las observaciones: suma de los xi / n
- La mediana es el valor central de los datos ordenados
- Los percentiles indican el valor por debajo del cual se encuentra determinado porcentaje de observaciones.

mean(datos$o3, na.rm = TRUE)
median(datos$o3, na.rm = TRUE)
quantile(datos$o3, 0.95, na.rm = TRUE)

# Tablas de frecuencia
- La frecuencia absoluta es la cantidad de observaciones de un intervalo.
- La frecuencia relativa es: fi = ni / n
- la frecuencia porcentual: fi = ni / n * 100
- Un histograma representa la distribucion de una variable numérica agrupada en intervalos.

# Transformación de fechas
Las fechas tienen que convertirse al tipo correcto antes de analizarlas.

library(lubridate)

datos <- datos %>%
  mutate(
    mes = month(fecha),
    hora = hour(fecha)
  )


## Clase 8
Pandas y Matplotlib

Pandas - sirve para trabajar con tablas y 
Matplotlib - para crear graficos.
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

Al trabajar con varias fuentes:
- revisar que tengan variables compatibles 
- datos estén en la misma unidad y escala temporal.

# (ej de chat) Por ejemplo, si tenemos mediciones de contaminación cada minuto y tránsito por hora, debemos agrupar los datos antes de compararlos.
df["fecha"] = pd.to_datetime(df["fecha"])
df["hora"] = df["fecha"].dt.floor("h")
resumen = df.groupby("hora")["o3"].mean()

Graficos 

- de líneas: ver cómo evoluciona una variable (en el tiempo).
plt.plot(df["fecha"], df["o3"])
plt.xlabel("Fecha")
plt.ylabel("Ozono")
plt.title("Evolución del ozono")
plt.show()

- Histograma: permite observar la distribucion de una variable.
plt.hist(df["o3"].dropna(), bins=20)
plt.show()

- de dispersión: relacion entre dos variables numericas.
plt.scatter(df["transito"], df["pm25"])
plt.xlabel("Tránsito")
plt.ylabel("PM2.5")
plt.show()

- barras: para comparar categorías
