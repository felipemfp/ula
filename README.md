Construa uma `ULA` que permita a implatação de 32 operações. As 2 entradas da `ULA` são dados de 32 bits (cada entrada).

O projeto final deve ser um subcircuito.

```
      
a ⊡— │‾‾\  —⊙ S
      >  │  —⊙ overflow
b ⊡— │__/  —⊙ zero
       └── Sel
```

Seleção | Operação
------- | --------
00000 | AND :white_check_mark:
00001 | OR :white_check_mark:
00010 | NAND :white_check_mark:
00011 | XOR :white_check_mark:
00100 | Soma (Inteiros) :white_check_mark:
00101 | Soma (Naturais) :white_check_mark:
00110 | Subtração (Naturais) :white_check_mark:
00111 | Deslocamento para Esquerda :white_check_mark:
01000 | Deslocamento para Direita :white_check_mark:
01001 | Deslocamento para Direita c/ Sinal :white_check_mark:
01010 |
01011 |
01100 |
01101 |
01111 |
10000 |
10001 |
10010 |
10011 |
10100 |
10101 |
10110 |
10111 |
11000 |
11001 |
11010 |
11011 |
11100 |
11101 |
11110 |
11111 |
