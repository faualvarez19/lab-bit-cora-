## Clase 14 

Tipos de archivos
.csv - Texto plano	.xlsx - Binarios
.json - Texto plano	.pdf - Binarios
.txt - Texto plano	.jpg - Binarios
.py - Texto plano	.png - Binarios
.R - Texto plano	.docx - Binarios

- Los archivos de texto plano pueden leerse como caracteres
- Los binarios necesitan programas o bibliotecas que interpreten su formato.

# CSV y JSON

CSV almacena datos tabulares separados por delimitadores.
nombre,edad
Ana,20
Juan,22

JSON permite representar datos mediante claves, valores, listas y objetos.
{
  "nombre": "Ana",
  "edad": 20,
  "materias": ["Estadística", "Python"]}

# Union de tablas
Para unir tablas necesitamos identificar la clave que relaciona los registros.

Ejemplo:

Tabla de ventas:
id - 1, 2
cliente_id - 10, 20
monto - 500, 800


Tabla de clientes:
cliente_id ////	nombre
10	            Ana
30	            Pedro

Una union izquierda conserva las dos ventas, pero el nombre correspondiente al cliente 20 queda faltante.
resultado = pd.merge(    
  ventas,    
  clientes,    
  on="cliente_id",    
  how="left")

Una union interna conserva solamente la venta que tiene coincidencia en ambas tablas.
resultado = pd.merge(    
  ventas,    
  clientes,    
  on="cliente_id",    
  how="inner")


## Clase 15

# Analisis de datos experimentales
Cuando tenemos datos de un experimento, primero: describir las variables dsp: elegir las pruebas estadisticas que correspondan.

# Tablas descriptivas: tablas descriptivas permiten resumir las caracteristicas de las observaciones y comparar grupos.
df.describe()
df.groupby("grupo")["resultado"].describe()

# Prueba exacta de Fisher
fisher.test(tabla)

# ANOVA - permite comparar las medias de distintos grupos.
modelo <- aov(resultado ~ grupo, data = df)
summary(modelo)

# Tamaño del efecto
ademas de evaluar si un resultado es estadisticamente significativo, hay que analizar que tan grande es la diferencia.
- un resultado puede tener un valor p pequeño y, sin embargo, representar una diferencia muy reducida

# Intervalos de confianza
proporciona un rango de valores compatibles con los datos y el procedimiento estadístico utilizado.

# Bootstrap
es una técnica de remuestreo que consiste en tomar muchas muestras con reemplazo a partir de los datos originales.
- se utiliza para estudiar la variabilidad de un estadistico y construir intervalos de confianza.
- la idea es repetir el procedimiento muchas veces y calcular el estadistico en cada muestra.

# Aumentacion de datos con ruido
ruido = np.random.normal(0, 0.1, len(df))df["variable_nueva"] = df["variable"] + ruido
