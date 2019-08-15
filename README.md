# Interpreter

El patrón de diseño interpreter es utilizado para evaluar un lenguaje definido como Expresiones, este patrón nos permite interpretar un lenguaje como Java, C#, SQL o incluso un lenguaje inventado por nosotros el cual tiene un significado; y darnos una respuesta tras evaluar dicho lenguaje.

Interpreter es uno de los patrones de diseño más complejos debido a que para su funcionalidad debe combinar técnicas de programación orientada a objetos avanzada y su interpretación puede ser algo confusa, las principales cosas con las que nos enfrentaremos son la Herencia, Polimorfismo y la Recursividad.

Los componentes del patrón Interpreter se explican a continuación:

Client:Actor que dispara la ejecución del interpreter.
Context:Objeto con información global que será utilizada por el intérprete para leer y almacenar información global entre todas las clases que conforman el patrón, este es enviado al interpreter el cual lo replica por toda la estructura.
AbstractExpression:Interface que define la estructura mínima de una expresión.
TerminalExpression:Se refiere a expresiones que no tienen más continuidad y al ser evaluadas o interpretadas terminan la ejecución de esa rama. Estas expresiones marcan el final de la ejecución de un sub-árbol de la expresión.
NonTerminalExpression:Son expresiones compuestas y dentro de ellas existen más expresiones que deben ser evaluadas. Estas estructuras son interpretadas utilizando recursividad hasta llegar a una expresión Terminal.

Se aplica cuando:

Debemos trabajar con sentencias de un lenguaje que nuestro lenguaje de programación no reconoce automáticamente.
La gramática del lenguaje con el que debemos trabajar es sencilla. Para gramáticas complejas se deben emplear técnicas concretas de la Teoría de Gramáticas Formales (scanners y parsers).
No debe utilizarse si ya existe alguna clase nativa que interprete éste lenguaje. Por ejemplo en Python, si recibimos una expresión aritmética mediante un String, utilizaremos la función eval() en lugar de implementar un Interpreter.

Consecuencias:

POSITIVAS:

Fácil modificación y ampliación de los elementos gramaticales (al ser representados mediante una jerarquía de clases).
Su implementación es sencilla (en comparación con otros métodos para implementar esta funcionalidad).
La implementación de los métodos para cada elemento del lenguaje es dinámica (puede cambiarse en tiempo de ejecución).
NEGATIVAS:

No es muy eficiente.
No cubre gramáticas complejas.
