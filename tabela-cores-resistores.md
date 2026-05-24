## Tabela de Código de Cores de Resistores

[DICA DE DIAGRAMAÇÃO: Imprima esta página em A4 e plastifique se possível — é o material de referência que engenheiros usam o tempo todo. Fundo branco, tabela com linhas alternadas de cor suave para facilitar leitura rápida. Cada célula da coluna "Cor" deve ter o fundo da cor correspondente para referência visual imediata.]

Por que resistores têm faixas coloridas? Resistores são componentes muito pequenos — não há espaço físico para imprimir números legíveis em seu corpo. A solução encontrada pela indústria eletrônica foi codificar o valor em faixas de tinta coloridas, visíveis a olho nu mesmo nos componentes mais minúsculos. Este sistema foi padronizado mundialmente pela norma **IEC 60062**, adotada em todos os países e fabricantes, garantindo que um resistor comprado no Brasil, na China ou nos Estados Unidos use exatamente o mesmo código. Todo eletricista, técnico e engenheiro eletrônico precisa dominar esta leitura — ela é o ABC da eletrônica prática.

---

### Como Ler um Resistor de 4 Faixas

Ao pegar um resistor, sempre segure-o com a **faixa dourada ou prateada à direita** — essa é a faixa de tolerância e indica qual extremidade é a "última". As três faixas restantes, lidas da esquerda para a direita, codificam o valor.

```
  ┌────────────────────────────────────────────┐
  │  [1ª Faixa][2ª Faixa][Multiplicador][Tolerância]  │
  │   Dígito 1  Dígito 2      × 10^n           ±%      │
  └────────────────────────────────────────────┘
```

**Fórmula de leitura:**

```
Valor (Ω) = [Faixa1][Faixa2] × [Multiplicador]
```

Ou seja: forme um número de dois dígitos com a 1ª e 2ª faixas, depois multiplique pelo valor da 3ª faixa. A 4ª faixa indica a tolerância — o quanto o valor real pode se afastar do valor nominal.

---

### Tabela Principal de Código de Cores

| Cor      | Dígito | Multiplicador | Tolerância |
|----------|--------|---------------|------------|
| Preto    | 0      | × 1           | —          |
| Marrom   | 1      | × 10          | ± 1%       |
| Vermelho | 2      | × 100         | ± 2%       |
| Laranja  | 3      | × 1.000       | —          |
| Amarelo  | 4      | × 10.000      | —          |
| Verde    | 5      | × 100.000     | ± 0,5%     |
| Azul     | 6      | × 1.000.000   | ± 0,25%    |
| Violeta  | 7      | × 10.000.000  | ± 0,1%     |
| Cinza    | 8      | —             | ± 0,05%    |
| Branco   | 9      | —             | —          |
| Dourado  | —      | × 0,1         | ± 5%       |
| Prateado | —      | × 0,01        | ± 10%      |

---

### Exemplos Práticos com os Resistores do Nosso Projeto

#### Resistor de 220Ω

Este é o resistor que protege o LED no circuito do poste inteligente.

- Faixa 1 (1º dígito): **Vermelho** = 2
- Faixa 2 (2º dígito): **Vermelho** = 2
- Faixa 3 (multiplicador): **Marrom** = × 10
- Faixa 4 (tolerância): **Dourado** = ± 5%
- Cálculo: 22 × 10 = **220Ω** (com tolerância de ± 5%, o valor real está entre 209Ω e 231Ω)

#### Resistor de 10kΩ (10.000Ω)

Este é o resistor que forma o divisor de tensão com o sensor LDR.

- Faixa 1 (1º dígito): **Marrom** = 1
- Faixa 2 (2º dígito): **Preto** = 0
- Faixa 3 (multiplicador): **Laranja** = × 1.000
- Faixa 4 (tolerância): **Dourado** = ± 5%
- Cálculo: 10 × 1.000 = **10.000Ω = 10kΩ** (com tolerância de ± 5%, o valor real está entre 9.500Ω e 10.500Ω)

---

### Valores Comuns de Resistores (Série E24) — Referência Rápida

A **Série E24** é o conjunto de 24 valores padronizados pela norma IEC que os fabricantes produzem comercialmente. Em vez de fabricar resistores em todos os valores possíveis (o que seria inviável), a indústria definiu uma escala logarítmica de 24 valores por década — por exemplo, entre 100Ω e 1kΩ existem exatamente 24 valores padronizados. Isso garante que qualquer resistência necessária em um projeto possa ser obtida com no máximo dois resistores em série ou paralelo. A tabela abaixo lista os valores mais encontrados em projetos com Arduino:

| Valor  | Notação | Uso Típico em Arduino                        |
|--------|---------|----------------------------------------------|
| 100Ω   | 100R    | LEDs de alto brilho                          |
| 220Ω   | 220R    | LEDs padrão (usado neste projeto)            |
| 330Ω   | 330R    | LEDs com menor brilho, proteção de pinos     |
| 470Ω   | 470R    | Divisores de tensão, LEDs dimmer             |
| 1kΩ    | 1K      | Pull-up/pull-down para botões                |
| 2.2kΩ  | 2K2     | Divisores de tensão                          |
| 4.7kΩ  | 4K7     | Comunicação I2C (SDA/SCL)                    |
| 10kΩ   | 10K     | Sensor LDR divisor de tensão (neste projeto) |
| 22kΩ   | 22K     | Filtros e divisores de tensão                |
| 47kΩ   | 47K     | Sensores analógicos                          |
| 100kΩ  | 100K    | Entradas de alta impedância                  |

---

[DICA DE DIAGRAMAÇÃO: Imprimir em A4 retrato, plastificar e manter na bancada de trabalho. Considere adicionar uma régua de cores físicas ao lado da tabela para facilitar a identificação visual imediata.]
