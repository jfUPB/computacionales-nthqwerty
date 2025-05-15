#### Actividad 9

En esta plataforma, cada instrucción ocupa 16 bits y se clasifica en dos grupos principales. Las **instrucciones A** empiezan con un 0 y emplean los 15 bits restantes para señalar directamente una dirección de la memoria. Por su parte, las **instrucciones C** arrancan con 111 y dividen el resto de los bits en tres secciones: el destino del resultado (dest), la operación a realizar (comp) y la condición de salto (jump).

Para calcular cuántas entradas necesita el arreglo SCREEN, partimos de que la pantalla mide 512×256 píxeles, es decir, 131 072 píxeles en total. Dado que cada posición de SCREEN cubre 16 de esos píxeles, basta dividir 131 072 entre 16, lo que nos da 8 192 celdas. Así, el array SCREEN se declara con 8 192 elementos.

```csharp
using System;
class HelloWorld {
  static void Main() {
    int Screen = new int [8192];
    Act_pos = 0;
    int KBD = 0;
    while(true){
      if(KBD !=0){
        Screen[Act_pos] = 1;
        if(Act_pos <= 8192)
        Act_pos++;

        }
        else if (KBD ==0 ){
        Screen[Act_pos] = -1;
        if(Act_pos >= 0)
        Act_pos=Act_pos - 1;
        }
    }

  }
}
```
