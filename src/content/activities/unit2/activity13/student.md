#### Actividad 13

**¿Qué aprendí?**
Durante el curso, aprendí a traducir conceptos de programación de alto nivel —como condicionales, ciclos (while y for), uso de punteros y definición de funciones— al lenguaje ensamblador Hack. Este proceso me ayudó a entender cómo se representan realmente estas estructuras en la memoria y en el flujo de ejecución de un computador. Por ejemplo, al convertir un ciclo *while* a ensamblador, comprendí cómo funcionan los saltos condicionales y cómo se controla manualmente la dirección a la que el programa debe continuar, algo que en lenguajes como C# ocurre automáticamente.

**Conceptos más desafiantes**
Lo más complicado para mí fue manejar punteros y funciones con parámetros. Estas tareas implican trabajar directamente con direcciones de memoria, algo que en alto nivel no vemos porque el lenguaje se encarga de eso por nosotros. En ensamblador, uno debe asegurarse de cargar correctamente las direcciones, usar los registros adecuados (como A y D), y controlar cuidadosamente la secuencia de instrucciones. Implementar una función con parámetros y retorno, por ejemplo, requiere una comprensión profunda del uso de la RAM como espacio de trabajo temporal y del control del flujo con saltos.

**Estrategias que usé**
Para resolver los ejercicios, empecé dividiendo cada problema en partes simples: inicialización, condición, cuerpo y actualización (en el caso de ciclos, por ejemplo). Luego simulaba manualmente cómo se comportaría el programa línea por línea, para asegurarme de que entendía su lógica. También me apoyé mucho en el simulador de Hack para visualizar cómo cambiaban los registros y la memoria con cada instrucción, y revisé ejemplos de código y explicaciones para reforzar lo aprendido.

**Lo que más me ayudó**
La estrategia más útil fue practicar constantemente con simuladores, porque me permitía experimentar y ver de forma visual cómo se ejecutaba el código. Además, comparar el código en ensamblador con su versión equivalente en C# me ayudó a entender qué hace cada instrucción y cómo encajan todas en un flujo lógico. Esa comparación fue clave para corregir errores, mejorar mi comprensión del funcionamiento del hardware y pensar en términos de eficiencia.
