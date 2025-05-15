#### Actividad 2

**¿En qué direcciones de memoria se implementan las variables i y sum?**
En Hack, el ensamblador asigna automáticamente espacio para las variables a partir de la dirección 16 de la RAM, a menos que especifiquemos otra ubicación. De este modo, la primera variable definida (por ejemplo, i) se guarda en RAM\[16] y la siguiente (sum) en RAM\[17], simplificando el mapeo de nombres a celdas de memoria.

**¿Cuál es la diferencia entre la dirección de una variable y su contenido?**
La “dirección” es el número de casilla de RAM donde reside el dato (por ejemplo, 16 para `i`), mientras que el “contenido” es el valor almacenado en esa posición en un instante dado (por ejemplo, si `i = 50`, entonces RAM\[16] contiene el número 50). En el simulador de Hack aparecen dos columnas que muestran por separado la dirección y lo que hay dentro de cada posición de memoria.

**¿Cómo se implementa la condición i <= 100?**
La condición i <= 100 se traduce en estas instrucciones:

```
@i
D=M        // D = i
@100
D=D-A      // D = i - 100
@END
D;JGT      // Si (i - 100) > 0, salta a END
```

Después de ejecutar este fragmento, si el resultado de i − 100 es positivo, el salto condicional D;JGT lleva el flujo a la etiqueta END, interrumpiendo el bucle. En cambio, si el resultado no supera cero (es decir, i sigue siendo ≤ 100), la ejecución continúa con la siguiente instrucción del ciclo.
