#### Actividad 6

* **int *pvar;**
  Declara un puntero llamado pvar que puede almacenar la dirección de memoria de una variable de tipo int. Aún no apunta a nada concreto hasta que se le asigne una dirección válida.

* ** *pvar = var;**
  Desreferencia el puntero pvar (accede a la celda de memoria a la que apunta) y escribe en ella el valor de la variable var. Equivale a “pon en la dirección guardada en pvar el valor de var”.

* **var2 = *pvar;**
  Lee el contenido de la dirección a la que apunta pvar y lo asigna a var2. Es decir, copia en var2 el valor almacenado en la celda señalada por pvar.

* **pvar = &var3;**
  Asigna a pvar la dirección de memoria de la variable var3. Desde ese momento, pvar “apunta” a var3 y cualquier desreferencia (*pvar) accederá al contenido de var3.
