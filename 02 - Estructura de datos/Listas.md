
**¿Qué son las listas?**

Una lista es una colección ordenada de elementos. Son estructuras heterogéneas, es decir que pueden contener cualquier tipo  
de datos, inclusive otras listas.

Declaración de una lista

~~~ Python
movies_duration = [108, 106, 135, 90, 122, 140]
~~~

**Accediendo a los elementos de una lista**

Se accede a través de un índice que indica la posición del elemento dentro de la lista encerrado entre corchetes [].
**IMPORTANTE**: al igual que las cadenas los índices comienzan en 0.

~~~ Python
my_list = [ 17, "hola", [1, "dos"], 5.5, True] 
print(my_list[0])  
print(my_list[2][1] )  
print(my_list[-3])
print(my_list[-1])

1° out : '17'
2° out : 'dos'
3° out : [1, 'dos']
4° out : True
~~~

**Recorriendo una lista**

Para recorrer una lista utilizamos una estructura iterativa, por ejemplo:

~~~ Python
for elem in my_list:
	print(elem)
~~~

Asignación de listas

observemos el siguiente ejemplo para entenderlo mejor:

~~~ Python
rock = ['Riff', 'La Renga', 'La Torre']
blues = ['La Mississippi', 'Memphis']
music = rock
rock[0] = 'Rata Blanca'
print(music)

out : ['Rata Blanca', 'La Renga', 'La Torre']
~~~

Recordemos que las variables son **referencias a objetos**, significa que no almacena el objeto en sí, sino que almacena la dirección de memoria donde se encuentra el objeto. 

Observemos este código

~~~ Python
more_music = rock[:]  
print(id(rock))  
print(id(more_music))  
print(id(music))
more_music.append("Hermetica")  
print(rock)
~~~

music = rock: music y rock referencian al mismo objeto (misma zona de memoria).  
` more_music = rock[:]` more_music y rock referencian a dos objetos distintos (dos zonas de memoria distintas con el mismo contenido).

**Operaciones con listas**

Las listas se pueden concatenar (+) y repetir (*)
~~~ Python
rock = ["Riff", "La Renga", "La Torre"]  
blues =["La Mississippi", "Memphis"]  
music = (rock + blues)
more_rock = (rock * 3)

print(music)
out : ["Riff", "La Renga", "La Torre", "La Mississippi", "Memphis"]
print(more_rock)
out : ["Riff", "La Renga", "La Torre", "Riff", "La Renga", "La Torre", "Riff", "La Renga", "La Torre",]
~~~

## **¿Funciones en Python?**

Una **función** es un bloque de código que solo se ejecuta cuando es llamado. Podes pasarle datos (parámetros) y puede devolver un resultado usando `return`.

### Declaración de una función

~~~python
def saludar(nombre):
    print(f"Hola, {nombre}")
~~~

### Llamada a una función

~~~python
saludar("Federico")
~~~

### Funciones con retorno

~~~python
def sumar(a, b):
    return a + b

resultado = sumar(5, 3)
print(resultado)  # out: 8
~~~

### Parámetros por defecto

~~~python
def saludar(nombre="invitado"):
    print(f"Hola, {nombre}")
    
saludar()           # out: Hola, invitado  
saludar("Lucía")    # out: Hola, Lucía
~~~

### Enlace útil

(https://www.w3schools.com/python/python_functions.asp)

## **métodos en Python**

Los **métodos** son funciones que están asociadas a un objeto, es decir, se llaman usando `objeto.metodo()`.

Por ejemplo, las listas tienen métodos propios como `append()`, `remove()`, `sort()`.

### Ejemplos de métodos en listas

~~~python
peliculas = ["Matrix", "Titanic", "Avatar"]

peliculas.append("Interestelar")    # Agrega un elemento al final  
peliculas.remove("Titanic")         # Elimina un elemento  
peliculas.sort()                    # Ordena la lista alfabéticamente

print(peliculas)
~~~

### Enlace útil

(https://www.w3schools.com/python/python_ref_functions.asp)
