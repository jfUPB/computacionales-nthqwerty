#### Actividad 5

Al ejecutar el programa, se nota que los valores de las variables globales se actualizan correctamente. La variable global_inicializada cambia de 42 a 69, y global_no_inicializada pasa de 0 (su valor por defecto) a 666. Esto ocurre porque ambas están almacenadas en el segmento de datos, que está destinado a variables globales y estáticas, y permite tanto lectura como escritura. Por eso, el programa puede modificar sus valores sin inconvenientes durante la ejecución.

El compilador genera un error cuando se intenta acceder directamente a var_estatica desde main(). Esto se debe a que var_estatica es una variable local estática que, aunque mantiene su valor entre llamadas y no se destruye al salir de la función, solo es accesible dentro del ámbito en el que fue declarada, es decir, dentro de funcionConStatic(). No se puede acceder desde fuera de esa función por las reglas de encapsulación del lenguaje.
