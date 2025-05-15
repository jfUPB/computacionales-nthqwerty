#### Actividad 5

```
// int a = 10;
@10
D=A
@a      // RAM[16]
M=D     // a = 10

// int b = 5;
@5
D=A
@b      // RAM[17]
M=D     // b = 5

// int* p;
// p = &a;
@a
D=A     // dirección de a (16)
@p      // RAM[18]
M=D     // p = 16 (guarda la dirección de a)

// b = *p;
@p
A=M     // A = contenido de p (16), ahora apuntamos a a
D=M     // D = M[16] (contenido de a, que es 10)
@b
M=D     // b = 10 (guarda el valor en RAM[17])

// Bucle infinito (opcional para terminar el programa)
(END)
@END
0;JMP
```
