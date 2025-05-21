El tipo de datos nos indica que valores y operaciones podemos hacer con una determinada variable.

* Números: int y float
* Booleanos: bool
* Cadenas de caracteres: str

Existe la función type() que nos permite saber con que tipo es un determinado objeto referenciado a una variable.

~~~ Python
	x = "casa"
	type(x)
	out : str
~~~

Hay algunas conversiones de tipo implícitas y otras explicitas

~~~ Python
	mitad = 10/2
	type(mitad)
	out: float
~~~

~~~ Python
	mitad = int(10/2)
	type(mitad)
	out: int
~~~


## Cadenas de caracteres

Secuencia de caracteres encerrados entre comillas simples ' ' o comillas dobles " "

También se pueden definir con """ """

~~~ Python
	menu = """ Menu de opciones:
			   1. - Jugar
			   2. - Configurar el juego
			   3. - Salir
		   """

	mensaje_de_error = "ATENCION: opcion ingresada no es correcta"
~~~

## Operaciones con cadenas de caracteres

* Concatenación: +
* Repetición: *
* Longitud de la cadena: len()

Cada elemento de la cadena se accede mediante un índice entre "[ ]". Iniciando el primer elemento a diferencia de otros lenguajes de programación en 0

## Sub cadenas - slicing

1- El operador " : " permite obtener sub cadenas. Esto se denomina **slicing**.
2- El formato es **cadena[inicio:fin]**.
3- **NO** incluye al elemento cuyo índice es fin.
4- [:] devuelve toda la cadena de caracteres.
5- Si los índices son negativos, se recorre de derecha a izquierda.

Ejemplo:
~~~ Python
cadenaPy = 'Python'
print(cadenaPy[3:-1])
out: 'ho'
~~~

**LAS CADENAS DE CARACTERES SON INMUTABLES**

Recordemos que en Python, todos los tipos de datos son objetos. En un futuro retornaremos con este tema, pero por ahora podemos mencionar que los objetos tienen **Propiedades** y **Métodos**.
Por ejemplo:
~~~ Python
	cadena = "PyTHon"
	print(cadena.upper())
	out: 'PYTHON'
	
	print(cadena.lower())
	out: 'python'
~~~

Otro ejemplo mas interesante:
~~~ Python
cadena = "Hola!!!!!!!"
print(cadena.count("!"))
out: 7
~~~

Para ver más funciones: https://www.w3schools.com/python/python_ref_string.asp


## El módulo string

Python tiene un módulo denominado *string* que contiene mucha funcionalidad para la manipulación de cadenas.
Para acceder a esta funcionalidad debemos importarla, lo cual veremos en detalle mas adelante
Ejemplo del módulo:
~~~ Python
	import string
	letras = string.ascii_letras
	minusculas = string.ascii_lowercase
	digitos = string.digits

	print(minusculas)
	out: 'abcdefghijklmnopqrstuvwxyz'
~~~

Esto es interesante para dar solución a diferentes tareas que se pueden llegar a plantear, por ejemplo para saber si una letra leída desde un archivo o ingresada por el usuario es mayúscula o minúscula.

## Cadenas con formato

Es posible definir cadenas con determinados formatos utilizando el método format.
La forma general es:
	cadena.format(argumentos)
Se vera mejor en los siguientes ejemplos:

~~~ Python
	intentos = 5
	print('Hola {}!! Ganaste y necesitaste {} intentos'.format("Lionel",intentos))
	out: 'Hola Lionel!! Ganaste y necesitaste 5 intentos'
	
~~~


## f-String

A partir de la versión de Python 3.6 hay una forma más fácil de declarar los f-Sting, se ven mucho mejor en la [PEP 498](https://peps.python.org/pep-0498/)

Es una forma mucho mas sencilla de utilizar el format
Ejemplo:
~~~ Python
	intentos = 5
	nombre = "Lionel"
	print(f'Hola {nombre}!! ganaste y necesitaste {intentos} intentos)
	out: 'Hola Lionel!! ganaste y necesistaste 5 intentos'
~~~