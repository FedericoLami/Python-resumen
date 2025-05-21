
Un módulo es un archivo (con extensión .py) que contiene sentencias y definiciones.
Usualmente un programa puede estar formado por muchos módulos.

**La sentencia import**
Permite acceder a funciones y variables definidas en otro módulo
~~~Python
import random
~~~

- Si el módulo contiene definiciones de funciones, sólo se importa estas definiciones, no las ejecuta.
- Para ejecutar una función definida en otro módulo debo invocarla en forma explícita.

**Archivos .pyc**
Son archivos que se ejecutan en caso de que no exista el modulo .py, es una forma de ejecutar mas rápido que en un archivo .py

Afecta solo la velocidad de carga del archivo: "Un programa no se ejecuta más rápido cuando es leído de un archivo .pyc que cuando es leído de un archivo .py"
Más información en el [sitio oficial](https://peps.python.org/pep-3147/)


**Import**
Cuando usamos la sentencia **import** se actualizan los espacios de nombres.

~~~Python
import mi_modulo
~~~
- En este caso, todos los recursos definidos dentro de **mi_modulo** serán locales a **mi_modulo**
- Lo que se agrega al espacio de nombres es el nombre del módulo (**mi_modulo**)
- Para usarlo debo hacerlo con notación puntual. (**mi_modulo.recurso**)

**Otra forma de importación**
~~~Python
from mi_modulo import una_funcion
~~~

- Sólo se importa una_funcion de mi_modulo (no el nombre del módulo)
- El único nombre que se agrega al espacio de nombres es **una_funcion**
~~~ Python
from mi_modulo import *
~~~
- En este caso, todos los ítems definidos en **mi_modulo** formarán parte del espacio de nombres actual.
- **Esta forma no está recomendada:** podrían existir conflictos de nombres.

**Biblioteca de módulos estándar**
- Existe un conjunto de módulos que vienen incluidos con el intérprete.
- Para usarlos se los debe importar en forma explícita (usando **sentencia import**).
- Para mas información visitar la [pagina oficial](https://docs.python.org/es/3.11/library/index.html)