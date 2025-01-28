#### Actividad 5


ROM         |    Explicación
__________________________________________________
@9          |  -Al iniciar el programa, el PC equivale a 1. @9 Asigna al registro A como valor 9
D=A         |  -Aqui, D copia el valor de A
@60         |  -Luego, el registro de A toma como valor 60
D=D+A       |  -D suma los valores de A y D, y los asigna a simismo.
@6          |  -El registro de A toma el valor de 6.
M=D         |  -Aqui, D guarda su valor en la memoria en la posición de A, o sea 6.
@0          |  -El registro de A toma el valor de 0.
0;JMP       |  -PC saltara a la dirección del registro de A, en este caso, 0, haciendo que el programa entre en un bucle.
