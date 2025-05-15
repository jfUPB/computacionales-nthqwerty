#### Actividad 7

**Valores en la Memoria:**

En notación hexadecimal, el valor `0a` corresponde a 10 en decimal.
De igual forma, `14` en hexadecimal equivale a 20 en decimal.

Es importante notar que los bytes se almacenan en formato *little-endian*, lo que significa que el byte de menor peso (el menos significativo) se coloca primero en la memoria. Esta es una característica común en muchas arquitecturas modernas, como la familia x86, y afecta cómo se interpretan los datos a nivel bajo.

---

**Diferencia entre Constructor y Destructor en C++:**

* **Constructor:** Es una función especial dentro de una clase que se ejecuta automáticamente al crear un objeto. Su función principal es inicializar los atributos del objeto, preparando su estado inicial. Por ejemplo, en una clase `Punto`, el constructor puede asignar valores iniciales a las coordenadas `x` e `y`.

* **Destructor:** Se invoca automáticamente cuando el objeto deja de estar en uso, es decir, cuando sale del ámbito donde fue declarado o cuando se destruye explícitamente. Su objetivo es liberar recursos adquiridos durante la vida del objeto, como memoria dinámica, conexiones o archivos abiertos, para evitar fugas y asegurar una correcta limpieza.

---

**Diferencia entre Objeto y Clase en C++:**

* **Clase:** Actúa como un plano o plantilla que define la estructura y el comportamiento que tendrán sus objetos. Define los datos (atributos) y las funciones (métodos) comunes a todos los objetos que se creen a partir de ella.

* **Objeto:** Es una instancia específica de una clase que existe en memoria durante la ejecución. Cada objeto posee sus propios valores para los atributos definidos en la clase, funcionando como una entidad concreta derivada del molde.

---

**Diferencias entre `Punto` en C++ y C#:**

* **En C++:** La instrucción `Punto p(10, 20);` crea un objeto `p` directamente en la pila (stack). Esto implica que la memoria para `p` se asigna automáticamente y su destrucción ocurre al salir del ámbito donde fue declarado.

* **En C#:** La declaración `Punto p = new Punto(10, 20);` genera un objeto en el heap. La variable `p` no contiene el objeto en sí, sino una referencia o puntero a la ubicación del objeto en el heap. El recolector de basura se encarga de liberar esta memoria cuando el objeto deja de ser accesible.

---

**¿Qué es `p` en C++ y qué es `p` en C#?**

* En **C++**, `p` es el propio objeto, almacenado directamente en la pila con sus datos concretos.

* En **C#**, `p` es una referencia o puntero que apunta a un objeto ubicado en el heap, no contiene los datos del objeto directamente.

---

**Parte de Memoria donde se Almacena `p`:**

* En **C++**, la instancia `p` reside en el stack, una región de memoria que maneja automáticamente la creación y destrucción de variables basadas en su ámbito.

* En **C#**, la variable `p` (la referencia) se guarda en el stack, pero el objeto real está en el heap. La referencia apunta a la dirección donde se encuentra el objeto.

---

**¿Qué es un Objeto en C++ Según lo Observado?**

Un objeto en C++ representa una instancia específica de una clase, con sus propios valores y métodos. Por ejemplo, en la clase `Punto`, el objeto `p` tiene valores concretos para `x` e `y`. Cuando no se usa `new`, este objeto se guarda en el stack, y su vida está limitada al ámbito donde se declara. Este enfoque garantiza una gestión automática y eficiente de la memoria para objetos locales.
