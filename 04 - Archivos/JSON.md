
**JavaScript Object Notation**

[JSON](https://www.json.org/json-en.html) es un formato de intercambio de datos muy popular que utilizan el formato:

~~~ JSON
  
{ 
"Tema": "Photograph",
"Intérprete": "Ed Sheeran",
"Año": 2015
} 

o utiliza:

[
{"Tema": "Unintended",
"Intérprete": "Muse",
"Año": 1999},
{"Tema": "Photograph",
"Intérprete": "Ed Sheeran",
"Año": 2015}
]
~~~

[Otro ejemplo más especifico](https://sampleapis.com/api-list/movies)

**Módulo json**

Python tiene un módulo que permite trabajar con este formato. Para usarlo debemos importarlo
~~~Python
import json
~~~

Este módulo nos permite **serializar objetos**, 
serializamos con: 
1. **dumps()**
2. **dump()**

deserializamos con:
1. **loads()**
2. **load()**

cuando hablamos de **serializar** y **deserializar** objetos en el contexto de JSON nos referimos que con **serializar** convertimos un objeto de Python (como un diccionario, lista, etc.) en una cadena de texto en formato JSON. Esto permite guardar el objeto en un archivo o enviarlo por la red.
Y con **deserializar** nos referimos a convertir una cadena JSON (texto) de vuelta a un objeto de Python (como un diccionario o lista). Esto permite leer datos JSON desde un archivo o una respuesta de red.

[Más información](https://docs.python.org/3/library/json.html)


Ejemplo serializando un archivo:

~~~ Python

import json

data = [  
{"nombre": "William Campbell", "es_solista": False, "ciudad": "La Plata", "pais": {"nombre": "Marcos Fava", "es_solista": True, "ciudad": "La Plata", "pais": "Arge  
{"nombre": "Ed Sheeran", "es_solista": True, "ciudad": "Halifax", "pais": "Reino  
{"nombre": "INXS", "es_solista": False, "ciudad": "Sidney", "pais": "Australia","  
{"nombre": "La Ley", "es_solista": False, "ciudad": "Santiago", "pais": "Chile", {"nombre": "Héroes del Silencio", "es_solista": False, "ciudad": "Zaragoza", "pai  
{"nombre": "Panza", "es_solista": False, "ciudad": "Buenos Aires", "pais": "Argen  
{"nombre": "Adele", "es_solista": True, "ciudad": "Tottenham", "pais": "Reino Uni  
]

file_route = Path('ejemplos') / "clase04" / "musica.json"  
music_file = open(file_route, "w")

json.dump(data, music_file)
music_file.close()
~~~

Ejemplo deserializando para trabajar con nuestra lista de diccionarios
~~~ Python
file_route = Path('ejemplos') / "clase04" / "musica.json"
file = open(file_route, 'r')
data = json.load(file)
file.close()
~~~