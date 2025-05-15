#### Actividad 4

En C++ declaramos una variable entera y un puntero que almacena su dirección, cambiando luego el valor a través de ese puntero:

```cpp
int a = 10;      // a tiene el valor 10
int* p;          // p es un puntero
p = &a;          // p guarda la dirección de a
*p = 20;         // cambia el valor de a (usando p) a 20
```

Como en Hack Assembler no existen tipos de datos ni punteros, simularíamos esa misma lógica reservando dos celdas de RAM: una para `a` y otra para `p`, donde `p` contiene el número de la dirección de `a`. Al “desreferenciar” `p`, cargamos su contenido y apuntamos a esa posición para escribir el nuevo valor:

```asm
// int a = 10;
@10
D=A
@a      // a se almacena en RAM[16]
M=D     // M[a] = 10

// int* p;
// p = &a;
@a
D=A     // D tiene la dirección de a (que es 16)
@p      // p se almacena en RAM[17]
M=D     // M[p] = 16

// *p = 20;
@p
A=M     // A = contenido de p => A = 16
@20
D=A
M=D     // M[16] = 20 (a = 20)

// Bucle infinito (opcional para detener el programa)
(END)
@END
0;JMP
```
