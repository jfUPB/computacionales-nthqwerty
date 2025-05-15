#### Actividad 10

```asm
@16384
D=A
@16
M=D

@24576
D=M
@8
M=A
@12
0;JMP

@4
0;JMP


@8
A=M
@98
D=D-A
@24
D;JEQ
@14
D=D-A
@35
D;JEQ
@10
0;JMP


@16
D=M
@16384
D=D-A
@20
D;JLE


@16
AM=M-1
M=0
@20
0;JMP

@16
D=M
@24576
D=D-A
@20
D;JGE


@16
A=M
M=-1
@16
M=M+1
@20
0;JMP****
```
