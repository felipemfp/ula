### 4º Etapa

Realizar fatorial.

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
	(0, 0, 0, 0, 0), 		# 00. faz nada
	(SUB, 0, 0, 0, 0), 		# 01. zera o $0 (zero)
	(SUB, 1, 1, 1, 0), 		# 02. zera o $1 (valor)
	(SUB, 2, 2, 2, 0), 		# 03. zera o $2 (resultado)
	(SUB, 3, 3, 3, 0), 		# 04. zera o $3 (atual)
	(SUB, 4, 4, 4, 0), 		# 05. zera o $4 (contador)
	(SUMI, 1, 0, 0, 5), 	# 06. colocar IMM (5) no $1
	(SUM, 3, 1, 0, 1), 		# 07. colocar $1 no $3
	(SUBI, 3, 3, 0, 1), 	# 08. reduzir 1 do $3
	(BEQ, 20, 3, 2, 4), 	# 09. verificar se $3 é igual a $4, entao pular 4 enderecos
	(SUM, 2, 2, 1, 0),		# 10. somar $2 com $1
	(SUMI, 4, 4, 0, 1), 	# 11. somar $4 com 1
	(JUMP, 20, 0, 0, 10), 	# 12. voltar para 9
	(SUB, 4, 4, 4, 0), 		# 13. zerar $4
	(SUBI, 3, 3, 0, 1), 	# 14. reduzir 1 do $3
	(SUBI, 1, 1, 0, 1), 	# 15. reduzir 1 do $1
	(BNQ, 20, 3, 0, 2), 	# 16. verificar se $3 é diferente de $0, entao pular 2 enderecos
	(JUMP, 20, 0, 0, 18),   # 17. voltar para 17
	(JUMP, 20, 0, 0, 10)	# 18. voltar para 9
]

for y in x:
	b = '{:05b}{:05b}{:05b}{:05b}{:012b}'.format(*y)
	print('{:08x}'.format(int(b, 2)))


print('Expected Rx:', '{:032b}'.format(120))

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
