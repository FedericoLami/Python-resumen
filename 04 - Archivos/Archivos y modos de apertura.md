
**¿Qué es un archivo?**

Es una unidad de almacenamiento que contiene datos o información y que está guardada en un sistema de archivos. Es como un documento físico: tiene un **nombre**, un **tipo** (como `.txt`, `.csv`, `.pdf`, `.jpg`, etc.), y **contenido**.
Tipos comunes de archivos:
- .txt
- .csv
- .py
- .jpg / .png
- .pdf

**Manejo de archivos**

Existen funciones predefinidas. Si las operaciones fallan, se levanta una excepción, los archivos se manejan como objetos que se crean usando la función **open**

**La función open**

~~~ Python
open(file,mode, ...)
~~~

En la sección mode ponemos el modo en el que queremos abrir el archivo:
- " r ": read
- "w": write
- "a": append
- "x": create
¿De qué modo se abren estos archivos? ¿Qué significan? 

Veamos algunos ejemplos para entender mejor los modos para abrir archivos

**Caso 1: usamos modo " W "**

Bien, en Python, el modo **W** se utiliza para abrir un archivo en modo de escritura (write mode).
El modo de escritura es cuando abris un archivo para escribir en él. Si el archivo **no existe**, se creara uno nuevo. Si el archivo **ya existe**, se sobrescribe completamente, eliminando su contenido anterior

Uso típico: Este modo es útil para crear nuevos archivos o reemplazar el contenido de un archivo existente con datos nuevos.

~~~ Python
file1 = open('archivo.txt', 'w')
~~~

**Caso 2: usamos modo " X "**

Modo de escritura exclusiva, cuando abrimos un archivo en modo **X**, el archivo se abre para escritura, pero **solo si el archivo no existe**. Si el archivo ya existe, se lanza un error **FileExistsError** en lugar de sobrescribirlo.

Uso típico: Este modo es útil cuando queremos asegurarnos de no sobrescribir accidentalmente un archivo existente, garantizando que se cree un archivo nuevo.

~~~Python
file2 = open('archivo.txt', 'x')
~~~

**Caso 3: usamos modo " A "**

Modo anexar, abrimos un archivo en modo **A**, el archivo se abre para escritura, pero en lugar de sobrescribir contenido, los nuevos datos se agregan al final del archivo. Si el archivo no existe, se crea uno nuevo.
Este modo es útil para agregar datos a un archivo existente, como en registro de logs o archivos de datos acumulativos.

~~~ Python
file3 = open('archivo.txt','a')
~~~


**Caso 4: usamos modo " R "**

El modo **R** es el modo de lectura, no se puede escribir en el archivo, en caso de que este no exista se lanzara un error **FileNotFoundError**

~~~ Python
file4 = open('archivo.txt','r')
~~~


**Otros argumentos de la función open**

~~~ Python
open(file, mode = 'r', buffering = -1, encoding = None, errors = None, newline = None, closefd = True, opener = None)
~~~

- **buffering:** Controla cómo se almacena temporalmente (en el buffer) el contenido del archivo antes de leerlo o escribirlo.
	1. -1: usa el valor por defecto del sistema
	2. 0: sin Buffer, solo para modo binario
	3. Numero positivo: Tamaño del buffer en bytes (para optimizar lecturas/escrituras)
	
- **encoding:** Especifica la codificación del texto (ejemplo: "utf-8", "latin-1")
	1. Solo aplica en modo texto (no binario).
	2. Si es **None**, usa la codificación por defecto del sistema (por ejemplo, UTF-8 en muchos sistemas)
	
- **errors:** Define cómo manejar errores al leer / escribir texto con problemas de codificación
	1. Ejemplo: "**strict**" (lanza error, por defecto), "**ignore**" (ignora errores), "**replace**" (reemplaza caracteres problemáticos)
	2. Si es **None** usa "**strict**"
	
- **newline:** Controla cómo se manejan los saltos de linea (\n,\r, \r\n) en archivos de texto.
	1. **None**: Detecta automáticamente el formato de salto de línea.
	2. "" o valores como **"\n"** o **"\r"**: Forza un formato específico
	
- **closefd:** Indica si se cierra el descriptor de archivo (un número que identifica el archivo en el sistema).
	1. **True:** Cierra el archivo al cerrar el objeto
	2. **False:** Mantiene el descriptor abierto (raro, usado en casos avanzados).
	
- **opener:** Permite usar una función personalizada para abrir el archivo en lugar del método estándar.
	1. Es **None** por defecto (usa el método estándar).
	2. Útil para casos avanzados, como manejar archivos de manera especial.

**NOTA:** en la mayoría de los casos, solo se necesitara utilizar **FILE** y **MODE**. Los otros argumentos son para configuraciones específicas


**¿Qué pasa cuando el archivo está en otro directorio?**

Usamos [pathlib](https://docs.python.org/es/3/library/pathlib.html) descripta en la [PEP 428](https://peps.python.org/pep-0428/): una interfaz orientada a objetos que permite el manejo de rutas.

~~~ Python
from pathlib import 
Pathfile_ejemplo = Path('ejemplos') / "clase04" / "ejemplo.txt"  
file_ejemplo
~~~

**¿Cómo almacenar datos en un archivo?**

Vamos a ver el caso más sencillo: guardar solo texto plano.

~~~ Python
file_muchachos = Path('ejemplos') / "clase04" / "muchachos1.txt"

f = open(file_muchachos, 'w')  

cad1 = "De los pibes de Malvinas"  
cad2 = "Que jamás olvidaré."  

f.write("En Argentina nací")  
f.write("Tierra del Diego y Lionel")  
f.write(cad1)  
print(f.write(cad2))  

f.close()
~~~

1. **write(cadena):** escribe cadena en el archivo y retorna cantidad de caracteres escritos.
2. **close():** cierra el archivo.


**La sentencia with**

La sentencia [with](https://docs.python.org/3/reference/compound_stmts.html#with) crea un objeto denominado runtime context o contexto de tiempo de ejecución qué permite ejecutar un grupo de sentencias bajo el control de un **administrador de contexto** o **context manager**.
El ejemplo típico se da en el acceso a archivos, ya que son recursos externos a nuestros programas que requieren una gestión adecuada.

~~~ Python
with open(file_route_csv) as file_csv:  
	csv_reader = csv.reader(file_csv, delimiter=',')  
	header, data = next(csv_reader), list(csv_reader)

print(header)  
for line in data:  
print(line)
~~~

Veamos el siguiente ejemplo:
~~~ Python
with open(data_temp) as file_temp:
	csv_reader = csv.reader(file_temp, delimiter = ',')
	for line in csv_reader
		print(line)
	header,data = next(csv_reader), list(csv_reader)
~~~

Un iterador es un objeto que representa un flujo de datos, al abrir este, nos posicionamos en el primer ítem y luego utilizando el método **next()** del iterador vamos obteniendo los siguientes ítems del flujo.
Para poder trabajar con estos datos debemos guardarlos en una variable:

~~~Python
with open(data_temp) as file_temp:
	csv_reader = csv.reader(file_temp, delimiter = ',')
	header, data = next(csv_reader), list(csv_reader)
~~~

Y en caso de querer un diccionario para acceder a los datos?

~~~ Python
data = {}
with open(data_temp) as file_temp:
	csv_reader = csv.DictReader(file_temp, delimiter = ',')
	for row in csv_reader:
		print(row)
~~~

Recordemos que **DictReader** permite crear un diccionario donde el nombre de las columnas son las **keys** y el valor de la celda son las **values**


**Ordenar los datos**

Para ordenar los datos podemos utilizar:
- **[sort](https://www.w3schools.com/Python/ref_list_sort.asp):** es un método que permite ordenar una secuencia modificándola.
- **[sorted](https://www.w3schools.com/python/ref_func_sorted.asp):** es una función que nos permite ordenar una secuencia indicando varias opciones para la acción sin modificar la secuencia original.

**Módulo datetime**

[Datetime](https://docs.python.org/3/library/datetime.html) es un módulo para trabajar y realizar cálculos con las fechas.
Contiene varias clases para manejar fechas y tiempo:
- **date**: se utiliza para fechas pero no guarda hora, minutos ni segundos
- **time**: se utiliza para operar valores de tiempo al nivel de minutos a microsegundos
- **datetime**: contiene información de las fechas **date** y tiempo **time**

¿Qué podemos realizar con la clase **datetime**?
- **datetime.now()**: nos da la fecha actual
- **datetime.timestamp(datetime.now())**: convierte la hora actual en el formato timestamp, que es utilizado para guardar fecha de forma única.
- **datetime.strptime():** convierte un string con el formato que le indicamos en un objeto datetime.
- **date.strftime("%m/%d/%Y, %H:%M:%S")**: convierte un objeto datetime a un string
- **date.weekday()**: podemos saber el día de la semana de la fecha
- **date.hour:** podemos saber la hora

Los datos que se guardan en los logs, en general van acompañados de un timestamp, que es un número que representa el tiempo pasado desde 1/1/1970

**%m/%d/%Y, %H:%M:%S**: le indica el formato que debe representarse la fecha.