Las funciones en Python sirven para organizar el código, haciendo que sea más legible, mantenible y reutilizable. Permiten agrupar un conjunto de instrucciones que realizan una tarea específica, la cual puede ser ejecutada varias veces en diferentes partes del programa.

Declaración de funciones

~~~ Python
def my_function (param1,param2):
	sentences
	return <expression>
~~~

La sentencia return y los parámetros de la función son opcionales

Ejemplo de función

~~~Python
movies = [50, 48, 85, 93, 100]  
def average_calculation(movies_duration):  
	total_movies = len(movies_duration)  
	average_movies = 0 	if total_movies == 0 	else sum(movies_duration) / total_movies 
	return average_movies
~~~

Cuando pasamos un parámetro a una función, pasamos una copia de la referencia al objeto pasado.


Python nos permite definir parámetros con **valores por defecto**.

**Si hay mas de un argumento, los que tienen valores por defecto siempre van al final de la lista de parámetros.**
~~~ Python
def demo_function(param1,param2 = 'Hola')
	print(f'{param1 = } - {param2 =})

demo_function(10)
~~~

Los parámetros formales y reales se asocian de acuerdo al orden posicional, pero es posible invocar a la función con los parámetros en otro orden pero nombrando al parámetro

~~~ Python
def my_music(music,name,music_type = 'nacional'):

my_music(music, music_type = 'internacional', name = 'lista')
~~~


**Definición de funciones con un número variable de parámetros**
**Permite pasar una **cantidad indefinida de argumentos** a una función como **tupla**.**

~~~ Python
def my_args(*args):
	for value in args:
		print(f'{value} es de tipo {type(value)}')
~~~


Otra forma de definir una función con un número variable de parámetros es con **KWARGS**
**Permite pasar una cantidad indefinida de argumentos **con nombre**, y los recibe como **diccionario**.**

~~~ Python
def my_args1(**kwargs):
	for key, value in kwargs.items():
		print(f'{key} es {value}')
~~~


**Variables locales y globales**

~~~ Python
x = 12
a = 13
def my_function(a):
	#global x
	x = 9
	a = 10

my_function(a)
print(a)
print(X)
~~~

- Variables locales enmascaran las globales.
- Acceso a las globales mediante **global**

Aunque no es recomendable utilizar variables globales debido a su falta de practicidad y legibilidad


**Atributos de las funciones**

Las funciones en Python también son objetos.

Algunos de sus atributos son:
- `my_function.__doc__`: es el docstring.  
- `my_function.__name__`: es una cadena con el nombre la función.  
- `my_function.__defaults__`: es una tupla con los valores por defecto de los parámetros  
  opcionales.

Para ver mas sobre atributos visitar [documentación oficial](https://peps.python.org/pep-0232/)