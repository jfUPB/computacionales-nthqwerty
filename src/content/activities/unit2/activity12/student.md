#### Actividad 12

### **1. Condicionales**

**C#:**

```csharp
if (x > 10) {
    y = 1;
} else {
    y = 0;
}
```

**Hack:**

```asm
@x
D=M       // D = x
@10
D=D-A     // D = x - 10
@ELSE
D;JLE     // Si x <= 10 salta a ELSE
@1
D=A
@y
M=D       // y = 1
@END
0;JMP
(ELSE)
@0
D=A
@y
M=D       // y = 0
(END)
```

---

### **2. Ciclo While**

**C#:**

```csharp
while (i < 10) {
    sum = sum + i;
    i++;
}
```

**Hack:**

```asm
(LOOP)
@i
D=M
@10
D=D-A
@END
D;JGE    // Si i >= 10, salta a END

@i
D=M
@sum
M=D+M    // sum += i

@i
M=M+1    // i++

@LOOP
0;JMP
(END)
```

---

### **3. Ciclo For**

**C#:**

```csharp
for (int i = 0; i < 10; i++) {
    sum += i;
}
```

**Hack:** (similar al while anterior, pero incluye inicialización)

```asm
@0
D=A
@i
M=D       // i = 0
@0
D=A
@sum
M=D       // sum = 0

(LOOP)
@i
D=M
@10
D=D-A
@END
D;JGE     // Si i >= 10, termina

@i
D=M
@sum
M=D+M     // sum += i

@i
M=M+1     // i++

@LOOP
0;JMP
(END)
```

---

### **4. Escritura con Punteros**

**C#:**

```csharp
*p = 20;
```

**Hack:** (simulación, p contiene dirección)

```asm
@p
A=M     // A = dirección apuntada por p
@20
D=A
M=D     // *p = 20
```

---

### **5. Lectura con Punteros**

**C#:**

```csharp
x = *p;
```

**Hack:**

```asm
@p
A=M
D=M     // D = *p
@x
M=D     // x = *p
```

---

### **6. Manipulación de un Arreglo con Punteros**

**C#:**

```csharp
*(arr + i) = 5;
```

**Hack:**

```asm
@arr
D=M       // D = arr base
@i
A=D+M     // A = arr + i
@5
D=A
M=D       // *(arr + i) = 5
```

> \*Nota: El lenguaje Hack no permite directamente `A=D+M`, este es un concepto idealizado para fines didácticos. En la práctica, se hace en pasos.

---

### **7. Llamado a Funciones con Parámetros**

**C#:**

```csharp
int result = add(3, 5);
```

**Hack (simulado):**

```asm
@3
D=A
@arg1
M=D
@5
D=A
@arg2
M=D

// Simula función add:
@arg1
D=M
@arg2
D=D+M
@result
M=D
```

---

### **8. Llamado a Función con Retorno**

**C#:**

```csharp
int square(int x) {
  return x * x;
}
int y = square(4);
```

**Hack (simulado):**

```asm
@4
D=A
@x
M=D

// Función square
@x
D=M
D=D*M    // (Hack no soporta multiplicación, es pseudocódigo)
@y
M=D
```

---

¿Te gustaría que arme esto como un documento o presentación organizada también?
