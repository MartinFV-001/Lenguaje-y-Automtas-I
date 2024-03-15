# Expresiones Regulares: Concepto, Importancia y Casos de Uso

Las expresiones regulares, también conocidas como regex o regexp, son patrones de búsqueda utilizados para encontrar y manipular texto basado en ciertas reglas definidas. Estas reglas pueden incluir la coincidencia de caracteres específicos, rangos de caracteres, repeticiones, y mucho más. Las expresiones regulares se utilizan en una variedad de contextos, desde la búsqueda y validación de cadenas de texto hasta el procesamiento de datos estructurados.
<p align="center">
  <img src="https://sarudalf3.github.io/assets/images/posts/Regex.png" width="500">
</p>

## Concepto:

Una expresión regular es una secuencia de caracteres que define un patrón de búsqueda. Estos patrones pueden ser simples o muy complejos, dependiendo de las necesidades del usuario. Las expresiones regulares se construyen utilizando una sintaxis específica que permite definir reglas de coincidencia precisa o flexible.
<p align="center">
  <img src="https://i.pinimg.com/originals/6a/e0/9d/6ae09d56f3894692b0c0c735a9882916.gif" width="500">
</p>

*Ejemplo de un filtrado de texto:* 

 - ### Expresión Regular:
   
   La expresión regular que utilizaremos es: `/alvaro|alexys/`
   ### Ejemplos de Filtrado: 
|Numero|Texto de Entrada                                                 |Resultado Filtrado|
|-------|-----------------------------------------------------------------|------------------|
|1      |"El nombre de mi amigo es **alvaro** y el de mi compañero es **alexys**."|alvaro, alexys    |
|2      |"Me llamo **alvaro** y mi hermana se llama **alexys**."                  |alvaro, alexys    |
|3      |"Mi amigo se llama Álvaro y mi hermano se llama Alex."         |(ningún resultado ya que los nombres no estan como se a dicho o no aparecen)|
|4      |"**Alvaro** y **Alexys** son buenos amigos."                             |alvaro, alexys    |
|5      |"El nombre de mi perro es **Alvaro** y mi gato se llama **Alexys**."     |alvaro, alexys    |


## Importancia:
Las expresiones regulares revolucionan la forma en que interactuamos con el texto en el mundo digital. Desde la validación de formularios web hasta el análisis de logs en sistemas informáticos, su importancia radica en su capacidad para buscar patrones específicos y manipular datos de manera precisa y eficaz.

<p align="center">
  <img src="https://i.pinimg.com/originals/5b/22/49/5b224949fa4150484fbcb3710612d915.gif" width="500">
</p>
 - **Búsqueda y Validación de Texto**: Las expresiones regulares son esenciales para buscar y validar cadenas de texto en aplicaciones informáticas. Permiten a los desarrolladores encontrar patrones específicos dentro de grandes conjuntos de datos de manera eficiente.
		
	- Supongamos que queremos validar si una cadena de texto contiene la palabra "**perro**".
		La expresión regular `/perro/` nos permite buscar y validar esta palabra en un texto.

 - **Manipulación de Texto**: Con expresiones regulares, se puede manipular fácilmente el texto mediante la búsqueda y reemplazo de cadenas basadas en patrones definidos. Esto es útil en la limpieza de datos, transformación de texto y análisis de datos.
 
	 - Imagina que deseamos reemplazar todas las letras "a" en una cadena de texto con un guion "-". 
	 - La expresión regular `s/a/-/g` nos permite realizar esta manipulación.

 - **Formateo de Datos**: En aplicaciones donde es necesario validar y formatear datos de entrada, las expresiones regulares son fundamentales. Por ejemplo, se pueden utilizar para verificar la validez de direcciones de correo electrónico, números de teléfono, códigos postales, etc.
	 - Si queremos verificar si una cadena de texto tiene el formato de una dirección de correo electrónico, podemos usar la expresión regular `/^[^\s@]+@[^\s@]+\.[^\s@]+$/`.

 - **Análisis de Logs**: En sistemas informáticos, las expresiones regulares son ampliamente utilizadas para analizar archivos de registro (logs) y extraer información relevante, como errores, eventos importantes, direcciones IP, etc.

	 - Supongamos que estamos analizando un archivo de registro y queremos extraer todas las direcciones IP que aparecen en él. Podemos utilizar la expresión regular `\b(?:\d{1,3}\.){3}\d{1,3}\b` para este propósito.

 - **Procesamiento de Lenguaje Natural (NLP)**: En el campo del procesamiento de lenguaje natural, las expresiones regulares pueden ser útiles para tokenizar texto, encontrar patrones lingüísticos específicos, y realizar otras tareas de preprocesamiento de datos.

	 - Si queremos dividir un párrafo en oraciones, podemos utilizar la expresión regular `(?<=[.!?])\s+`.
    
 - **Web Scraping**: En la extracción de datos de páginas web, las expresiones regulares son herramientas valiosas para identificar y extraer información específica de la estructura HTML.

	 - Si queremos extraer todos los enlaces de una página web, podemos utilizar la expresión regular `<a\s+(?:[^>]*?\s+)?href="([^"]*)"`.

## Casos de Uso:
Esencial en aplicaciones web para garantizar la integridad y precisión de los datos ingresados por los usuarios, como direcciones de correo electrónico y códigos postales, tambien es fundamental en entornos de administración de sistemas para identificar errores, eventos importantes y tendencias en registros de sistemas informáticos, permitiendo diagnósticos y soluciones rápidas y eficientes.
<p align="center">
  <img src="https://i.pinimg.com/originals/9d/1f/82/9d1f82cc324e498dd5127a6ed0296dac.gif" width="500">
</p>

1. **Validación de Formularios**: En aplicaciones web, las expresiones regulares se utilizan para validar datos ingresados por el usuario en formularios, como direcciones de correo electrónico, números de teléfono, contraseñas, etc.
	 - La expresión regular "^\d{5}$" se puede utilizar para **validar un código** postal de cinco dígitos.

2. **Análisis de Logs**: En entornos de administración de sistemas, las expresiones regulares son fundamentales para analizar registros de eventos y diagnosticar problemas en servidores y aplicaciones.
	-  **Expresión Regular**: `ERROR: (.*)`
	   **Descripción**: Esta expresión regular buscará líneas de registro que comiencen con "ERROR:" y capturará el mensaje de error en un grupo de captura. Por ejemplo, "ERROR: El servidor ha encontrado un error interno" sería capturado como mensaje de error.
	
3. **Procesamiento de Texto**: En el campo del procesamiento de texto, las expresiones regulares se utilizan para realizar tareas como la tokenización, eliminación de caracteres no deseados, identificación de entidades, entre otros.
	-   **Expresión Regular**: `(?<=[.!?])\s+`
  **Descripción**: Esta expresión regular dividirá un párrafo en oraciones. Busca espacios seguidos de uno o más caracteres de puntuación (punto, interrogación o exclamación).

5. **Búsqueda Avanzada**: En editores de texto y IDEs, las expresiones regulares permiten realizar búsquedas avanzadas y reemplazos con criterios específicos, lo que agiliza el proceso de edición de código y texto.
	-   **Expresión Regular**: `\berror\b`
   **Descripción**: Esta expresión regular buscará la palabra "error" como una palabra completa (no parcial) en un archivo de código fuente. Evita coincidencias con palabras como "errors" o "error404".

6. **Extracción de Datos**: En proyectos de minería de datos y análisis de texto, las expresiones regulares son utilizadas para extraer información específica de grandes conjuntos de datos de manera automatizada.
	-   **Expresión Regular**: `\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b`
  **Descripción**: Esta expresión regular buscará patrones que coincidan con direcciones de correo electrónico en un conjunto de datos. Busca una secuencia de caracteres alfanuméricos seguida de "@" y luego otro conjunto de caracteres alfanuméricos seguido de un punto y un dominio.

## Conclusion
Las expresiones regulares son una herramienta poderosa y versátil en el ámbito de la informática y el procesamiento de texto. Su capacidad para definir patrones de búsqueda y manipular texto de manera eficiente las convierte en una herramienta indispensable en una amplia variedad de aplicaciones y escenarios.
<p align="center">
  <img src="https://i.pinimg.com/originals/98/fe/f3/98fef3f6784cb3575d9f723aa9f8ecaa.gif" width="500">
</p>

# Referencias 


 - _¿Qué son las expresiones regulares?_  (2019). EDteam - En Español Nadie Te Explica Mejor. https://ed.team/blog/que-son-las-expresiones-regulares
 - el, L. (2024).  _Liberar el poder de las expresiones regulares en aplicaciones de listado - FasterCapital_. FasterCapital. https://fastercapital.com/es/contenido/Liberar-el-poder-de-las-expresiones-regulares-en-aplicaciones-de-listado.html#:~:text=Las%20expresiones%20regulares%20se%20utilizan,(XXX)%20XXX%2DXXXX.
 - aukera. (2016, August 31).  _Expresiones Regulares para GTM y Analítica Web - Aukera_. Aukera. https://aukera.es/blog/expresiones-regulares-analytics-gtm/
 - Vasili. (2022, October 23).  _8 Expresiones regulares, que debes conocer_. Code Envato Tuts+; Envato Tuts. https://code.tutsplus.com/es/8-regular-expressions-you-should-know--net-6149t
 - _Lenguaje regular - EcuRed_. (2024). Ecured.cu. https://www.ecured.cu/Lenguaje_regular
 - _Pinterest_. (2024). Pinterest; Pinterest. https://www.pinterest.com.mx/
 - _Cómo formar etiquetas con expresiones regulares y substrings (Súper-etiquetas)_. (2023). Help Center DANAconnect. https://help.danaconnect.com/es/article/como-formar-etiquetas-con-expresiones-regulares-y-substrings-super-etiquetas-rnbqtm/
 - adegeo. (2023, May 9).  _cuantificadores en expresiones regulares - .NET_. Microsoft.com. https://learn.microsoft.com/es-es/dotnet/standard/base-types/quantifiers-in-regular-expressions
