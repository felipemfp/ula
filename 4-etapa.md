### 4º Etapa

Realizar fatorial.

#### Lógica

```
registrador $0 = 0
registrador $1 = resultado
registrador $2 = atual
registrador $3 = contador

1. pegar n do IMM e colocar no $1 (SUMI, 1, 0, 0, 5)
2. pegar $1 e diminuir 1 e colocar no $2 (SUBI, 2, 1, 0, 1)
3. verificar se $3 é igual a $2, pular para endereco 6 (BEQ, 12, 2, 3, 4)
4. somar $1 com $2 e colocar no $1 (SUM, 1, 1, 2, 0)
5. somar $3 com 1 (SUMI, 3, 3, 0, 1)
6. pular para endereco 3 (JUMP, 12, 0, 0, 3)
7. zerar $3 (SUB, 3, 3, 3, 0)
8. diminuir 1 do $2 (SUBI, 2, 2, 0, 1)
9. verificar se $2 é diferente de $0, pular para endereco 3 (BNQ, 12, 2, 0, 2)
10. pular para endereco 11 (JUMP, 12, 1, 0, 10)
11. pular para endereco 3 (JUMP, 12, 1, 0, 3)

```

#### Script para gerar comandos

```python
SUM = 5
SUMI = 21
SUB = 6
SUBI = 22
BEQ = 29
BNQ = 30
JUMP = 31

x = [
	(SUMI, 1, 0, 0, 5),
	(SUBI, 2, 1, 0, 1),
	(BEQ, 12, 2, 3, 4),
	(SUM, 1, 1, 2, 0),
	(SUMI, 3, 3, 0, 1),
	(JUMP, 12, 0, 0, 3),
	(SUB, 3, 3, 3, 0),
	(SUBI, 2, 2, 0, 1),
	(BNQ, 12, 2, 0, 2),
	(JUMP, 12, 1, 0, 10),
	(JUMP, 12, 1, 0, 3)
]

for y in x:
	b = '{:05b}{:05b}{:05b}{:05b}{:012b}'.format(*y)
	print('{:x}'.format(int(b, 2)))

```

#### Comandos

```
a8400005
b0820001
eb043004
28422000
a8c60001
fb000003
30c63000
b0840001
f3040002
fb02000a
fb020003
```
