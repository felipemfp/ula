### 4º Etapa

Realizar fatorial.

```
registrador $0 = 0
registrador $1 = resultado
registrador $2 = atual
registrador $3 = contador

1. pegar n do IMM e colocar no $1 (SUMI, 1, 0, 0, 5)
2. pegar $1 e diminuir 1 e colocar no $2 (SUBI, 2, 1, 0, 1)
3. verificar se $3 é igual a $2, pular para endereco 6 (BEQ, 10, 2, 3, 6)
4. somar $1 com $2 e colocar no $1 (SUM, 1, 1, 2, 0)
5. somar $3 com 1 (SUMI, 3, 3, 0, 1)
5. pular para endereco 3 (JUMP, 10, 0, 0, 3)
6. zerar $3 (SUB, 3, 3, 3, 0)
7. diminuir 1 do $2 (SUBI, 2, 2, 0, 1)
8. verificar se $2 é diferente de $0, pular para endereco 3 (BNQ, 10, 2, 0, 3)
9. pular para endereco 9 (JUMP, 10, 1, 0, 9)

```

```python
SUM = 5
SUMI = 21
SUB = 6
SUBI = 22
BEQ = 14
BNQ = 15
JUMP = 13

x = [
	(SUMI, 1, 0, 0, 5),
	(SUBI, 2, 1, 0, 1),
	(BEQ, 10, 2, 3, 6),
	(SUM, 1, 1, 2, 0),
	(SUMI, 3, 3, 0, 1),
	(JUMP, 10, 0, 0, 3),
	(SUB, 3, 3, 3, 0),
	(SUBI, 2, 2, 0, 1),
	(BNQ, 10, 2, 0, 3),
	(JUMP, 10, 1, 0, 9)
]

for y in x:
	b = '{:05b}{:05b}{:05b}{:05b}{:012b}'.format(*y)
	print('{:x}'.format(int(b, 2)))

```
