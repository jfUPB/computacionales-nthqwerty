#### Actividad 6

Experimento 5 – Variables locales estáticas frente a no estáticas

En este experimento se comparan las diferencias entre variables locales normales y variables locales con el modificador static.

La variable local sin static (var_no_estatica) se declara dentro de una función y se inicializa cada vez que se llama la función. Al estar almacenada en el segmento Stack, su vida útil está limitada al bloque donde fue creada. Por eso, cada vez que la función se ejecuta, la variable se destruye al salir y se reinicia a 100 en cada llamada.

En contraste, la variable local con static (var_estatica) también se define dentro de una función, pero al usar la palabra clave static, se guarda en el segmento de datos. Esto le permite mantener su valor entre las llamadas a la función. En el experimento, comienza con 100, y conforme se invoca la función repetidamente, su valor se incrementa y permanece almacenado.

Este comportamiento confirma que:

Las variables locales no estáticas se destruyen al terminar la función.

Las variables locales estáticas retienen su estado entre llamadas y no se reinician.

Experimento 6 – Modificación del segmento Heap

Aquí se asigna memoria dinámica para un arreglo usando new[], lo que coloca los datos en el Heap. Después se inicializan los elementos, y se imprimen tanto sus valores como sus direcciones de memoria. Luego, se libera la memoria con delete[].

Posteriormente, se intenta acceder al arreglo después de liberarlo, lo cual provoca un comportamiento indefinido porque se está accediendo a memoria ya marcada como libre. Aunque a veces no cause un error inmediato, puede originar bloqueos, fallos como segmentation fault o corrupción de memoria.

Diferencias entre Heap y Stack:

Stack:

La gestión de memoria es automática.

La memoria se libera al salir del ámbito de la función.

Es más rápido pero con espacio limitado.

Ideal para variables temporales y locales.

Heap:

La gestión de memoria es manual mediante new y delete.

Permite reservar memoria durante la ejecución.

Más flexible, pero con mayor riesgo de errores si no se maneja bien.

Ideal para estructuras dinámicas como arreglos que cambian de tamaño.

Conclusión

Los experimentos muestran que las variables locales estáticas mantienen su valor entre llamadas, mientras que las no estáticas se reinician cada vez que la función se ejecuta. En cuanto a la memoria dinámica, usar el Heap requiere asignar y liberar memoria manualmente, y acceder a memoria liberada puede causar errores graves. La diferencia principal entre Heap y Stack es la flexibilidad frente a la gestión automática, siendo fundamental liberar correctamente la memoria en el Heap para evitar fugas que puedan afectar el rendimiento o la estabilidad del programa.
