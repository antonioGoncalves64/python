# Expressões

Um dos tipos de entidades que utilizamos nos nossos programas corresponde a expressões. Por definição, uma expressao é uma entidade computacional que tem um valor. Usamos o termo entidade computacional para designar, de um modo genérico, uma entidade que existe dentro de um programa. Uma expressão em Python pode ser uma **constante**, uma **expressão composta o**u um **nome**. Em notação **BNF**, uma **expressão** é definida do seguinte modo:

```sql
<expressão> ::= <constante> | <expressão composta> | <nome>
```

## Constante

 Em **Python** podem ser números, valores lógicos ou cadeias de caracteres. Sempre que é fornecida uma constante ao **Python**, este devolve a constante como resultado da avaliação. Ou seja, o valor de uma constante é a própria constante.

```python
#NUMERO POSITIVO
10

#NUMERO NEGATIVO
-1

#VALOR LÓGICO 
True

#CADEIA DE CARACTER 
’Bom dia’

#CADEIA DE CARACTER 
"Bom dia"
```

### Tipos de constantes

**Números Inteiros.** Estes correspondem a números sem parte decimal \(com ou sem sinal\) e podem ser arbitrariamente grandes.

```python
#NUMEROS POSITIVOS
10
655484877641416186376754588877162243232221200091999228887333

#NUMERO NEGATIVO
-1
```

**Números Reais.** Estes correspondem a numeros com parte decimal \(com ou sem sinal\) e podem ser arbitrariamente grandes ou arbitrariamente pequenos. Os numeros reais com valores absolutos muito pequenos ou muito grandes são apresentados \(eventualmente arredondados\) em notacao cientÍfica.

```python
#NUMEROS REAIS
3.5
65397518517617656541959.888666225224423331
0.00000000000000000000000000000000000001
```

**Valores lógicos.** Os quais são representados por **True** \(verdadeiro\) e **False** \(falso\).

```python
#VALORES LÓGICOS
True
False
```

**Cadeias de caracteres.** As quais correspondem a sequencias de caracteres. O comprimento da cadeia é o numero de caracteres que a constitui. As constantes das cadeias de caracteres sao representadas em Python delimitadas por **plicas**  ou **aspas**.

```python
#CADEIA DE CARACTER COM PLICAS
'Ola Mundo !'

#CADEIA DE CARACTER COM ASPAS
"Ola Mundo !"
```

## Expressões compostas

Uma expressão composta é constituída por um **operador** e por um certo número de **operandos**. Os operadores podem ser **unários** \(se apenas tem um operando, por exemplo, o operador lógico not ou o operador **-** representando o simétrico\) ou **binários** \(se têm dois operandos, por exemplo, + ou \*\). Em notação **BNF**, uma **expressão composta** é definida do seguinte modo:

```sql
<expressao composta> ::= <operador> <expressao> |
                         <operador> (<expressao>) |
                         <expressao> <operador> <expressao> |
                         <expressao> <operador> <express ̃ao>)
```

Utilizando expressões compostas  podemos originar a seguinte interacção:

```sql
>>> 2012 - 1958
54

>>> 3 * (24 + 12)
108

>>> 3.0 * (24 + 12)
108.0

>>> 7 > 12
False

>>> 23 / 7 * 5 + 12.5
28.928571428571427
```

Uma questão que surge imediatamente quando consideramos expressões com postas diz respeito à ordem pela qual as operações  são efectuadas. Por exemplo qual o **denominador** da ultima expressao apresentada?   

* **7?     7 \* 5?   7\*5+12.5?**

Para evitar ambiguidade em relacao á ordem de aplicacao dos operadores numa expressao, o Python utiliza duas regras que especificam a ordem de aplicacao dos operadores. 

1. A primeira regra, associada a uma lista de prioridades de operadores, **especifica que os operadores com maior prioridade são aplicados antes dos operadores com menor prioridade;** 
2. A segunda regra especifica qual a ordem de aplicação dos operadores quando se encontram dois operadores com a mesma prioridade. Neste caso quando existem dois \(ou mais\) operadores com a mesma prioridade, eles são aplicados da **esquerda para a direita.**

| **Prioridade** | **Operador** |
| :--- | :--- |
| **Máxima** | execução de funções, not, - \(simétrico\), \*, /, //, %, and, +; -, or |
| **Mínimo** | &lt;, &gt;,  ==, &gt;=, &lt;=, ! |

Dito de outro modo:

{% hint style="info" %}
> #### Prioridade entre os operadores \(ordem de cálculo\):
>
> parêntesis **\( \)**  
> exponenciação **\*\***  
> multiplicação e divisão **\* /**  
> soma e subtração **+ -**

  
**Operadores da mesma prioridade agrupam à esquerda.**
{% endhint %}

{% hint style="info" %}
A utilização de parêntesis permite alterar a ordem de aplicação dos operadores.
{% endhint %}

```sql
#Exemplos de avaliação de expressões compostas
>>> 20 + 4 * 10
60

>>> (20 + 4) * 10
240

>>> 2 * 3 ** 4 * 5
810

>>> 2 * 3 ** (4 * 5)
6973568802
```

## Exercícios práticos



1. Recorde as operações aritméticas básicas do Python: `+` \(adição\), `-` \(subtracção\), `*` \(multiplicação\), `/` \(divisão\), `**` \(exponenciação\), `//` \(divisão inteira\), `%` \(resto da divisão inteira\). Avalie as expressões:

* 21000
* 45+2×3
* \(45+2\)×3
* 72÷3+3
* resto da divisão inteira de 25 por 3
* resto da divisão inteira de 25 por 5

1. Diga qual o resultado rpduzido em cada expressão:

* \(4/2\)+\(2/4\)
* 4/\(2+2\)/4e
* \(4+2\)\*2-4
* 4/2+2/4 B 4/2+2/4
* 4+2\*2-4

1. Reescreva as instruções abaixo com o mínimo de parênteses possível, mas sem alterar o

   resultado:

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <img src="blob:https://app.gitbook.com/d9bed0b9-66f5-4b19-81c8-5a461a229ca7"
        alt="page4image677903728" />6*(3+2)</th>
      <th style="text-align:left">
        <p>
          <img src="blob:https://app.gitbook.com/d88ddcc1-e2dc-4125-acf7-8c180111d0a3"
          alt="page4image677993920" />
        </p>
        <p>F
          <img src="blob:https://app.gitbook.com/d9e9178d-d3a5-43e2-997b-ec33813b3d31"
          alt="page4image677995920" />(6/3)+(8/2)
          <img src="blob:https://app.gitbook.com/5e4334cc-6cde-4684-add0-50579bd4e322"
          alt="page4image677997648" />
        </p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">B
        <img src="blob:https://app.gitbook.com/ca88ad9a-b3cc-4328-abd4-11df84e59464"
        alt="page4image677998848" />2+(6*(3+2))</td>
      <td style="text-align:left">G
        <img src="blob:https://app.gitbook.com/8cea969e-25c6-448d-abdc-ecdd79b1722f"
        alt="page4image678000048" />((3+(8/2))*4)+(3*2)</td>
    </tr>
    <tr>
      <td style="text-align:left">C
        <img src="blob:https://app.gitbook.com/c16491a4-f46b-4003-87a9-370add76e53c"
        alt="page4image678008032" />2+(3*6)/(2+4)</td>
      <td style="text-align:left">H
        <img src="blob:https://app.gitbook.com/33502698-4ed6-4ad0-8ec2-407d41e43af9"
        alt="page4image678011840" />(6*(3*3)+6)-10</td>
    </tr>
    <tr>
      <td style="text-align:left">D
        <img src="blob:https://app.gitbook.com/3eea986d-d7c5-402f-95cd-720a862b3a72"
        alt="page4image678014912" />2*(8/(3+1))</td>
      <td style="text-align:left">I
        <img src="blob:https://app.gitbook.com/f0db382c-ea85-40bd-9d36-9a7e2c475100"
        alt="page4image678016112" />(((10*8)+3)*9)</td>
    </tr>
    <tr>
      <td style="text-align:left">E
        <img src="blob:https://app.gitbook.com/a9349b56-775f-4240-9c8f-366e370c13e3"
        alt="page4image678024672" />3+(16-2)/(2*(9-2))</td>
      <td style="text-align:left">J
        <img src="blob:https://app.gitbook.com/7b8593de-64c0-4673-a186-31e5ddfcd265"
        alt="page4image678027072" />((-12)*(-4))+(3*(-4))</td>
    </tr>
  </tbody>
</table>





## Exercícios laboratoriais

