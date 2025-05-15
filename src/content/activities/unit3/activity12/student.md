#### Actividad 12

En el Stack:

El objeto se crea dentro de un bloque delimitado por llaves {} y su ciclo de vida está restringido a ese ámbito específico.
Al entrar en el bloque, se llama automáticamente al constructor para inicializar el objeto, y al salir, se invoca el destructor para liberar los recursos asociados.
La memoria utilizada por el objeto se libera de forma automática, sin necesidad de que el programador intervenga manualmente.
Esto hace que el manejo de memoria en el stack sea sencillo y eficiente, aunque limitado en tamaño y duración.

En el Heap:

El objeto se crea dinámicamente usando new y permanece en memoria hasta que se libera explícitamente mediante delete.
El constructor se ejecuta al momento de la creación con new, pero el destructor solo se llama si el programador invoca delete.
La gestión de memoria en el heap es responsabilidad del desarrollador, por lo que un mal manejo puede causar fugas de memoria o corrupción.
El heap es adecuado para objetos que requieren una vida útil más flexible o que deben persistir más allá del ámbito local.

-¿Por qué pBloque se destruye y pBloque2 no?

pBloque es un objeto creado directamente en el stack; su memoria se maneja automáticamente y se libera cuando el bloque finaliza, invocando su destructor.
pBloque2 es un puntero almacenado en el stack, pero apunta a un objeto que vive en el heap. Como el heap no se limpia automáticamente, ese objeto permanece en memoria hasta que se llame a delete.

-¿pBloque2 es un objeto o una referencia?

pBloque2 es un puntero, es decir, una variable que contiene la dirección de memoria de otro objeto, no el objeto en sí mismo.

-¿Dónde se almacena pBloque2?

Se almacena en el stack, dado que es una variable local dentro de la función main.

-¿Dónde está el objeto al que apunta pBloque2?

El objeto apunta a una dirección en el heap, ya que fue creado dinámicamente con new, y su ciclo de vida depende de una gestión manual mediante delete.

Este contraste entre stack y heap es fundamental para comprender la gestión de memoria en C++. Mientras que el stack ofrece rapidez y manejo automático pero con un tamaño limitado, el heap proporciona flexibilidad para objetos con vida útil variable pero requiere cuidado para evitar errores comunes como fugas de memoria. Por eso, entender cuándo y cómo usar cada tipo de memoria es crucial para el desarrollo eficiente y seguro de programas en C++.
