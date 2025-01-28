#### Actividad 6

El direccionamiento directo es un modo de acceso a la memoria en el cual la dirección de la memoria a la que se desea acceder es especificada directamente en la instrucción. Es decir, no se usa una dirección calculada o modificada por un registro; simplemente se indica explícitamente cuál es la dirección en la memoria que se quiere leer o escribir. En el contexto de la máquina Hack, el direccionamiento directo significa que puedes referirte a una dirección específica de memoria en una instrucción sin necesidad de usar cálculos o registros intermedios.

M=D: Almacena el valor de D en la memoria en la dirección A.

D=M: Carga el valor de la memoria en la dirección A en el registro D.

Puntero:
En el contexto de la memoria y la computación, un puntero es una variable o registro que almacena la dirección de memoria de otro valor o dato. Es decir, en lugar de contener directamente el valor de un dato (como un número o texto), el puntero guarda la dirección de memoria donde ese dato está almacenado. Los punteros permiten manipular direcciones de memoria de manera flexible y eficiente, lo que es especialmente útil para trabajar con estructuras de datos dinámicas o grandes.

Ejemplo:
@100
M=5
@101
M=10
(Usar un "puntero" (registro A) para acceder a la memoria).
@100        
D=M         
@101
D=D+M
