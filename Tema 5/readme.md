<p align="center">
  <img src="img/logos.png">
</p>

<h1 align="center">INGENIERÍA EN SISTEMAS COMPUTACIONALES</h1>

<h2 align="center">Proyecto Analizador Sintactico PyEspañol</h2>

<p align="center">
<b>NOMBRE DE LA ASIGNATURA:</b><br>
Lenguaje y Automatas I
</p>

<p align="center">
<b>INTEGRANTES DEL EQUIPO:</b><br>
 Martin Feria Vázquez - 21200594<br>
 Ramírez Hernández Josué - 21200990<br>
 Valdez Zuñiga Leonardo Vicente - 24200196<br>
 Zeron López Germán Eduardo - 21200642
</p>

<p align="center">
<b>PROFESOR DE LA MATERIA:</b><br>
Ing. Rodolfo Baumé Lazcano
</p>

<p align="center">
<b>PACHUCA, HIDALGO, 27 DE MAYO DEL 2024</b>
</p>

<p align="center">
<b>INSTITUTO TECNOLÓGICO DE PACHUCA</b><br>
<i>“El hombre alimenta el ingenio en contacto con la Ciencia”</i>
</p>

---


## Índice
1. [Propósito](#propósito)
2. [¿Qué es un analizador sintactico?](#qué-es-un-analizador-sintactico)
3. [Definición de Tokens](#definición-de-tokens)
4. [Tabla de Tokens](#tabla-de-tokens)
5. [Expresiones regulares](#expresiones-regulares)
6. [Manejo de Espacios en Blanco y Comentarios](#manejo-de-espacios-en-blanco-y-comentarios)
7. [Prioridad de Coincidencia](#prioridad-de-coincidencia)
8. [Acciones Asociadas a los Tokens](#acciones-asociadas-a-los-tokens)
9. [Manejo de errores](#manejo-de-errores)
10. [Conclusión](#conclusión)
11. [Interface Gráfica o Aplicación](#interface-gráfica-o-aplicación)
12. [Repositorio en el cual se trabajó](#repositorio-en-el-cual-se-trabajó)
13. [Referencias](#referencias)

---

<h2 style="text-align: center;" id="propósito">Propósito</h2>
<p>El analizador sintáctico se encarga de verificar la estructura gramatical del código fuente, asegurando que esté conforme a las reglas del lenguaje de programación. Este proceso es crucial en la fase de compilación o interpretación del lenguaje, ya que una correcta sintaxis es fundamental para la correcta ejecución del programa.</p>

<div align="center">
    <img src="img/proposito.png" alt="Propósito">
</div>

---

<h2 style="text-align: center;" id="qué-es-un-analizador-sintactico">¿Qué es un analizador sintactico?</h2>
<p>Un analizador sintáctico o parser (viene del inglés: parse - analizar una cadena o texto en componentes sintácticos lógicos) es un programa que normalmente es parte de un compilador. El compilador se asegura de que el código se traduce correctamente a un lenguaje ejecutable.</p>

<div align="center">
    <img src="img/quees.png" alt="¿Qué es un analizador sintactico?">
</div>

---

<h2 style="text-align: center;" id="definición-de-tokens">Definición de Tokens</h2>
<h3 style="text-align: center;">Definición del lenguaje (PyEspañol):</h3>
<ul>
    <li><strong>Palabras clave:</strong> "si", "sino", "mientras", "para", "función", "retorno", "clase", "importar", "verdadero", "falso"</li>
    <li><strong>Identificadores:</strong> Secuencias de letras y números que comienzan con una letra (Variables).</li>
    <li><strong>Números:</strong> Secuencias de dígitos enteros (0-9).</li>
    <li><strong>Operadores:</strong> "+", "-", "*", "/", "=", "==", "&lt;", "&gt;"</li>
    <li><strong>Símbolos especiales:</strong> "(", ")", "{", "}", ";"</li>
    <li><strong>Comentarios:</strong> Se pueden denotar con "#" para comentarios de una sola línea.</li>
</ul>

<h3 style="text-align: center;">Especificación de tokens para PyEspañol:</h3>
<ul>
    <li><strong>Palabras clave:</strong> <code>si|sino|mientras|para|función|retorno|clase|importar|verdadero|falso</code></li>
    <li><strong>Identificadores:</strong> <code>[a-zA-Z][a-zA-Z0-9]*</code></li>
    <li><strong>Números:</strong> <code>\d+(\.\d+)?</code></li>
    <li><strong>Operadores:</strong> <code>\+|\-|\*|\/|=|==|&lt;|&gt;</code></li>
    <li><strong>Símbolos especiales:</strong> <code>\(|\)|\{|\}|\;</code></li>
    <li><strong>Comentarios:</strong> <code>#.*</code></li>
</ul>

<h3 style="text-align: center;">Patrones regulares para cada tipo de token (en formato regex):</h3>
<ul>
    <li><strong>Palabras clave:</strong> <code>\b(si|sino|mientras|para|función|retorno|clase|importar|verdadero|falso)\b</code></li>
    <li><strong>Identificadores:</strong> <code>[a-zA-Z][a-zA-Z0-9]*</code></li>
    <li><strong>Números:</strong> <code>\d+(\.\d+)?</code></li>
    <li><strong>Operadores:</strong> <code>==|!=|&lt;=|&gt;=|&lt;|&gt;|=|\+|\-|\*|\/</code></li>
    <li><strong>Símbolos especiales:</strong> <code>[{}();,]</code></li>
    <li><strong>Comentarios:</strong> <code>#.*</code></li>
</ul>

---

<h2 style="text-align: center;" id="tabla-de-tokens">Tabla de Tokens</h2>

| TOKEN    | Tipo            |
|----------|-----------------|
| Si       | Palabra Clave   |
| Sino     | Palabra Clave   |
| Mientras | Palabra Clave   |
| Para     | Palabra Clave   |
| Función  | Palabra Clave   |
| Retorno  | Palabra Clave   |
| Clase    | Palabra Clave   |
| Importar | Palabra Clave   |
| Verdadero| Palabra Clave   |
| Falso    | Palabra Clave   |
| Variable | Identificador   |
| 1-9      | Número          |
| +        | Operador        |
| -        | Operador        |
| *        | Operador        |
| /        | Operador        |
| =        | Operador        |
| ==       | Operador        |
| <        | Operador        |
| >        | Operador        |
| (        | Símbolo Especial|
| )        | Símbolo Especial|
| {        | Símbolo Especial|
| }        | Símbolo Especial|
| ;        | Símbolo Especial|
| #        | Comentario      |

---
<h2 style="text-align: center;" id="expresiones-regulares">Expresiones regulares</h2>
<p>Las expresiones regulares son utilizadas para definir patrones en cadenas de caracteres. Se emplean para reconocer los diferentes tokens en el código fuente del lenguaje PyEspañol.</p>
<ul>
    <li><strong>Palabras clave:</strong> <code>\b(si|sino|mientras|para|función|retorno|clase|importar|verdadero|falso)\b</code></li>
    <li><strong>Identificadores:</strong> <code>[a-zA-Z][a-zA-Z0-9]*</code></li>
    <li><strong>Números:</strong> <code>\d+(\.\d+)?</code></li>
    <li><strong>Operadores:</strong> <code>==|!=|&lt;=|&gt;=|&lt;|&gt;|=|\+|\-|\*|\/</code></li>
    <li><strong>Símbolos especiales:</strong> <code>[{}();,]</code></li>
    <li><strong>Comentarios:</strong> <code>#.*</code></li>
</ul>

<div align="center">
    <img src="img/01.png" alt="Expresiones Regulares">
</div>

---

<h2 style="text-align: center;" id="manejo-de-espacios-en-blanco-y-comentarios">Manejo de Espacios en Blanco y Comentarios</h2>
  
</p>Los comentarios en el código fuente se manejan mediante la expresión regular r'#.*'. Estos son ignorados completamente por el analizador léxico, ya que están asociados a None.</p>

<div align="center">
    <img src="img/02.png" alt="Expresiones Regulares">
</div>
---

<h2 style="text-align: center;" id="prioridad-de-coincidencia">Prioridad de Coincidencia</h2>
<p>Cuando una misma secuencia de caracteres puede corresponder a múltiples tokens, se priorizan las coincidencias más largas. Esto se logra al ordenar las expresiones regulares de manera que las coincidencias más específicas aparezcan primero.</p>

<div align="center">
    <img src="img/03.png" alt="Expresiones Regulares">
</div>
---

<h2 style="text-align: center;" id="acciones-asociadas-a-los-tokens">Acciones Asociadas a los Tokens</h2>
<p>Las acciones asociadas a cada token incluyen la asignación de un tipo de token y la recopilación de información adicional, como el valor de un número. Si un carácter o secuencia no coincide con ningún patrón, se genera un error léxico.</p>

<div align="center">
    <img src="img/04.png" alt="Expresiones Regulares">
</div>
---

<h2 style="text-align: center;" id="manejo-de-errores">Manejo de errores</h2>
<p>Los errores de análisis léxico y sintáctico se manejan generando mensajes de error descriptivos y deteniendo el análisis. Esto asegura que los problemas en el código fuente se identifiquen y reporten de manera clara.</p>

<div align="center">
    <img src="img/05.png" alt="Expresiones Regulares">
</div>
---

<h2 style="text-align: center;" id="conclusión">Conclusión</h2>
<p>El analizador sintáctico es un componente indispensable en el proceso de compilación que aporta estructura y coherencia al análisis del código fuente. Su capacidad para verificar la corrección sintáctica, facilitar el análisis semántico, y proporcionar una base para la optimización y generación de código, lo convierte en un pilar fundamental para la construcción de compiladores eficientes y robustos. A través de un análisis sintáctico riguroso, los compiladores pueden ofrecer herramientas más poderosas y amigables para los desarrolladores, contribuyendo significativamente a la calidad y eficiencia del software producido.</p>

<div align="center">
    <img src="img/con.jpg" alt="Conclusión">
</div>

---

<h2 style="text-align: center;" id="interface-gráfica-o-aplicación">Interface Gráfica o Aplicación</h2>
<p>Una interfaz gráfica de usuario (GUI) o una aplicación puede facilitar la interacción con el analizador léxico, permitiendo a los usuarios ingresar código y ver los resultados del análisis en tiempo real. Esta interfaz debe ser intuitiva y amigable para el usuario.</p>

<div align="center">
    <img src="img/ig.png" alt="Interface Gráfica">
</div>

---

<h2 style="text-align: center;" id="repositorio-en-el-cual-se-trabajó">Repositorio en el cual se trabajó</h2>
<p>El código fuente y la documentación del proyecto están disponibles en un repositorio en línea, accesible para todos los interesados en estudiar o contribuir al desarrollo del analizador léxico.</p>
<p style="text-align: center;"><strong>Repositorio:</strong> <a href="https://github.com/MartinFV-001/AnalizadorSintacticoLexico">https://github.com/MartinFV-001/AnalizadorSintacticoLexico</a></p>
<p style="text-align: center;"><strong>Web:</strong> <a href="https://martinfv-001.github.io/AnalizadorSintacticoLexico/">https://martinfv-001.github.io/AnalizadorSintacticoLexico/</a></p>

---

<h2 style="text-align: center;" id="referencias">Referencias</h2>
<ol>
    <li>Aho, A. V., Lam, M. S., Sethi, R., & Ullman, J. D. (2006). Compilers: Principles, Techniques, and Tools (2nd ed.). Pearson.</li>
    <li>Analizador sintáctico de oraciones. (2023). Sintaxis.org. <a href="Https://sintaxis.org/analizador/‌">Https://sintaxis.org/analizador/</a></li>
    <li>Python Software Foundation. (2023). Python Language Reference, version 3.10.<a href="https://docs.python.org/3.10/reference/">https://docs.python.org/3.10/reference/</a></li>
  
</ol>
