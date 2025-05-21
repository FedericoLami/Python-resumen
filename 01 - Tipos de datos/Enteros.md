## Valores Enteros (`int`) en Python

El tipo de dato `int` representa **números enteros**, es decir, sin decimales (positivos, negativos o cero).

~~~python
x = 22
type(x)
# out: <class 'int'>
~~~

---

### Operaciones con enteros

Con los valores enteros se pueden realizar operaciones matemáticas básicas:

- Suma: `+`
- Resta: `-`
- Multiplicación: `*`
- División entera (descarta decimales): `//`
- Módulo (resto): `%`
- Potencia: `**`

~~~python
a = 10
b = 3

print(a + b)    # 13
print(a - b)    # 7
print(a * b)    # 30
print(a // b)   # 3
print(a % b)    # 1
print(a ** b)   # 1000
~~~

---

### Conversión de tipos

La división con `/` siempre devuelve un `float`, incluso si el resultado es exacto.

~~~python
resultado = 10 / 2
type(resultado)
# out: <class 'float'>
~~~

Se puede convertir explícitamente a `int`:

~~~python
resultado = int(10 / 2)
type(resultado)
# out: <class 'int'>
~~~

---

### Funciones útiles con enteros

- `abs(x)` → valor absoluto  
- `pow(x, y)` → potencia  
- `divmod(x, y)` → devuelve una tupla `(cociente, resto)`  
- `int(valor)` → convierte a entero si es posible

~~~python
print(abs(-7))          # 7
print(pow(2, 3))        # 8
print(divmod(10, 3))    # (3, 1)
print(int("42"))        # 42
~~~

---

### Números grandes y negativos

Python permite trabajar con enteros de cualquier tamaño (limitado solo por la memoria).

~~~python
grande = 10**100
print(grande)
~~~

Los enteros también pueden ser negativos:

~~~python
negativo = -25
print(negativo)
~~~

---

### Entrada desde el usuario

Las entradas por teclado se reciben como `str`, por lo tanto hay que convertirlas a `int`.

~~~python
numero = int(input("Ingresá un número entero: "))
print(numero * 2)
~~~

---

### Comparaciones

Se pueden comparar valores enteros usando:

- `==` igual  
- `!=` distinto  
- `<`, `>`, `<=`, `>=`

~~~python
x = 5
y = 10

print(x < y)     # True
print(x == 5)    # True
print(x != y)    # True
~~~

---

### Más información

Para más detalles:  
[https://www.w3schools.com/python/python_numbers.asp](https://www.w3schools.com/python/python_numbers.asp)
