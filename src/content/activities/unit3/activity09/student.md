#### Actividad 9

**¿Qué sucede al copiar un objeto en C++ y en C#?**

En C++, al copiar un objeto se genera una nueva instancia independiente. Esto significa que cualquier modificación realizada en la copia no tendrá impacto en el objeto original, ya que son dos entidades separadas en memoria.

En cambio, en C#, al copiar un objeto, en realidad se copia la referencia que apunta al objeto en el heap. Por lo tanto, tanto la variable original como la copia señalan a la misma ubicación en memoria, y los cambios realizados a través de cualquiera de ellas afectan al mismo objeto compartido.

**¿Qué significa copiar en C++ y en C#? ¿Es una copia independiente del original?**

En C++, copiar un objeto implica crear una instancia completamente nueva, independiente del original, con su propio espacio en memoria y valores separados.

En C#, copiar una variable que contiene un objeto significa duplicar la referencia al mismo objeto, no el objeto en sí. Por ende, la copia no es independiente; ambas referencias operan sobre el mismo objeto en memoria.
