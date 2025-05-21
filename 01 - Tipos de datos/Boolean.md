## Valores Booleanos (`bool`) en Python

El tipo de dato `bool` representa **valores lógicos**:

- `True` → verdadero  
- `False` → falso

~~~python
activo = True
print(type(activo))
# out: <class 'bool'>
~~~

---

### ¿Cómo se obtienen valores `bool`?

1. Directamente:

~~~python
estado = False
~~~

2. Mediante comparaciones:

~~~python
print(5 > 3)       # True
print(10 == 5)     # False
print(7 != 7)      # False
~~~

3. Con la función `bool()`:

~~~python
print(bool(0))         # False
print(bool(1))         # True
print(bool(""))        # False
print(bool("Hola"))    # True
print(bool([]))        # False
print(bool([1, 2]))    # True
~~~

---

### Operadores lógicos

Se usan para combinar condiciones:

- `and` → verdadero si **ambas** son verdaderas  
- `or` → verdadero si **al menos una** es verdadera  
- `not` → invierte el valor

~~~python
a = 5
b = 10

print(a > 0 and b < 20)   # True
print(a > 10 or b < 20)   # True
print(not a > 0)          # False
~~~

---

### Uso en estructuras de control

Los `bool` son fundamentales para tomar decisiones con `if`, `while`, etc.

~~~python
edad = 18

if edad >= 18:
    print("Mayor de edad")
else:
    print("Menor de edad")
~~~

---

### Conversión de otros tipos a `bool`

Python convierte automáticamente ciertos valores a `False`:

- `0`
- `0.0`
- `""` (cadena vacía)
- `None`
- `[]`, `{}`, `set()`

Todo lo demás se considera `True`.

~~~python
print(bool(0))        # False
print(bool("Hola"))   # True
print(bool([]))       # False
~~~

---

### Ejemplos prácticos

~~~python
usuario = ""
if not usuario:
    print("Debe ingresar un nombre")
~~~

~~~python
a = 7
if a % 2 == 0:
    print("Es par")
else:
    print("Es impar")
~~~

---

### Más información

Más detalles sobre `bool`:  
[https://www.w3schools.com/python/python_booleans.asp](https://www.w3schools.com/python/python_booleans.asp)
