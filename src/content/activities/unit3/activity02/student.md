#### Actividad 2

``` cpp
#include <iostream>

using namespace std;

// Esta función intenta intercambiar dos valores pasados por valor (no afecta las variables originales)
void modificarPorValor(int a , int b) {
    int t = a;   // Guarda temporalmente el valor de 'a'
    a = b;       // Asigna el valor de 'b' a 'a'
    b = t;       // Asigna el valor temporal (original de 'a') a 'b'
}

// Esta función intercambia los valores reales de las variables usando referencias
void modificarPorReferencia(int& a, int& b) {
    int t = a;   // Guarda temporalmente el valor de 'a'
    a = b;       // Asigna el valor de 'b' a 'a'
    b = t;       // Asigna el valor temporal (original de 'a') a 'b'
}

// Esta función intenta intercambiar los valores usando punteros, pero solo intercambia los punteros locales
void modificarPorPuntero(int* a , int* b) {
    int* t = a;  // Guarda temporalmente la dirección de 'a'
    a = b;       // Apunta 'a' a lo que apunta 'b'
    b = t;       // Apunta 'b' a lo que originalmente apuntaba 'a'
}

int main() {
    int a = 1;
    int b = 2;

    cout << "Valor inicial de a (paso por valor): " << a << endl;
    cout << "Valor inicial de b (paso por referencia): " << b << endl;

    cout << "\nLlamando a modificarPorValor(a, b)..." << endl;
    modificarPorValor(a, b);
    cout << "Después de modificarPorValor, valor de a: " << a  << " y valor de b: " << b << endl;

    cout << "\nLlamando a modificarPorReferencia(a, b)..." << endl;
    modificarPorReferencia(a, b);
    cout << "Después de modificarPorReferencia, valor de a: " << a << " y valor de b: " << b << endl;

    cout << "\nLlamando a modificarPorPuntero(&a, &b)..." << endl;
    modificarPorPuntero(&a, &b);
    cout << "Después de modificarPorPuntero, valor de a: " << a << " y valor de b: " << b << endl;

    return 0;
}
```
