#### Actividad 4

La función de A-instructions y C-instructions es:
A-instructions: Representar direcciones de memoria o valores en la memoria. Es una forma de establecer direcciones de memoria.
C-instructions: Son instrucciones de cálculo, que operan sobre los valores de las direcciones y determinan el comportamiento de la máquina.




Sus representaciones binarias son:
Las A-instruccions se representa con un prefijo 0 seguido por 15 bits que representan la dirección de memoria o el valor numérico.

Las C-instructions tienen un formato de 16 bits y se dividen en varios campos:
Bit 0: Es siempre 1 (indica que es una C-instruction).
Bits 1-3: Definen el tipo de operación de la ALU (Unidad Aritmético Lógica).
Bits 4-10: Son los bits que representan el registro destino (dónde guardar el resultado).
Bits 11-15: Representan la condición para el salto (en el caso de instrucciones de salto condicional).

1  [comp] [dest] [jump]
Donde:
comp es la parte que representa la operación de la ALU (por ejemplo, suma, resta, etc.).
dest indica el registro de destino para la operación.
jump es el campo de salto (si corresponde).





Ejemplos de A-instructions:

0  0000000000000101:         A-instruction con valor 5

0  0000000000011111:         A-instruction con valor 15

0  0000000001100100:         A-instruction con valor 5


Ejemplos de C-instructions:

111  0000000  001  000:     Sumar los valores de A y D, y guardar el resultado en D.

111  1110000  001  000:     Negar el valor de A y guardar el resultado en D

111  0000010  000  010:     Si el valor de A es mayor que 0, salta a la dirección 100.
