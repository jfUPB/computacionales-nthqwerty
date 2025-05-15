#### Actividad 3

Los dos fragmentos en C++ cumplen la misma tarea —acumular la suma de 1 a 100—, pero difieren solo en su envoltorio sintáctico:

* El **while** separa claramente la asignación inicial de i y luego realiza el incremento dentro del bloque.
* El **for** concentra la inicialización, la prueba condicional y la actualización en una sola línea, aunque internamente sigue el mismo patrón de ejecución.

**Versión en ensamblador de la estructura for:**

```
@sum      // sum = 0
M=0
@i        // i = 1
M=1

(LOOP)
@i
D=M       // D = i
@100
D=D-A     // D = i - 100
@END
D;JGT     // Si i > 100, salta a END

@i
D=M       // D = i
@sum
M=D+M     // sum = sum + i

@i
M=M+1     // i = i + 1

@LOOP
0;JMP     // Vuelve al inicio del ciclo LOOP

(END)
@END
0;JMP     // Bucle infinito para terminar el programa
```

Cuando traduces ambos estilos de bucle al Hack, descubres que:

* **Inicialización**: cargas sum e i en sus direcciones de RAM.
* **Condición**: comparas i con 100 usando la resta en D y haces un salto condicional.
* **Cuerpo**: actualizas la suma.
* **Incremento**: aumentas i manualmente.

En ensamblador no existen etiquetas especiales para while o for: todo se reduce a organizar saltos y cargas/almacenamientos de registros.

**Conclusiones**

1. Tanto for como while acaban convirtiéndose en los mismos pasos de máquina: inicialización, comparación, cuerpo e incremento, porque el hardware solo entiende saltos y operaciones aritmético-lógicas.
2. Desmenuzar cómo cada sección de un bucle de alto nivel se refleja en instrucciones (A-instructions y C-instructions) ofrece una perspectiva real de lo que ocurre en cada ciclo de reloj.
3. Al ejecutar este código en el simulador Hack, obtendrás sum = 5050, demostrando que, más allá de la sintaxis, el flujo de control y la lógica determinan el resultado.
