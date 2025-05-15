#### Actividad 8

**Direcciones de memoria:**

`pStack` representa un objeto creado directamente en la pila (*stack*), y su dirección de memoria se asigna automáticamente por el sistema.
![image](https://github.com/user-attachments/assets/728120c5-330a-4af8-8ee8-80738e25f100)


`pHeap`, en cambio, es un puntero que contiene la dirección de un objeto que fue instanciado dinámicamente en el *heap* mediante el uso de `new`.

![image](https://github.com/user-attachments/assets/96febe1b-4c0f-4b5c-b554-9438b80525da)


**Diferencias entre pStack y pHeap:**

* **pStack:** Es un objeto como tal, no un puntero. Se encuentra en el *stack* y su ciclo de vida está controlado automáticamente por el alcance del bloque de código donde fue creado.

* **pHeap:** Es un puntero que guarda la dirección de un objeto creado dinámicamente en el *heap*. Aunque el puntero `pHeap` está en el *stack*, el objeto al que apunta vive en el *heap*, y es responsabilidad del programador liberar esa memoria con `delete`.

**Visualización en Memory1:**

* Al revisar el contenido de `pHeap` en el panel Memory1, estarás viendo la dirección que apunta al objeto en el *heap*.
* Si inspeccionas `&pHeap`, estarás accediendo a la dirección en el *stack* donde está almacenado el puntero mismo.

*pHeap
![image](https://github.com/user-attachments/assets/77651699-03fe-4fce-864c-33cbc031b351)

*&pHeap
![image](https://github.com/user-attachments/assets/6c78f414-499c-4132-856f-e2f409edb224)
