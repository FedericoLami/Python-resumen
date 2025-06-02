
**Introducción al manejo de excepciones en Python**

Una **excepción** es un acontecimiento, que ocurre durante la ejecución de un programa, que interrumpe el flujo normal de las instrucciones del programa


**Qué situaciones pueden producir excepciones?**

- Abrir un archivo que no existe o donde no tenemos permisos adecuados.
- Acceder al contenido de un archivo que no respeta el formato.
- Invocar un método o función que no fue definida.
- Referirse a una variable que no fue definida.
- Mezclar tipos de datos sin convertirlos previamente.

Declaración de excepciones en Python:

~~~ Python
try:
	sentencias
except nombreExcepcion:
	sentencias
except nombreExcepcion:
	sentencias
except:
~~~

Para más información visitar la [documentación oficial](https://docs.python.org/3/library/exceptions.html)

Ejemplo de excepciones:

~~~ Python
file_name = 'pp.txt'
try:
	file_data = open(file_name)
except FileNotFoundError:
	print(f'El archivo {file_name} no se encuentra')
~~~

**Forma de saber el nombre de la excepción**

~~~ Python
file_books_csv = 'books.csv'
import csv
try:
	with open(file_route/file_books_csv) as csvfile:
		csv_reader = csv.reader(csvfile, delimiter = ';')
		for row in csv_reader:
			if row[3] > '2024':
				print(row)
		header, data = next(csv_reader), list(csv_reader)
except Exception as e:
	print(f'La excepción fue: {e}')
	print(f'La excepción es {type(e).__name__}')
~~~

**Qué hace type(e)?**
~~~ Python
type(e).__name__
~~~

se utiliza para saber el nombre de la clase de la excepción, nos permite especificar el nombre.

**¿Cómo es la forma de propagación que utiliza Python?**

- Primero busca estáticamente
- Si no se encuentra, busca dinámicamente a quién llamó a la función.
- Si encuentra un manejador lo captura.
- Si no encuentra un manejador entonces termina el programa con error.

**Algunas preguntas para entender mejor el tema de Excepciones:**

**¿Qué acción se toma después de levantada y manejada una excepción? ¿Se continúa con la ejecución de la unidad que lo provocó o se termina?**

- Las sentencias después de generada la excepción no se ejecutan. Si se captura la excepción se continúa con la ejecución del programa según el flujo por fuera del bloque **try**, sino da error el programa.

**¿En qué casos es mas legible excepciones y cuándo flow-control?**

- Las excepciones son más legibles cuando se manejan **errores inesperados**, mientras que el control de flujo es preferible para **condiciones esperadas y predecibles**.

**¿Cómo se alcanza una excepción?**

- Una excepción se alcanza cuando se produce un error en el código.

**¿Cómo especificar los manejadores de excepciones que se deben ejecutar cuando se alcanzan las mismas?**

- Se especifican utilizando bloques **try** y **except**, donde se define el código que se ejecutará en caso de que ocurra una excepción. Opcionalmente podemos utilizar **else** y/o **finally**

**¿Qué sucede cuando no se encuentra un manejador para una excepción levantada?**

- Si no se encuentra un manejador estáticamente, **la excepción se propaga** dinámicamente. Si no se maneja, el programa termina con un mensaje de error.


**Utilización de ELSE, FINALLY y RAISE**

**ELSE**

- Se utiliza la cláusula `else` para incluir el código que se debería ejecutar si **no se levanta ninguna excepción** en el bloque try.. except

**FINALLY**

- Se utiliza la cláusula `finally` para incluir el código que se ejecuta **siempre**, independientemente si se levanta o no alguna excepción en el bloque try.. except

**RAISE**

- Podes usar `raise` para generar un traceback de la excepción que se generó y para relanzar la misma excepción anterior al `raise`

**Algunas de las excepciones predefinidas (built-in)**

- **ImportError:** error con importación de módulos.
- **ModuleNotFoundError:** error por módulo no encontrado.
- **IndexError:** error por índice fuera de rango.
- **NameError:** error por nombre no encontrado.
- **SyntaxError:** error por problemas sintácticos
- **ZeroDivisionError:** error por división por cero.
- **IOError:** error en entrada salida.

[listado completo](https://docs.python.org/3/library/exceptions.html)