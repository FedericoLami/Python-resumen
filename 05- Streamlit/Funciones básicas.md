
**[Streamlit](https://docs.streamlit.io/)** es una herramienta que permite generar web apps interactivas sencillas.

Características:
- Es sencillo para comenzar a desarrollar web apps
- Orientado a la ciencia de datos
- Permite la integración con las librerías más usadas de Python directamente
- Actualización en tiempo real, las modificaciones se visualizan sin volver a ejecutar

**Instalación**

- Se recomienda generar un entorno virtual
- Instalar utilizando pip

~~~ Git
$ python3 -m venv env
$ source env/bin/activate
$ (env) $ pip install streamlit
~~~

**Creación de una aplicación básica**

- Importar el módulo Streamlit en un script de Python
- Utilizar la función **st.write()** para mostrar texto en la aplicación
- Ejecutar la aplicación utilizando el comando **streamlit run archivo.py**
- Organizar la información

**st.write()** es una función para mostrar texto que permite múltiples opciones y puede mostrar varios tipos de datos.

Algunos de los tipos que soporta son:
- **write(string)** Imprime el string en formato Markdown, con soporte de expresiones LaTeX, emojis y texto en color
- **write(data_frame)** Muestra el DF en formato de tabla.
- **write(error)** Imprime la excepción
- **write(mpl_figure)** Muestra una figura de Matplotlib
- **write(altair)** Muestra un gráfico de Altair
- **write(plotly_fig)** Muestra una figura de Plotly
- **write(dict)** Muestra un diccionario en un widget interactivo.

**Personalización**

- Definir el estilo de la página:
~~~ Python
	st.set_page_config(layout="wide")
~~~
- Cambiar el título de la aplicación con
~~~ Python
st.title()
st.header()
st.subheader()
~~~
- Generar divisiones en la pantalla con
~~~ Python
st.divide()
~~~


**Estructuración**

Podemos estructurar nuestra página usando diferentes recursos:
- Pages
- Containers
	1. Tabs
	2. Columnas
	3. Formularios

**Pages**

- Estructura dinámica, se debe crear un directorio **pages** y dentro de crear archivos con numeración:
	- 01_nombre pagina1.py
	- 02_nombre pagina2.py
	- 03_emoji_nombre pagina3.py
- Se genera un sidebar.
- El orden en que se muestra está dado por la numeración.
- Se pueden poner emojis.

**Tabs**

- Nos permite organizar nuestros datos
- Se deben definir con una lista los nombres en los tabs y luego incluir el código dentro de cada una

**Columnas**

- Divide el espacio según la cantidad de columnas **st.columns(number)**
- Cada columna debe indicarse con el número correspondiente, en lugar de **st**, se debe ir **c1** o la columna correspondiente.
Ejemplo
~~~ Python
with tab1:
	c1,c2 = st.columns(2)
	c1.write("Columna 1")
	c2.write("Columna 2")
~~~

**Formularios**

- Debe tener un botón "form_submit_button" para permitir el envío
- Los datos no se refrescan hasta que se hace clic sobre el botón
Ejemplo:
~~~ Python
with my_form:
	questions_data = [1,2,3]
	my_form.write("Dentro del form")
	my_form.write(f"##Información del usuario")
	usuario = my_form.text_input('Usuario', 'completar')
	answer = my_form.radio('Cuanto te gusta Streamlit:', questions_data, index = None)
	submitted = st.form_submit_button("Responder")
~~~