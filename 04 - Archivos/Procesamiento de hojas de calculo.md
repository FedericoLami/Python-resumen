Una hoja de cálculo es un tipo de documento que permite manipular datos numéricos y alfanuméricos dispuestos en forma de tablas compuestas por celdas, las cuales se suelen organizar en una matriz de filas y columnas

El programa más popular para manipular estos archivos es Microsoft Excel, Google Sheets y LibreOffice.

Para entender mejor el procesamiento en hojas de calculo en Excel vamos a trabajar con los siguientes [archivos](https://gobiernoabierto.cordoba.gob.ar/data/datos-abiertos/categoria/turismo/afluencia-turistica-en-hoteles-apart-hoteles-y-hostales/138)

1. **Procesamos el formato Excel**
Una opción es utilizar la librería openpyxl
~~~Python
from pathlib import Path
from openpyxl import load workbook

data_route = Path('Ejemplo') / 'pathRandom' / 'Afluencia turística CORDOBA.xlsx'
~~~

2. Abrimos el archivo usando la función **load_workbook**
~~~Python
work_book = load workbook(filename = data route)
~~~

3. Obtenemos los nombres de las hojas del archivo
~~~ Python
sheet_names = work_book.sheetnames
print(sheet_names)
out : ['2023','2022','2021','2020','2019','2018']
~~~

4. Procesamos las hojas de datos
Vamos a crear un diccionario con el nombre de la hoja como clave. En este caso, corresponden a los años desde 2018 a 2023. Utilizaremos **iter_rows**

~~~Python
summer_tourists = {}

for sheet_name in sheet_names:
	sheet = work_book[sheet_name]
	total_tourists = 0
	#Itera sobre las filas y columnas de las hojas
	for row in sheet.iter_rows(values_only = True):
		if row[0] in ("Ene", "Feb"):
			total_tourists += row[10]
	summer_toursits[sheet_name] = total_tourists
~~~
