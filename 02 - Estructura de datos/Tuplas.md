
Son colecciones heterogéneas de datos ordenados

Distintas declaraciones de una tupla:

~~~ Python
tupla1 = (1,2) 
tupla2 = 1,2  #No importa el uso de parentesis para declarar una tupla
tupla3 = (1, ) #Modo de declarar una tupla de un unico valor
tupla4 = ()  #Tupla vacía
~~~

**Diferencia con las listas**

Veamos las siguientes comparaciones

~~~ Python
my_tuple = ("tuple", 2)
my_list = ["list",2]

elem = my_tuple[0]
print(elem)
out : 'tuple'
print(len(my_tuple))
out : 2

elem = my_list[0]
print(elem)
out : 'list'
print(len(my_list))
out : 2 
~~~

- Se acceden a los elementos de igual manera: usando `[]`(Empezando desde cero).
- La función `len()` retorna la cantidad de elementos en ambos casos.

**DIFERENCIA:** las tuplas son **INMUTABLES**
Por lo tanto su tamaño y valores de las mismas no se pueden cambiar.


**Obteniendo sub tuplas**

~~~ Python
my_tuple = (1, 2, 3, "hola")
print(my_tuple[1:4])
out : (2, 3, 'hola')

new_tuple = ("nueva",) + my_tuple[:2]
print(new_tuple)
out : ('nueva', 1, 2)
~~~

