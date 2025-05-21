
**Conjuntos en Python**

Un conjunto es una colección de datos heterogénea, desordenada, NO indexada y sin elementos duplicados

~~~ Python
bandas = {"AC/DC", "Metallica", "Greta Van Fleet", "Soda Stereo"}
type(bandas)
out: "set"
~~~

otro ejemplo útil en el caso de tener un único elemento para hacer conjunto:

~~~Python
letras = set("alabanza")
print(letras)
out: 'a','b','l','n','z'
~~~


 **Recorrido de un conjunto**

Se recorre al igual que cualquier otra estructura de datos, con un elemento iterativo
ejemplo:
~~~ Python
bandas = {"AC/DC", "Metallica", "Greta Van Fleet", "Soda Stereo"}
for elem in bandas:
	print(elem)
~~~

**Operaciones con conjuntos**

- **in**: retorna si un elemento pertenece o no a un conjunto
- **|**: unión entre dos conjuntos
- **&**: intersección entre dos conjuntos
- **-**: diferencia de conjuntos

**Métodos que se pueden utilizar con conjuntos**

- **Copy()**
~~~ Python
bandas = {"AC/DC", "Metallica", "Greta Van Fleet", "Soda Stereo"}

mis_bandas = bandas.copy()
print(id(mis_bandas))
print(id(bandas))

mis_bandas out: '140099003817920'
bandas out: '140099003819936'
~~~

- **Add()**
~~~ Python
bandas.add('Foo Fighters')
print(bandas)
out : {"AC/DC", "Metallica", "Greta Van Fleet", "Foo Fighters", "Soda Stereo"}
~~~

Para mas métodos en Python: (https://www.w3schools.com/python/python_sets_methods.asp)