
Un diccionario es un conjunto ordenado de pares de datos : `clave:valor`

Su definición se hace con { }

~~~Python
peliculas = {
    "Matrix": 1999,
    "Titanic": 1997,
    "Interestelar": 2014,
    "El Padrino": 1972,
    "Parásitos": 2019
}
~~~

**Las claves deben ser únicas e inmutables**

- Las claves pueden ser cualquier tipo inmutable
- Las cadenas y números siempre pueden ser claves
- Las tuplas se pueden usar sólo si no tienen objetos mutables

**Accediendo a los elementos de un diccionario**

Al igual que en las listas y las tuplas, se accede usando [ ] pero en vez de un índice que representa la posición, usamos la clave.
Es un error extraer un valor usando una clave no existente

Dos posibles formas para acceder:
~~~ Python
print(movies['Matrix'])
out : 1999

print(movies.get('Matrix'))
out : 1999
~~~

Cual es la diferencia entre estas dos? La primera en caso de que no exista nos va a retornar un **KeyError**

**Agregando elementos al diccionario**

Si se usa una clave que ya está en uso para guardar un valor, el valor que estaba asociado con esa clave se pierde, si no está la clave, se agrega
Ejemplo:
~~~ Python
months = {'enero': 31, 'febrero': 28, 'marzo': 31}

print(months)

out : {'enero': 31, 'febrero': 28, 'marzo': 31}

months['febrero'] = 29
months['abril'] = 30

print(months)

out : {'enero': 31, 'febrero': 29, 'marzo': 31, 'abril': 30}
~~~

**Recorriendo un diccionario**

~~~ Python
music = {'rock': ['Riff','La Renga', 'La Torre'],
		 'blues': ['La Mississippi', 'Memphis']
		}
		
for elem in music:
	print(elem)

out: rock
	 blues 
~~~

Si queremos imprimir los valores:

~~~ Python
	for elem in music:
		print(music[elem])
out: ['Riff', 'La Renga', 'La Torre']
	 ['La Mississippi', 'Memphis']
~~~

**Algunos métodos útiles**

~~~ Python
music_keys = music.keys()
music_values = music.values(
music_items = music.items()

for elem in music_keys:
	print(elem)
out: rock
	 blues

for elem in music_values:
	print(elem)
	
out: ['Riff', 'La Renga', 'La Torre']
	 ['La Mississippi', 'Memphis']

for elem in music_items:
	print(elem)

out: rock : ['Riff', 'La Renga', 'La Torre']
	 blues : ['La Mississippi', 'Memphis']
)
~~~

Operador **IN** en diccionarios

Verifica claves o los valores?

~~~Python
music = {'rock': ['Riff','La Renga', 'La Torre'],
		 'blues': ['La Mississippi', 'Memphis']
		}

'rock' in music
out : True

'riff' in music
out : False
~~~

Por lo tanto podemos determinar que trabaja sobre las claves.

Para mas operaciones con diccionarios visitar la [documentación oficial](https://docs.python.org/3/tutorial/datastructures.html#dictionaries)

**Otra forma de crear diccionarios**

- Podemos usar **dict()**
- Se denomina "**Constructor**" y crea un diccionario directamente desde una secuencia de pares clave - valor.
