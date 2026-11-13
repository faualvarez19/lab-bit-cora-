# CLASE 3

## 1. Tipos de datos
→ `int` = número entero  
→ `float` = número decimal  
→ `str` = texto  
→ `bool` = verdadero/falso (`True`, `False`)  
→ `list` = lista de elementos  
→ `dict` = pares clave-valor

Para saber el tipo: `type(variable)`

## 2. Listas, vectores y arrays

### Python — Listas
`x = [10, 20, 30, 40]`
Pueden guardar distintos tipos de objetos.

### R — Vectores
`x <- c(10, 20, 30, 40)`
Los elementos de un vector tienen el mismo tipo.

### NumPy — Arrays
Son estructuras pensadas principalmente para operaciones numéricas.
`np.array([10, 20, 30, 40])`
→ Permiten realizar operaciones matemáticas de forma más eficiente.

## 3. Diccionarios

Un diccionario almacena información:
**clave → valor**

Ejemplo:
`persona = {"nombre": "Juan", "edad": 25, "peso": 75}`

Para acceder:
`persona["edad"]` → `25`

También se pueden usar para construir datasets:
`datos = {"nombre": ["Juan","Ana"], "edad": [25,30]}`

Luego:
`df = pd.DataFrame(datos)`

→ transforma el diccionario en una tabla/DataFrame.

# 4. Cómo leer errores en Python

Cuando aparece un error → mirar principalmente **la última línea del mensaje**.
Ahí aparece el **tipo de error** y normalmente una explicación.

### `NameError`
Python no encuentra una variable u objeto.

### `SyntaxError`
El código está escrito con una sintaxis que Python no entiende.

### `TypeError`
Estamos intentando hacer una operación entre tipos incompatibles.

### `ValueError`
El tipo de operación es válido pero el **valor no puede convertirse/utilizarse de esa manera**.

### `FileNotFoundError`
Python no encuentra el archivo.

# 5. Variables categóricas

### Nominal
Las categorías no tienen orden.

### Ordinal
Las categorías tienen un orden lógico.

Ejemplo:
`Bajo < Medio < Alto`

# 6. Calidad y validación de datos
Antes de analizar un dataset → comprobar que los valores tengan sentido.
También revisar:
→ valores imposibles  
→ IDs repetidos  
→ datos faltantes  
→ tipos de variables incorrectos

# 7. Diccionario de variables
Documento que explica qué significa cada columna del dataset.

Puede contener:
**Variable → descripción → tipo → unidad → valores/rango permitido → missing**
→ Permite interpretar correctamente el dataset y establecer controles de calidad.

# 8. Valores faltantes
Representan datos que no están disponibles.
Pueden aparecer como:
`NaN`  
`NA`  
`NULL`  
`""`  
`-999`

Problema → a veces un valor como `-999` parece un número real aunque en realidad signifique “dato faltante”. Por eso hay que conocer cómo están codificados los missing.

# 9. CSV vs Parquet

### CSV
Archivo de texto separado por delimitadores.
Ventajas:
→ simple  
→ fácil de abrir  
→ compatible con casi cualquier programa

Problema:
→ puede perder información sobre los tipos de datos.
Por ejemplo, una variable categórica puede volver a cargarse como texto.

### Parquet
Formato diseñado para almacenar datos de manera más eficiente.
→ mantiene mejor los tipos de datos  
→ ocupa menos espacio  
→ suele ser más eficiente con datasets grandes



# CLASE 4 

# 1. Directorio de trabajo
Es la carpeta que el programa toma como punto de referencia para buscar archivos.

En R:
`getwd()`
→ muestra el directorio de trabajo actual.

# 2. Rutas absolutas y relativas

### Ruta absoluta
Indica toda la ubicación del archivo.

### Ruta relativa
Parte desde la carpeta del proyecto.

# 3. Rutas en R

Se puede utilizar `here`.
Ejemplo:
`here("datos", "ventas.csv")`

→ construye la ruta desde la raíz del proyecto.

# 4. Rutas en Python

Se puede utilizar `pathlib`.
`from pathlib import Path`

Crear una ruta:
`ruta = Path("datos") / "ventas.csv"`

También se puede comprobar si existe:
`ruta.exists()`

→ devuelve `True` o `False`.

# 5. Cargar un CSV

Con pandas:
`import pandas as pd`
`df = pd.read_csv(ruta)`

El resultado queda guardado como un **DataFrame**.

# 6. Data profiling
Es una primera inspección del dataset para entender qué datos tenemos y en qué estado están.
Antes de hacer modelos/análisis → revisar estructura y calidad.

### Dimensiones

`df.shape`
Devuelve: `(filas, columnas)`

Ejemplo:
`(1000, 15)`
1000 observaciones y 15 variables.

### Información de las columnas
`df.info()`
Muestra:
→ nombres de columnas  
→ cantidad de valores no nulos  
→ tipo de cada variable  
→ memoria utilizada

### Primeras filas

`df.head()`
→ permite ver rápidamente cómo está armado el dataset.

# 7. Unidad de observación

Pregunta fundamental:
Qué representa UNA fila del dataset

# 8. Identificador / ID
Variable que debería identificar de forma única cada observación.

Ejemplo:
`id_cliente`
Para ver cuántos valores distintos hay:
`df["id_cliente"].nunique()`

Si:
cantidad de IDs únicos = cantidad de filas
→ probablemente el ID identifica de forma única cada observación.

Si hay menos IDs únicos que filas:
→ existen IDs repetidos.

# 9. Valores faltantes

Para detectarlos:
`df.isnull().sum()`
Devuelve cuántos faltantes tiene cada columna.

# 10. Duplicados

Para detectar filas duplicadas:
`df.duplicated().sum()`

Si devuelve:
`0` → no hay filas duplicadas.

Si devuelve:
`15` → existen 15 filas consideradas duplicadas.

# Esquema general para revisar un dataset

**Cargar archivo**  
↓  
**¿Qué representa cada fila?** → unidad de observación  
↓  
**¿Cuántas filas y columnas hay?** → `shape`  
↓  
**¿Qué variables hay y de qué tipo son?** → `info()`  
↓  
**¿Cuál es el ID?** → `nunique()`  
↓  
**¿Hay valores faltantes?** → `isnull().sum()`  
↓  
**¿Hay duplicados?** → `duplicated().sum()`  
↓  
**Recién después → análisis/modelado**
