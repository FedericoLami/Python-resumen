## Valores Flotantes (`float`) en Python

El tipo de dato `float` representa **números reales**, es decir, números con parte decimal.

~~~python
x = 3.14
type(x)
# out: <class 'float'>
~~~

---

### ¿Cuándo se usa `float`?

Cuando un número:

- Tiene parte decimal.
- Resulta de una división con `/`, aunque el resultado sea exacto.

~~~python
a = 10 / 2
print(a)         # 5.0
type(a)          # float
~~~

---

### Operaciones con `float`

Los valores `float` permiten todas las operaciones aritméticas:

- Suma: `+`
- Resta: `-`
- Multiplicación: `*`
- División: `/`
- División entera: `//`
- Módulo: `%`
- Potencia: `**`

~~~python
a = 5.5
b = 2

print(a + b)     # 7.5
print(a - b)     # 3.5
print(a * b)     # 11.0
print(a / b)     # 2.75
print(a // b)    # 2.0
print(a % b)     # 1.5
print(a ** b)    # 30.25
~~~

---

### Conversión de tipos

Se pueden convertir otros tipos a `float`:

~~~python
print(float(10))       # 10.0
print(float("3.14"))   # 3.14
~~~

Un `float` puede convertirse a `int`, pero pierde la parte decimal:

~~~python
x = int(7.9)
print(x)     # 7
~~~

---

### Precisión y errores comunes

Los `float` tienen **limitaciones de precisión** por cómo se representan en memoria.

~~~python
print(0.1 + 0.2)
# out: 0.30000000000000004
~~~

Esto es normal y sucede en muchos lenguajes de programación.

---

### Funciones útiles

- `round(x, n)` → redondea a `n` decimales  
- `abs(x)` → valor absoluto  
- `pow(x, y)` → potencia  
- `int(x)` → convierte a entero

~~~python
x = 3.14159

print(round(x, 2))   # 3.14
print(abs(-4.2))     # 4.2
print(pow(2.0, 3))   # 8.0
print(int(x))        # 3
~~~

---

### Entrada desde el usuario

Las entradas del usuario se reciben como `str`, por eso deben convertirse a `float`.

~~~python
precio = float(input("Ingresá el precio: "))
print(precio * 2)
~~~

---

### Comparaciones

Los `float` se pueden comparar igual que los `int`:

~~~python
x = 2.5
y = 3.1

print(x < y)     # True
print(x == 2.5)  # True
~~~

---

### Notación científica

Los `float` se pueden escribir usando notación científica:

~~~python
print(1.5e2)     # 150.0
print(2.3e-3)    # 0.0023
~~~

---

### Más información

Más detalles:  
[https://www.w3schools.com/python/python_numbers.asp](https://www.w3schools.com/python/python_numbers.asp)
