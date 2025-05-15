#### Actividad 13

``` cpp
#include <iostream>
#include <string>
#include <vector>

class Libro {
private:
    std::string titulo;
    std::string autor;
    int anioPublicacion;
    bool prestado;
    
    static int contadorLibros;

public:
    Libro(const std::string& _titulo, const std::string& _autor, int _anio) 
        : titulo(_titulo), autor(_autor), anioPublicacion(_anio), prestado(false) {
        contadorLibros++;
        std::cout << "Libro creado: " << titulo << std::endl;
    }
    
    Libro(const Libro& otroLibro) 
        : titulo(otroLibro.titulo), autor(otroLibro.autor), 
          anioPublicacion(otroLibro.anioPublicacion), prestado(otroLibro.prestado) {
        contadorLibros++;
        std::cout << "Libro copiado: " << titulo << std::endl;
    }
    
    ~Libro() {
        contadorLibros--;
        std::cout << "Libro destruido: " << titulo << std::endl;
    }
    
    void mostrarInfo() const {
        std::cout << "Título: " << titulo << std::endl;
        std::cout << "Autor: " << autor << std::endl;
        std::cout << "Año: " << anioPublicacion << std::endl;
        std::cout << "Estado: " << (prestado ? "Prestado" : "Disponible") << std::endl;
    }
    
    bool comprobarDisponibilidad() const {
        return !prestado;
    }
    
    void prestar() {
        if (!prestado) {
            prestado = true;
            std::cout << "El libro '" << titulo << "' ha sido prestado." << std::endl;
        } else {
            std::cout << "El libro '" << titulo << "' ya está prestado." << std::endl;
        }
    }
    
    void devolver() {
        if (prestado) {
            prestado = false;
            std::cout << "El libro '" << titulo << "' ha sido devuelto." << std::endl;
        } else {
            std::cout << "El libro '" << titulo << "' no estaba prestado." << std::endl;
        }
    }
    
    static int obtenerContadorLibros() {
        return contadorLibros;
    }
};

int Libro::contadorLibros = 0;

class Biblioteca {
private:
    std::string nombre;
    std::vector<Libro*> librosHeap;
    std::vector<Libro> librosStack;

public:
    Biblioteca(const std::string& _nombre) : nombre(_nombre) {
        std::cout << "Biblioteca '" << nombre << "' creada." << std::endl;
    }
    
    ~Biblioteca() {
        for (Libro* libro : librosHeap) {
            delete libro;
        }
        std::cout << "Biblioteca '" << nombre << "' destruida." << std::endl;
    }
    
    void agregarLibroStack(const Libro& libro) {
        librosStack.push_back(libro);
        std::cout << "Libro añadido al stack en la biblioteca." << std::endl;
    }
    
    void agregarLibroHeap(const std::string& titulo, const std::string& autor, int anio) {
        Libro* nuevoLibro = new Libro(titulo, autor, anio);
        librosHeap.push_back(nuevoLibro);
        std::cout << "Libro añadido al heap en la biblioteca." << std::endl;
    }
    
    void mostrarLibros() const {
        std::cout << "\nLibros en la biblioteca '" << nombre << "':" << std::endl;
        std::cout << "--- Libros en el Stack ---" << std::endl;
        for (const Libro& libro : librosStack) {
            libro.mostrarInfo();
            std::cout << std::endl;
        }
        
        std::cout << "--- Libros en el Heap ---" << std::endl;
        for (const Libro* libro : librosHeap) {
            libro->mostrarInfo();
            std::cout << std::endl;
        }
    }
    
    void prestarLibroHeap(int indice) {
        if (indice >= 0 && indice < librosHeap.size()) {
            Libro* libro = librosHeap[indice];
            libro->prestar();
        } else {
            std::cout << "Índice de libro inválido." << std::endl;
        }
    }
    
    void prestarLibroStack(int indice) {
        if (indice >= 0 && indice < librosStack.size()) {
            Libro& libro = librosStack[indice];
            libro.prestar();
        } else {
            std::cout << "Índice de libro inválido." << std::endl;
        }
    }
};

void depurarEstado(const Biblioteca& biblioteca) {
    std::cout << "\n--- DEPURACIÓN ---" << std::endl;
    std::cout << "Total de libros creados: " << Libro::obtenerContadorLibros() << std::endl;
    biblioteca.mostrarLibros();
    std::cout << "--- FIN DEPURACIÓN ---\n" << std::endl;
}

int main() {
    Biblioteca miBiblioteca("Biblioteca Central");
    
    Libro libro1("Cien años de soledad", "Gabriel García Márquez", 1967);
    Libro libro2("El señor de los anillos", "J.R.R. Tolkien", 1954);
    
    miBiblioteca.agregarLibroStack(libro1);
    miBiblioteca.agregarLibroStack(libro2);
    
    miBiblioteca.agregarLibroHeap("Don Quijote de la Mancha", "Miguel de Cervantes", 1605);
    miBiblioteca.agregarLibroHeap("1984", "George Orwell", 1949);
    
    depurarEstado(miBiblioteca);
    
    std::cout << "Prestando libros:" << std::endl;
    miBiblioteca.prestarLibroStack(0);
    miBiblioteca.prestarLibroHeap(1);
    
    depurarEstado(miBiblioteca);
    
    {
        std::cout << "Bloque de demostración de referencias y punteros:" << std::endl;
        
        Libro& refLibro = libro1;
        refLibro.devolver();
        
        Libro* ptrLibro = &libro2;
        ptrLibro->prestar();
    }
    
    depurarEstado(miBiblioteca);
    
    std::cout << "Programa finalizado. La biblioteca será destruida..." << std::endl;
    return 0;
}

```
El programa permite crear libros, añadirlos a una biblioteca (tanto en stack como en heap), prestarlos, devolverlos y muestra el estado del sistema a través de mensajes de depuración.

Conceptos implementados:

-Clases y objetos
Clase Libro: Representa un libro con sus atributos y métodos
Clase Biblioteca: Gestiona una colección de libros
Creación de objetos de ambas clases en main()


-Paso de parámetros por valor y por referencia
Por valor: comprobarDisponibilidad() - no modifica el objeto
Por referencia: agregarLibroStack(const Libro& libro) - evita copias

-Constructores y destructores
Constructor de Libro que inicializa atributos
Constructor de copia para Libro
Destructores que liberan recursos y muestran mensajes

-Métodos y atributos
Atributos privados: titulo, autor, anioPublicacion, etc.
Métodos como mostrarInfo(), prestar(), devolver()

-Objetos en el stack y en el heap
Stack: Libro libro1(...) - memoria automática
Heap: new Libro(...) - memoria dinámica gestionada con punteros

-Punteros y referencias
Punteros: Libro* nuevoLibro, std::vector<Libro*>
Referencias: const Libro& libro, Libro& refLibro


-Variables estáticas
static int contadorLibros - cuenta todos los libros creados
Método estático obtenerContadorLibros()


Depuración de programas
Función depurarEstado() para mostrar información del sistema
Mensajes de seguimiento durante creación, préstamo y destrucción


# Análisis de memoria - Segmentos de memoria utilizados

| Variable/Objeto | Segmento | Observaciones |
|----------------|----------|---------------|
| `Libro::contadorLibros` | **.data** | Variable estática inicializada |
| `main()::miBiblioteca` | **Stack** | Objeto `Biblioteca` completo |
| `Biblioteca::nombre` | **Stack** | Objeto `string` (buffer interno en heap) |
| `Biblioteca::librosHeap` | **Stack** | Vector (buffer interno en heap) |
| `Biblioteca::librosStack` | **Stack** | Vector (buffer interno en heap) |
| `main()::libro1`, `libro2` | **Stack** | Objetos `Libro` completos |
| `Libro::titulo`, `Libro::autor` | **Stack** | Objetos `string` (buffers internos en heap) |
| `Libro*` en `librosHeap` | **Heap** | Objetos creados con `new` |
| Copias en `librosStack` | **Stack** | Copias de objetos `Libro` |
| `main()::refLibro` | No ocupa memoria | Referencia (solo información para el compilador) |
| `main()::ptrLibro` | **Stack** | Puntero (almacena dirección) |
| Parámetros por referencia | No ocupan memoria adicional | Como `depurarEstado(const Biblioteca&)` |
