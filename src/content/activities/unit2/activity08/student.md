#### Actividad 8

 Binario          | Descripción reinterpretada                                       
 -----------------| ---------------------------------------------------------------- 
 0100000000000000 | Carga 0 en el registro A (apunta a la celda 0 de RAM).           
 1110110000010000 | Incrementa en 1 el contenido de la celda apuntada por A.         
 0000000000010000 | Carga 16 en el registro A (apunta a RAM\[16]).                   
 1110001100001000 | Resta el valor de RAM\[A] al registro D y descarta el resultado. 
 0110000000000000 | Pone a cero el registro D.                                       
 1111110000010000 | Copia el contenido de D al acumulador.                           
 0000000000010011 | Carga 19 en el registro A (apunta a RAM\[19]).                   
 1110001100000101 | Suma D más RAM\[A] y desecha el resultado.                       
 0000000000010000 | Vuelve a apuntar A a la dirección 16.                            
 1111110000010000 | Vuelve a cargar el acumulador con el valor de D.                 
 0100000000000000 | Apunta A otra vez a la dirección 0.                              
 1110010011010000 | Realiza un AND bit a bit entre D y RAM\[A], guarda en D.         
 0000000000000100 | Carga 4 en el registro A (apunta a RAM\[4]).                     
 1110001100000110 | Resta RAM\[A] a D y descarta el resultado.                       
 0000000000010000 | Apunta de nuevo a RAM\[16].                                      
 1111110010101000 | Transfiere D al acumulador.                                      
 1110101010001000 | Salto incondicional al inicio del programa.                      
 0000000000000100 | Vuelve a fijar A en 4.                                           
 1110101010000111 | Salta al ciclo principal si no se cumple cierta condición.       
 0000000000010000 | Apunta otra vez a la dirección 16.                               
 1111110000010000 | Carga el valor de D en el acumulador.                            
 0110000000000000 | Reinicia D a 0.                                                  
 1110010011010000 | AND lógico entre D y RAM\[A], resultado en D.                    
 0000000000000100 | Establece A en 4.                                                
 1110001100000011 | Resta RAM\[A] a D y descarta el resultado.                       
 0000000000010000 | Señala de nuevo la celda 16 con A.                               
 1111110000100000 | Copia D en el acumulador.                                        
 1110111010001000 | Suma D con RAM\[A] y guarda (sin condiciones).                   
 0000000000010000 | Restablece A en 16.                                              
 1111110111001000 | Incrementa en 1 el contenido de RAM\[A] (RAM\[16]++).            
 0000000000000100 | Ajusta A para que apunte a la celda 4.                           
 1110101010000111 | Salta de nuevo al punto de control si la condición persiste.     
