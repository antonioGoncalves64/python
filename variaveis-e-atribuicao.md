# Variáveis e atribuição

## Introdução

Um dos aspectos importantes em programação corresponde à possibilidade de usar variáveis para designar entidades computacionais. A utilização de variáveis corresponde a um nível de abstracção no qual deixamos de nos preocupar com a indicação directa da entidade , referindo-nos a essa entidade pelo variável. 

{% hint style="info" %}
Uma variável Começam com uma **letra**, seguido de **letras**, **números** ou **sublinhado,** mas não podem ser **palavras reservadas.**
{% endhint %}

| Palavra reservadas | Palavra reservadas | Palavra reservadas | Palavra reservadas |
| :--- | :--- | :--- | :--- |
| `False` | `def` | `if` | `raise` |
| `None` | `del` | `import` | `return` |
| `True` | `elif` | `in` | `try` |
| `and` | `else` | `is` | `while` |
| `as` | `except` | `lambda` | `with` |
| `assert` | `finally` | `nonlocal` | `yield` |
| `break` | `for` | `not` |  |
| `class` | `from` | `or` |  |
| `continue` | `global` | `pass` |  |

```sql
#exemplos de variáveis válidas 
nome idade Preço_Max área2

```

{% hint style="warning" %}
Exemplos de nomes que **não podemos usar:**  
76trombones            more$          lambda
{% endhint %}

A associação entre um variável e um valor é realizada através da **instrução de atribuição.** A instrução de atribuição recorre ao operador de **atribuição =.** Este operador recebe dois operandos, o primeiro corresponde a variável  que queremos usar para nomear o valor resultante da avaliação do segundo operando, o qual é uma expressão.  Em notação **BNF**,  instrução de atribuição é definida do seguinte modo:

```sql
<instrucao de atribuicao> ::= <variavel> = <expressao> | 
                              <variavel>,<instrucao de atribuicao>,<expressao>
```

## **Atribuição simples**

Ao encontrar a instrução **&lt;variável&gt; = &lt;expressao&gt;,** o **Python** começa por avaliar a **&lt;expressao&gt;**  após o que associa **&lt;variável&gt;** ao valor da **&lt;expressao&gt;**. A execução de uma instrução de atribuição não devolve nenhum valor, mas sim altera o valor de uma variável.

```sql
>>> raio = 17
>>> raio
17
```

Na primeira linha surge uma instrução de atribuição. Ao executar esta instrução, o **Python** avalia a expressao 17 \(uma constante\) e atribui o seu valor à variável raio. A partir deste momento, o **Python** passa a “conhecer” o nome, raio, o qual tem o valor 17.

O exemplo em seguida apresentado mostra o carácter dinâmico da operacao de atribuição: 

```sql
>>> raio = raio + 1
>>> raio
18
```

Em primeiro lugar, a expressão  a direita do simbolo **=** é avaliada e, em segundo lugar, o valor resultante é atribuído a varável à esquerda deste simbolo.

{% hint style="info" %}
A instrução de atribuição **raio = raio + 1** tem o efeito de atribuir à variável **raio** o valor anterior de raio mais um.
{% endhint %}

{% hint style="info" %}
Isto mostra que uma operacao de atribuição nao é uma equação matemática, mas sim um processo de atribuir o valor da expressao a direita do operador de atribuição a variavel à sua esquerda.
{% endhint %}

Na seguinte interacção com o Python tentamos atribuir o valor 20 ao nome **del.**

```sql
>>> del = 20
Syntax Error: del = 20: <string>, line 1
```

O **Python** reage com um erro porque **del** o corresponde a um nome reservado do **Python.**

Consideremos agora a seguinte interacção:

```sql
>>> a = 10
>>> b = 15.5
>>> temp = a
>>> a = b
>>> b = temp
>>> a
15.5
>>> b
10
```

{% hint style="info" %}
A interação tem o efeito de trocar os valores das variáveis **a** e **b.**
{% endhint %}

## **Atribuição múltipla**

Ao encontrar ****uma instrucao da forma:

####  &lt;variavel1&gt;, &lt;variavel2&gt;,  ... &lt;variaveln&gt; =  &lt;exp1&gt;, &lt;exp2&gt;, ..., &lt;expn&gt;

o Python comeca por avaliar as expressoes &lt;exp1&gt;, &lt;exp2&gt;, ..., &lt;expn&gt; apos o que associa &lt;variavel1&gt; a ao valor da &lt;exp1&gt; e assim por diante. O exemplo em seguida apresentado mostra na seguinte interacção.

```sql
>>> nota_exame1, nota_exame2, nota_exame3 = 16, 15, 18
>>>
>>> nota_exame1
16

>>> nota_exame2
15

>>> nota_exame3
18
```

Consideremos agora a seguinte interacção:

```sql
>>> nota_exame1, nota_exame2 = 16, nota_exame1 +1
>>>NameError: name ’nota_exame1’ is not defined
```

Consideremos agora a seguinte interacção:

```sql
>>> a = 10
>>> b = 15.7
>>> a, b = b, a
>>> a
15.5
>>> b
10
```

{% hint style="info" %}
 instrução  **a, b = b, a** tem o efeito de trocar os valores das variáveis **a** e **b.**
{% endhint %}

## Predicados e condições

Uma operação que produz resultados do tipo lógico chama-se um **predicado**. Uma expressão cujo valor é do tipo lógico chama-se uma **condição**. As condições podem ser combinadas através de operações lógicas.

A seguinte interacção apresenta o uso de  predicados:

```sql
>>> a = 10
>>> b = 20

>>> a == b
False

>>> a = 30
>>> b = 30

>>> a == b
True

>>> a <= b
True

>>> a >= b
True
```

A seguinte interacçãoapresenta o uso de  condições:

```sql
>>> a = 3
>>> b = 1
>>> (b / a) > 0
True

>>> nota = 17
>>> 3 < nota % 2
False

>>> 3 < nota // 2
True
```

## Exercícios práticos

1. Crie um programa para converter graus ºC em ºF . Nota: F=\(9.C\)/5+32 .
2. Calcular e apresentar o valor do volume de uma lata de bebida.Utilize a fórmula: volume = 3.14159 \* raio2 \* altura.
3. Crie um programa que dados dois valores, divide o primeiro pelo segundo. Note que não é possível fazer a divisão por zero, neste caso deve ser apresentada a mensa- gem adequada.
4. Escreva um programa  para calcular o valor de y como função de x, segundo a função y\(x\) = 3x + 2, num domínio real.
5. Calcule a média de três números inteiros dados.
6. a partir da quantidade de chuva dada em polegadas clacule o equivalente em milímetros \(25,4 mm = 1 polegada\).
7. Escreva um programa que realize a conversão de toneladas para quilos e gramas.
8. Escreva um programa que armazene em variáveis dois inteiros e apresente o resultado da realização das operações aritméticas tradicionais.
9. Escreva um programa que armazene numa variável um número real e escreva a sua parte inteira e fraccionária.
10. Escreva um programa que armazene o valor 10 em uma variável A e o valor 20 em uma variável B. A seguir \(utilizando apenas atribuições entre variáveis\) troque os seus conteúdos fazendo com que o valor que está em A passe para B e vice-versa. Ao final, escrever os valores que ficaram armazenados nas variáveis.
11. Escreva um programa que a partir das dimensões de um retângulo \(base e altura\), calcular e escrever a área do retângulo.

## Exercícios laboratoriais

1. Crie um programa que a partir de duas variáveis A e B, efetuar a troca dos valores de forma a variável A passe a ter o valor de B, e que a variável B passe a ter o valor de A.
2. Crie um programa para converter graus ºF em ºC. Nota: C=5/9.\(F-32\)
3. Escreva um programa que declare uma variável inteira e uma variável caracter, atribua-lhes os valores 5 e ‘a’, imprimindo-as na saída.
4. O Banco ESE abriu uma linha de crédito. O valor máximo da prestação não poderá ultrapassar 35% do salário líquido. Fazer um programa  que permita entrando o valor do salário líquido determinar o valor máximo que a prestação poderá ter.
5. Escreva um programa  para calcular o valor de y como função de x, segundo a função y\(x\) = 4\*x\*x + 2\*x + 1, num domínio inteiro.
6. Escreva um programa para calcular o consumo médio de um automóvel \(medido em Km/l\), dado que são conhecidos a distância total percorrida e o volume de combustível consumido para percorrê-la \(medido em litros\).
7. Calcule a média de quatro números inteiros dados.
8. Calcule o quadrado de um número, ou seja, o produto de um número por si mesmo
9. O custo ao consumidor de um carro novo é a soma do custo de fábrica com a % do distribuidor e dos impostos, ambos aplicados ao custo de fábrica. Supondo que a % do distribuidor seja de 12% e a dos impostos de 45%, prepare um programa a aprtir do custo de fábrica do carro calcule o custo ao consumidor.
10. Faça um programa que a partir da idade de uma pessoa expressa em anos, meses e dias  calcule a idade dessa pessoa expressa apenas em dias. Considerar ano com 365 dias e mês com 30 dias
11. Escreva um programa que a partir do número total de eleitores de um município, o número de votos brancos, nulos e válidos calcule  a % que cada um representa em relação ao total de eleitores.
12. Escreva um programa paque a partir do  salário mensal atual de um funcionário e a %  de reajuste. Calcular e apresente o valor do novo salário.

