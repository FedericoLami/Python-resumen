**CSV (Comma Separated Values)** 
Es un formato muy común para importar/exportar desde/hacia hojas de cálculo y bases de datos.

[Más información](https://docs.python.org/3/library/csv.html) en la [PEP 305](https://peps.python.org/pep-0305/)

**¿Qué es un dataset?**

Un **dataset** es un conjunto de datos organizados, como una tabla, lista o archivo (por ejemplo CSV o JSON), usado para análisis, entrenamiento de modelos o visualización

**Módulo CSV**

El módulo CSV hay que importarlo
**csv.reader**: crea un objeto iterador que nos permite recorrer las líneas del archivo.

~~~ Python
csv_reader = csv.reader(file,delimiter = ',')
~~~
