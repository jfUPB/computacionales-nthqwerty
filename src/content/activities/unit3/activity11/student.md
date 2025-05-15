#### Actividad 12

Miembros de instancia:

Son variables que pertenecen exclusivamente a cada objeto creado a partir de una clase.
Cada objeto posee su propia copia, almacenada de forma independiente en memoria.
La ubicación en memoria depende de cómo se crea el objeto:

* Si se crea de forma directa, generalmente se guarda en la pila (stack).
* Si se crea dinámicamente, se aloja en el montón (heap).

Ventajas: Permiten que cada objeto mantenga su propio estado, facilitando el diseño orientado a objetos.
Desventajas: La creación de muchas instancias puede aumentar el consumo de memoria, ya que cada objeto conserva sus datos propios.
Cuándo usarlos: Son ideales cuando cada objeto debe manejar información diferente respecto a los demás.

Miembros estáticos:

No están ligados a objetos específicos, sino a la clase en sí.
Solo existe una copia compartida por todos los objetos de esa clase.
Se almacenan en el segmento de datos estáticos del programa, similar a las variables globales.

Ventajas: Ahorran memoria cuando se requiere un valor común para todos los objetos; útiles para contadores o configuraciones globales.
Desventajas: Pueden generar problemas si no se controlan adecuadamente, especialmente en programas con múltiples hilos (multithreading).
Casos de uso: Útiles para contar cuántos objetos se han creado, definir constantes globales o implementar funciones compartidas.

Distribución en memoria:

* c1 y c2: Son objetos locales creados dentro de main, por lo que se almacenan en la pila (stack) y se destruyen automáticamente al salir del ámbito.
* c3: Es un puntero ubicado en la pila, pero apunta a un objeto creado dinámicamente con new, que reside en el montón (heap) hasta que se libera con delete.
* Objeto apuntado por c3: Se encuentra en el heap, y su gestión de memoria es manual, responsabilidad del programador.
* Contador::total: Al ser un miembro estático, se aloja en la sección de datos globales (data segment) y su ciclo de vida abarca toda la ejecución del programa, sin importar la cantidad de objetos creados.
