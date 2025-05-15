#### Actividad 10

¿Qué sucede después de llamar a la función cambiarNombre? ¿Por qué se muestra el mensaje Destructor: Punto cambiado(70, 80) destruido.? Cuando llamamos a cambiarNombre pasando el objeto original por valor:

```cpp
void cambiarNombre(Punto p, string nuevoNombre) {
    p.name = nuevoNombre;
}
```

Se crea una copia del objeto original dentro del parámetro p de la función. Dentro de la función, se modifica el nombre del objeto p, pero ese cambio solo afecta a la copia local. Al finalizar la función, esa copia se elimina y se invoca su destructor, por eso aparece el mensaje de destrucción.

¿Por qué aparece el mensaje del destructor?
Porque p es un objeto creado en la pila (stack) de la función, siendo una copia del original, y cuando la función termina, p se destruye automáticamente, llamando a su destructor.

¿Por qué el objeto original sigue existiendo tras llamar a cambiarNombre?
El objeto original permanece intacto porque fue pasado por valor, lo que implica que no se modifica directamente. Solo se alteró la copia dentro de la función, sin afectar el objeto original en main. En C++, pasar un objeto por valor genera una copia local, y los cambios en esa copia no impactan el objeto original.

¿Dónde se localizan original y p en el mapa de memoria? ¿Son el mismo objeto?

* original: ubicado en la pila (stack) dentro de main.
* p: también en la pila, pero es una copia local dentro de cambiarNombre.
  No son el mismo objeto; original es el objeto definido en main, mientras que p es una copia creada dentro de la función cambiarNombre.

Ahora, modificamos cambiarNombre para pasar por referencia:

```cpp
void cambiarNombre(Punto& p, string nuevoNombre) {
    p.name = nuevoNombre;
}
```

¿Qué sucede en este caso? ¿Por qué?
Al pasar el objeto por referencia (Punto& p), no se crea una copia, sino que se pasa una referencia al objeto original. Por eso, cualquier modificación dentro de la función altera directamente el objeto original. Al llamar a cambiarNombre, el nombre de original se actualiza y no se destruye ninguna copia.

Luego, modificamos cambiarNombre y main para usar punteros:

```cpp
void cambiarNombre(Punto* p, string nuevoNombre) {
    p->name = nuevoNombre;
}

int main() {
    // Objeto original
    Punto original("original", 70, 80);
    original.imprimir();

    cambiarNombre(&original, "cambiado");
    original.imprimir();
    return 0;
}
```

¿Qué ocurre ahora? ¿Por qué?
Al pasar el objeto original como puntero (\&original), se envía la dirección de memoria del objeto original. Dentro de cambiarNombre, se usa el puntero p para acceder y modificar directamente el objeto original con el operador ->. Por tanto, no se crean copias, y el cambio afecta el objeto real. La diferencia fundamental con la referencia es que aquí se manipula explícitamente la dirección de memoria.

Diferencias entre pasar un objeto por valor, referencia y puntero:

* Por valor: Se envía una copia del objeto; los cambios dentro de la función no afectan al original, y la copia se destruye al salir de la función.
* Por referencia: Se pasa una referencia al objeto original; las modificaciones dentro de la función afectan directamente al objeto original.
* Por puntero: Se pasa la dirección de memoria del objeto; se accede y modifica el objeto original mediante el puntero, trabajando explícitamente con la dirección, a diferencia de la referencia.
