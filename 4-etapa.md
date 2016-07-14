### 4º Etapa

Realizar fatorial.

#### Lógica

```
registrador $0 = 0
registrador $1 = resultado
registrador $2 = atual
registrador $3 = contador

0. (0, 0, 0, 0, 0)
1. zerar $0 (SUB, 0, 0, 0, 0)
2. zerar $1 (SUB, 1, 1, 1, 0)
3. zerar $2 (SUB, 2, 2, 2, 0)
4. zerar $3 (SUB, 3, 3, 3, 0)
5. pegar n do IMM e colocar no $1 (SUMI, 1, 0, 0, 5)
6. pegar $1 e diminuir 1 e colocar no $2 (SUBI, 2, 1, 0, 1)
7. verificar se $3 é igual a $2, pular para endereco 11 (BEQ, 16, 2, 3, 4)
8. somar $1 com $2 e colocar no $1 (SUM, 1, 1, 2, 0)
9. somar $3 com 1 (SUMI, 3, 3, 0, 1)
10. pular para endereco 7 (JUMP, 16, 0, 0, 7)
11. zerar $3 (SUB, 3, 3, 3, 0)
12. diminuir 1 do $2 (SUBI, 2, 2, 0, 1)
13. verificar se $2 é diferente de $0, pular para endereco 15 (BNQ, 16, 2, 0, 2)
14. pular para endereco 11 (JUMP, 16, 1, 0, 14)
15. pular para endereco 7 (JUMP, 16, 1, 0, 7)

```

#### Script para gerar comandos

```python
SUM = 5
SUMI = 21
SUB = 6
SUBI = 22
BEQ = 13
BNQ = 14
JUMP = 31

x = [
	(0, 0, 0, 0, 0), 
	(SUB, 0, 0, 0, 0), 
	(SUB, 1, 1, 1, 0), 
	(SUB, 2, 2, 2, 0), 
	(SUB, 3, 3, 3, 0),
	(SUMI, 1, 0, 0, 5), 
	(SUBI, 2, 1, 0, 1), 
	(BEQ, 16, 2, 3, 4), 
	(SUM, 1, 1, 2, 0),
	(SUMI, 3, 3, 0, 1), 
	(JUMP, 16, 0, 0, 7), 
	(SUB, 3, 3, 3, 0), 
	(SUBI, 2, 2, 0, 1), 
	(BNQ, 16, 2, 0, 2), 
	(JUMP, 16, 1, 0, 14),
	(JUMP, 16, 1, 0, 7)
]

for y in x:
	b = '{:05b}{:05b}{:05b}{:05b}{:012b}'.format(*y)
	print('{:08x}'.format(int(b, 2)))


print('Expected Rx:', '{:b}'.format(120))

```

#### Comandos

```
00000000
30000000
30421000
30842000
30c63000
a8400005
b0820001
6c043004
28422000
a8c60001
fc000007
30c63000
b0840001
74040002
fc02000e
fc020007
```
