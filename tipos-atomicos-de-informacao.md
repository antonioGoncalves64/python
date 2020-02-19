# Tipos atómicos de informação

## Introdução

Os tipos de informação disponíveis variam de linguagem de programação para linguagem de programação. De um modo geral, podemos dizer que os tipos de informação se podem dividir em dois grandes grupos: **os tipos atómicos** ou **elementares** e os tipos estruturados. 

Os tipos atómicos são caracterizados pelo facto de as suas constantes \(os elementos do tipo\) serem tomadas como indecomponıveis. Como exemplo de um tipo elementar podemos mencionar o tipo lógico, que possui duas constantes, “**verdadeiro**” e “**falso**”. 

Em contraste, os **tipos estruturados** são caracterizados pelo facto de as suas constantes serem constituídas por um agregado de valores do tipo atómico e ou estruturados.

Em **Python**, como tipos elementares, existem, entre outros, o **tipo inteiro**, o **tipo real** e o **tipo lógico**.

## O tipo inteiro

Os números inteiros, em Python designados por **int** são números sem parte decimal, podendo ser positivos, negativos ou zero. Sobre expressões de tipo inteiro podemos realizar as operações apresentadas de seguida:

```sql
>>> -12
-12

>>> 7 + 2
9

>>> 7 - 2 
5

>>> 7 * 2
14

>>> 7 // 2
3

>>> 7 % 2
1

>>> 5 * (7 // 2)
15

>>> abs(-3)
3
```

Exemplos de expressões compostas com inteiros

```sql
#Exemplos de avaliação de expressões compostas
>>> 123123123123123123123123123123123123123123123123 + 1
123123123123123123123123123123123123123123123124

>>> (20 + 4) * 10
240

>>> 2 * 3 ** 4 * 5
810

>>> 2 * 3 ** (4 * 5)
6973568802
```

| Prefix | interpretação | Base |
| :--- | :--- | :--- |
| `0b` \(zero + lowercase letter `'b'`\) `0B` \(zero + uppercase letter `'B'`\) | Binário | 2 |
| `0o` \(zero + lowercase letter `'o'`\) `0O` \(zero + uppercase letter `'O'`\) | Octal | 8 |
| `0x` \(zero + lowercase letter `'x'`\) `0X` \(zero + uppercase letter `'X'`\) | Hexadecimal | 16 |

Por exemplo:

```sql

>>> 0o10
8

>>> 0x10
16

>>> 0b10
2
```

No interpretador podemos usar type\(...\) para obter o tipo do resultado duma expressão

```sql
>> type(10)
<class 'int'>

>>> type(0o10)
<class 'int'>

>>> type(0x10)
<class 'int'>

>>> type((1+2+3)*5-1)
<class 'int'>
```

## O tipo real

Os números reais, em **Python** designados por float, são números com parte decimal. Em **Python** existem dois métodos para a representação das constantes do tipo real, a notação decimal e a notação científica.

Na notação decimal, em que se representa o numero, com ou sem sinal, por uma parte inteira, um ponto \(correspondente à vírgula\), e uma parte decimal.

A notação científica em que se representa o numero, com ou sem sinal, através de uma mantissa \(que pode ser inteira ou real\) e de uma potencia inteira de dez \(o expoente\) que multiplicada pela mantissa produz o numero.

```sql
>>> 7.7
7.7

>>> 7.
7.0

>>> .4
0.4

>>> 200000000000000000000000000000000000.
2e+35

>>> .00000000000000000000000000000000000000000000000000001
1e-53
```

Notemos que existem operações aparentemente em comum entre os números inteiros e os números reais, por exemplo, a adição + e a multiplicação \*. Dentro do computador, os números inteiros e os números reais são representados de modos diferentes. Ou seja, o inteiro 1 e o real 1.0 não correspondem, dentro do computador, à mesma entidade computacional.

{% hint style="info" %}
Quando isto acontece, ou seja, quando a mesma representação externa de uma operação está associada a mais do que uma operação dentro do computador, diz-se que a operação está **sobrecarregada**.
{% endhint %}

Quando o **Python** tem de aplicar uma operação sobrecarregada, determina o tipo de cada um dos operandos. Se ambos forem inteiros, aplica a operação + dos inteiros se ambos forem reais, aplica a operação + dos reais, se um for inteiro e o outro real, converte o numero inteiro para o real correspondente e aplica a operação + dos reais

{% hint style="info" %}
Esta conversão tem o nome de **coerção**, sendo demonstrada na seguinte interacção:
{% endhint %}

```sql
>>> 2 + 3.5
5.5

>>> 7.8 * 10
78.0

# python converte ambos os números Inteiros para Reais 
>>> 1 / 3 
0.3333333333333333
```

O **Python** fornece também operações **embutidas** que transformam números reais em inteiros e vice-versa. A seguinte interacção mostra a utilização destas operações:

```sql
>>> round(3.3)
3

>>> round(3.6)
4

>>> int(3.9)
3

>>> float(3)
3.0
```

Tal como com os inteiros no interpretador podemos usar _**type\(...\)**_ para obter o tipo do resultado duma expressão com reais

```sql
>>> 4.2
4.2

>>> type(4.2)
<class 'float'>

>>> 4.
4.0

>>> .2
0.2

>>> .4e7
4000000.0

>>> type(.4e7)
<class 'float'>

>>> 4.2e-4
0.00042
```

## O tipo lógico

O tipo lógico, em Python designado por bool, apenas pode assumir dois valores, True \(verdadeiro\) e False \(falso\). As operações que se podem efectuar sobre valores lógicos, produzindo valores lógicos, são de dois tipos, as operações unárias e as operações binarias.

As operações unárias produzem um valor lógico a partir de um valor lógico. Existe uma operação unária em Python, not. A operação not muda o valor lógico. Assim, not\(True\) tem o valor False e not\(False\) tem o valor True.

As operações binarias aceitam dois argumentos do tipo lógico e produzem um valor do tipo lógico. Entre estas operações encontram-se as operações  correspondentes à conjunção e à disjunção. A conjunção, representada por and, tem o valor True apenas se ambos os seus argumentos têm o valor True . A disjunção, representada por or, tem o valor False apenas se ambos os seus argumentos têm o valor False.

```sql
>>> type(True)
<class 'bool'>

>>> type(False)
<class 'bool'>
```

## Exercícios práticos



1. Recorde as operações aritméticas básicas do Python: `+` \(adição\), `-` \(subtracção\), `*` \(multiplicação\), `/` \(divisão\), `**` \(exponenciação\), `//` \(divisão inteira\), `%` \(resto da divisão inteira\). Avalie as expressões:

* 21000
* 45+2×3
* \(45+2\)×3
* 72÷3+3
* resto da divisão inteira de 25 por 3
* resto da divisão inteira de 25 por 5





## Exercícios laboratoriais





