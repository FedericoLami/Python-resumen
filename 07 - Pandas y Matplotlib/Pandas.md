Pandas es una biblioteca de código abierto en Python diseñada para el análisis y manipulación de datos. Proporciona estructuras de datos flexibles y herramientas eficientes para trabajar con datos tabulares, como los que se encuentran en hojas de cálculo o bases de datos

**Importancia en el análisis de datos:**

- Manipulación eficiente: Permite limpiar, transformar y analizar grandes volúmenes de datos de manera rápida.

- Flexibilidad: Soporta una amplia variedad de formatos de entrada/salida (CSV, Excel, SQL, JSON, etc.).

- Integración: Se combina bien con otras bibliotecas de Python como NumPy, Matplotlib y Scikit-learn.

- Automatización: Facilita tareas repetitivas como filtrado, agrupación y unión de datos.

- Análisis exploratorio: Ofrece funciones para explorar y resumir datos, lo que es clave en la etapa inicial de cualquier proyecto de datos.


**Principales estructuras de datos en Pandas**

Pandas se basa en dos estructuras de datos principales:

- **Series:** 

- Es una estructura unidimensional, similar a un arreglo o lista, que puede contener cualquier tipo de datos (enteros, flotantes, cadenas, etc.).
- Cada elemento tiene un índice, que puede ser numérico o una etiqueta personalizada.
Ejemplo:
~~~Python
import pandas as pd

serie = pd.Series([10, 20, 30], index=['a', 'b', 'c'])

print(serie)

# Salida:
# a 10
# b 20
# c 30
# dtype: int64
~~~


- **DataFrame:** 
 
- Es una estructura bidimensional, similar a una tabla o una hoja de cálculo, con filas y columnas.
- Cada columna es una Series, y las filas están indexadas.
~~~python
data = {'Nombre': ['Ana', 'Bob', 'Clara'], 'Edad': [25, 30, 35]}
df = pd.DataFrame(data)
print(df)
# Salida:
#    Nombre  Edad
# 0    Ana    25
# 1    Bob    30
# 2  Clara    35
~~~


**Tipo de archivos y formas de abrir**

- pd.read_csv(): para leer archivos CSV (Comma Separated Values).  
- pd.read_excel(): para leer archivos de Excel.  
- pd.read_json(): para leer archivos JSON.  
- pd.read_html(): para leer tablas HTML de una página web.  
- pd.read_sql(): para leer datos de una base de datos SQL.  
- pd.read_hdf(): para leer archivos HDF5 (Hierarchical Data Format versión 5)
- [Muchos más](https://pandas.pydata.org/docs/user_guide/io.html)


**¿Cómo importar y explorar un conjunto de datos usando Pandas?**

1. Importar un conjunto de datos

Pandas permite importar datos desde múltiples fuentes. Un ejemplo común es leer un archivo CSV:
```python
import pandas as pd

df = pd.read_csv('datos.csv')

df_excel = pd.read_excel('datos.xlsx')  
df_json = pd.read_json('datos.json')    
df_sql = pd.read_sql('SELECT * FROM tabla', conexion) 
```

2. Explorar un conjunto de datos:

Pandas ofrece varias funciones para inspeccionar los datos:

- Ver las primeras filas:

```python
df.head()  # Muestra las primeras 5 filas (o especificar n, ej. df.head(10))
```

- Ver las últimas filas:

```python
df.tail()  # Muestra las últimas 5 filas
```

- Información general:

```python
df.info()  # Muestra tipos de datos, valores nulos y uso de memoria
```

- Estadísticas descriptivas:

```python
df.describe()  # Resumen estadístico (media, mediana, etc.) para columnas numéricas
```

- Dimensiones del DataFrame:

```python
df.shape  # Devuelve (filas, columnas)
```
- Nombres de columnas:

```python
df.columns  # Lista las columnas del DataFrame
```
- Valores únicos:    

```python
df['columna'].unique()  # Muestra valores únicos en una columna
```


**Funcionalidades de Pandas para conocer, filtrar y modificar datos**

Pandas ofrece un conjunto robusto de herramientas para trabajar con datos. A continuación, se detallan las principales funcionalidades:

1. **Conocer los datos**

- Resumen estadístico:


```python
df.describe()  # Estadísticas como conteo, media, desviación estándar, etc.
df['columna'].value_counts()  # Frecuencia de valores en una columna
```

- Verificar valores nulos:

```python
df.isnull().sum()  # Cuenta los valores nulos por columna
```

- Correlaciones:

```python
df.corr()  # Matriz de correlación entre columnas numéricas
```


2. **Filtrar datos**

- Filtrado por condiciones:

```python
# Filtrar filas donde la columna 'Edad' es mayor a 30
df_filtrado = df[df['Edad'] > 30]
```

- Filtrado con múltiples condiciones:

```python
df_filtrado = df[(df['Edad'] > 30) & (df['Ciudad'] == 'Madrid')]
```

- Selección de filas y columnas con loc e iloc:

```python
df.loc[0:5, ['Nombre', 'Edad']]  # Selección por etiquetas
df.iloc[0:5, 0:2]  # Selección por índices numéricos
```

- Filtrado con query:

```python
df.query('Edad > 30 and Ciudad == "Madrid"')
```

3. Modificar datos

- Cambiar valores:

```python
df['Edad'] = df['Edad'] + 1  # Incrementar la edad en 1
```

- Reemplazar valores:

```python
df['Ciudad'].replace('Madrid', 'Barcelona', inplace=True)
```

- Manejo de valores nulos:

```python
df.fillna(0)  # Rellenar nulos con 0
df.dropna()   # Eliminar filas con valores nulos
```

- Crear nuevas columnas:

```python
df['Edad_Doble'] = df['Edad'] * 2  # Nueva columna con el doble de la edad
```

- Eliminar columnas o filas:

```python
df.drop('columna', axis=1, inplace=True)  # Eliminar una columna
df.drop(0, axis=0, inplace=True)  # Eliminar una fila
```

4. Agrupación y agregación

- Agrupar datos:

```python
df.groupby('Ciudad').mean()  # Promedio por ciudad
```

- Funciones de agregación:

```python
df.groupby('Ciudad').agg({'Edad': 'mean', 'Salario': 'sum'})
```

5. Unión y combinación de datos

- Concatenar DataFrames:

```python
df_concat = pd.concat([df1, df2], axis=0)  # Unir por filas
```

- Fusión (merge):

```python
df_merged = pd.merge(df1, df2, on='clave_comun', how='inner')  # Unión tipo SQL
```

6. Ordenación

- Ordenar por columnas:

```python
df.sort_values('Edad', ascending=True)  # Ordenar por edad ascendente
```

7. Exportar datos

- Guardar como archivo:

```python
df.to_csv('nuevo_archivo.csv', index=False)  # Exportar a CSV
df.to_excel('nuevo_archivo.xlsx')  # Exportar a Excel
```

Ejemplo practico completo:

~~~Python
import pandas as pd

# Importar datos
df = pd.read_csv('datos.csv')

# Explorar
print(df.head())
print(df.info())
print(df.describe())

# Filtrar
df_filtrado = df[df['Edad'] > 30]

# Modificar
df['Edad'] = df['Edad'] + 1
df['Ciudad'].replace('Madrid', 'Barcelona', inplace=True)

# Agrupar
print(df.groupby('Ciudad')['Edad'].mean())

# Exportar
df.to_csv('datos_modificados.csv', index=False)
~~~