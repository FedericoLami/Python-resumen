# Resumen de funciones lambda, map, filter, reduce y sorted en Python

## Funciones lambda

Las funciones **lambda** en Python son funciones anónimas (sin nombre) que se definen en una sola línea. Son útiles para operaciones cortas y específicas, especialmente cuando se usan como argumentos en otras funciones.

### Sintaxis 
~~~python 
lambda argumentos: expresión
~~~

- No requiere **def** ni **return**. La expresión se evalúa y se devuelve automáticamente.
    
- Puede tener cualquier número de argumentos, pero solo una expresión.
    

### Ejemplo 
~~~python
# Función lambda para sumar dos números suma = lambda x, y: x + y print(suma(3, 4)) # Salida: 7
~~~

### Características

- Son funciones de una sola expresión, no bloques de código.
    
- Ideales para uso temporal o en combinación con funciones como **map**, **filter**, **reduce** o **sorted**.
    
- Menos legibles para operaciones complejas, por lo que deben usarse con moderación.
    

## Función map

La función **map** aplica una función a cada elemento de un iterable y devuelve un iterador con los resultados.

### Sintaxis 
~~~python
map(función, iterable, ...) 
~~~

- **función**: La función a aplicar (puede ser una función definida o una lambda).
    
- **iterable**: Uno o más iterables cuyos elementos se procesan.
    
- Devuelve un objeto **map** (iterador), que puede convertirse en lista con **list()**.
    

### Ejemplo 
~~~python 
numeros = [1, 2, 3, 4] cuadrados = map(lambda x: x**2, numeros) print(list(cuadrados)) # Salida: [1, 4, 9, 16] 
~~~

### Notas

- Es eficiente para aplicar transformaciones a grandes conjuntos de datos.
    
- Puede manejar múltiples iterables si la función acepta múltiples argumentos.
    

## Función filter

La función **filter** selecciona elementos de un iterable que cumplen con una condición definida por una función.

### Sintaxis 
~~~python 
filter(función, iterable) 
~~~

- **función**: Debe devolver **True** o **False**. Los elementos para los que devuelve **True** se incluyen.
    
- **iterable**: El iterable a filtrar.
    
- Devuelve un objeto **filter** (iterador), que puede convertirse en lista con **list()**.
    

### Ejemplo 
~~~python 
numeros = [1, 2, 3, 4, 5, 6] pares = filter(lambda x: x % 2 == 0, numeros) print(list(pares)) # Salida: [2, 4, 6]
~~~

### Notas

- Útil para extraer subconjuntos de datos basados en una condición.
    
- La función puede ser **None**, en cuyo caso filtra elementos que son **True** en el contexto booleano.
    

## Función reduce

La función **reduce** aplica una función de forma acumulativa a los elementos de un iterable, reduciéndolos a un solo valor. Está en el módulo **functools**.

### Sintaxis 
~~~python 
from functools import reduce reduce(función, iterable[, inicial]) 
~~~

- **función**: Debe aceptar dos argumentos y devolver un solo valor.
    
- **iterable**: El iterable a procesar.
    
- **inicial**: Valor inicial opcional para la reducción.
    
- Devuelve un solo valor.
    

### Ejemplo 
~~~python
from functools import reduce numeros = [1, 2, 3, 4] producto = reduce(lambda x, y: x * y, numeros) print(producto) # Salida: 24
~~~

### Notas

- Útil para operaciones como sumas, productos o concatenaciones acumulativas.
    
- Si se proporciona un valor **inicial**, se usa como primer argumento en la primera llamada.
    

## Función sorted

La función **sorted** ordena los elementos de un iterable y devuelve una nueva lista ordenada.

### Sintaxis 
~~~python
sorted(iterable, key=None, reverse=False)
~~~

- **iterable**: El iterable a ordenar.
    
- **key**: Una función opcional que define el criterio de ordenamiento (puede ser lambda).
    
- **reverse**: Si es **True**, ordena en orden descendente.
    
- Devuelve una nueva lista ordenada.
    

### Ejemplo 
~~~python
palabras = ['manzana', 'banana', 'arándano'] ordenadas = sorted(palabras, key=lambda x: len(x)) print(ordenadas) # Salida: ['banana', 'manzana', 'arándano']
~~~

### Notas

- A diferencia del método **.sort()** (que modifica listas in situ), **sorted** crea una nueva lista.
    
- La función **key** permite personalizar el criterio de ordenamiento (por ejemplo, longitud, valor).
    

## Combinación de funciones lambda con map, filter, reduce y sorted

Las funciones **lambda** son comúnmente usadas con **map**, **filter**, **reduce** y **sorted** para definir operaciones inline sin necesidad de funciones nombradas.

### Ejemplo combinado 
~~~python 
from functools import reduce numeros = [5, 2, 8, 1, 9]

# Elevar al cuadrado con map cuadrados = list(map(lambda x: x**2, numeros)) # [25, 4, 64, 1, 81]

# Filtrar mayores a 10 con filter mayores = list(filter(lambda x: x > 10, cuadrados)) # [25, 64, 81]

# Sumar con reduce suma = reduce(lambda x, y: x + y, mayores) # 170

# Ordenar original con sorted ordenados = sorted(numeros, key=lambda x: x, reverse=True) # [9, 8, 5, 2, 1]

print(suma) # Salida: 170 print(ordenados) # Salida: [9, 8, 5, 2, 1]
~~~

## Buenas prácticas

- Usa funciones **lambda** para operaciones simples y cortas.
    
- Evita funciones **lambda** complejas; en su lugar, define funciones nombradas para mayor legibilidad.
    
- Convierte los resultados de **map** y **filter** a listas solo cuando sea necesario, ya que los iteradores son más eficientes.
    
- Usa **reduce** solo cuando sea la herramienta más clara; a veces un bucle es más legible.
    
- Aprovecha **key** en **sorted** para criterios de ordenamiento personalizados.
    

## Referencias

- [Documentación oficial de Python sobre funciones lambda](https://docs.python.org/3/reference/expressions.html#lambda)
    
- [Documentación oficial de Python sobre map, filter, reduce y sorted](https://docs.python.org/3/library/functions.html)