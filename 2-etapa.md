### 2º Etapa

Contruir um Banco de Registradores para funcionar em conjunto com o a [ULA](/1-etapa.md).

#### Flip-Flop

- Tipos: `RS` `JK` `D` `T`
- Variações: `Mestre` `Escravo`
- Sensibilidades: `NIU+` `NIU-` `BS` `BD`
- Adições: `Entradas Assíncronas`

#### Flip-Flop D

- Esquema

![Flip-Flop D](http://image.slidesharecdn.com/dcsppt-150919142146-lva1-app6892/95/d-flip-flop-7-638.jpg?cb=1442672591)

- Linha do Tempo

![Linha do Tempo](http://www.gmcon.net/cirlog/img6/conten14.gif)

- Observações 
  - Sensível à borda positiva: reproduz a entrada para saída no clock `1`
  - Sensível à borda negativa: reproduz a entrada para saída no clock `0`
  - Sensível à nível positivo: reproduz a entrada na saída enquanto clock `1`
  - Sensível à nível negativo: reproduz a entrada na saída enquanto clock `0`
