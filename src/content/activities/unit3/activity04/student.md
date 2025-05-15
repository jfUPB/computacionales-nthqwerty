#### Actividad 4

El programa falla porque intenta modificar la memoria donde está ubicada la función main(). Esta función se encuentra en el segmento de código, que está protegido para evitar escrituras. Esa área de memoria es solo de lectura y ejecución, con el fin de impedir cambios mientras el programa corre. Por eso, intentar sobrescribirla provoca un error de protección de memoria, como un fallo de segmentación o una violación de acceso.

Cuando se intenta modificar el contenido de una constante global, también ocurre un error. Esto pasa porque mensaje_ro apunta a una cadena almacenada en una zona de memoria de solo lectura. El sistema operativo protege esta área para evitar cambios durante la ejecución, y cualquier intento de modificarla puede causar un fallo de segmentación o un comportamiento inesperado, dependiendo del sistema donde se ejecute.
