# Sintaxe e semantica

## Slides PowerPoint

{% file src=".gitbook/assets/sintaxe-e-semantica.pdf" caption="Slides Sintaxe e Semântica" %}

Ao estudar uma linguagem de programação é fundamental uma perfeita compreensão da sua sintaxe e da sua semântica.

{% hint style="info" %}
A **sintaxe** determina qual a constituição das frases que podem ser fornecidas ao computador.
{% endhint %}

{% hint style="info" %}
A **semântica** vai determinar o que o computador vai fazer ao seguir cada uma dessas frases.
{% endhint %}

## Sintaxe

A **sintaxe** de uma linguagem é o conjunto de regras que definem quais as relações validas entre os componentes da linguagem, tais como as palavras e as frases. 

{% hint style="info" %}
A **sintaxe** nada diz em relação ao significado das frases da linguagem. Este aspecto é assegurado pela **semântica**.
{% endhint %}

Como a **sintaxe** apenas se preocupa com o processo de combinação dos símbolos de uma linguagem, ela pode ser  formalizada através de uma **gramática**.

Uma **gramática** é uma ferramenta poderosa para a descrição e análise de linguagens. Uma gramática é o conjunto de regras segundo as quais as frases válidas da linguagem são construídas. Para formalizar uma gramática podemos utilizar várias notações no nosso caso vamos utilizar a **notação BNF.**

{% hint style="info" %}
**notação BNF -** [Backus-Naur Form ](https://en.wikipedia.org/wiki/Backus%E2%80%93Naur_Form) foi originalmente criada por John Backus e Peter Naur, no final dos anos 50, para descrever a [linguagem ALGOL](https://pt.wikipedia.org/wiki/ALGOL). Desde então a sua utilização generalizou-se para a especificação de linguagens de programação.
{% endhint %}

### Regras da notação BNF

A notação BNF é constituída por símbolos não terminais, símbolos não terminais e regras de produção.

* **Símbolos não Terminais -** Conjunto finito, de símbolos da gramática que podem ser substituídos por uma sequência de símbolos terminais.

{% hint style="info" %}
Os símbolos não terminais escrevem-se entre **`<` e `>`**
{% endhint %}

* **Símbolos Terminais -** Conjunto finito, não vazio, **dito alfabeto**  que não podem ser substituídos, correspondem às palavras válidas na linguagem.

{% hint style="info" %}
No caso do Python os símbolos terminais são:  **and, as, assert, break, class, continue, def, del, elif, else, except, exec, finally, for, from, global, if, import, in, is, lambda, not, or, pass, print, raise, return, try, while, with, yield,**
{% endhint %}

* **Regras de Produção** – Conjunto de uma regra da gramática que define a forma como os símbolos não terminais podem ser substituídos. As regras de produção escrevem-se segundo a seguinte convenção:
  * o símbolo **`::=`** define componentes da linguagem, i.e., símbolos não terminais, e lê-se "definido como";
  * o símbolo **`|`** denota possíveis alternativas e lê-se "ou";
  * a utilização do carácter **`+`** imediatamente após um símbolo não terminal denota que o mesmo pode ser repetido uma ou mais vezes;
  * a utilização do carácter **`*`** imediatamente após um símbolo não terminal denota que o mesmo pode ser repetido zero ou mais vezes;
  * a utilização de chavetas, **`{` e `}`**, englobando símbolos terminais ou não terminais, significa que esses símbolos são opcionais.

### Exemplo de gramática em notação BNF

representação de todos os número binários \(exemplos: 100100, 0001111000\)

```sql
<número binário> ::= <digito binário> | <digito binário> <número binário>
<digito binário> ::= 0 | 1
```

{% hint style="info" %}
**Símbolos Terminais**

**0 e 1**
{% endhint %}

{% hint style="info" %}
**Símbolos não Terminais** 

```sql
<número binário>
<digito binário>
```
{% endhint %}

{% hint style="info" %}
**Regras de Produção**

```sql
<número binário> ::=
<digito binário> ::=
```

\*\*\*\*

> A gramática tem duas regras de produção. 
>
> A primeira define a classe dos números binários, representados pelo símbolo não terminal **numero binário**, como sendo um **dígito binário**, ou um **dígito binário** seguido de um **numero binário**. 
>
> A segunda parte desta regra diz simplesmente que um **numero binário** é constituído por um **dígito binário** seguido por um **numero binário.**
{% endhint %}

### Erro Sintáctico

Os erros  sintácticos resultam do facto de o programador não ter escrito as frases do seu programa de acordo com as regras da gramática da linguagem de programação utilizada. A detecção destes erros é feita pelo processador da linguagem, o qual fornece normalmente um diagnostico sobre o que provavelmente está errado.

De sequida é apresentado  um trecho de código em **Python** que ao ser executado o interpretador  detecta  um erro sintatico. Neste caso a mensagem apresentada indica que  a instrução **print** deveria estar aninhada dentro do **if.**

```sql
if 5 > 2:
print("Five is greater than two!")
```

```sql
C:\Users\My Name>python demo_indentation_test.py
  File "demo_indentation_test.py", line 2
    print("Five is greater than two!")
        ^
IndentationError: expected an indented block
```

Código com o erro sintatico corrigido, isto com a instrução **print** aninhada no **if**

```sql
if 5 > 2:
 print("Five is greater than two!")  
```

## Semântica

A semântica de uma linguagem define qual o significado de cada frase da linguagem. A semântica nada diz quanto ao processo de geração das frases da linguagem. A descrição da semântica de uma linguagem de programação é  muito mais difícil do que a descrição da sua sintaxe.

{% hint style="info" %}
Um dos processos de descrever a semântica de uma linguagem consiste em fornecer uma descrição em linguagem natural \(por exemplo, em portugês\) do significado, ou seja, das acções que são realizadas pelo computador, de cada um dos possíveis  componentes da linguagem. Este processo, embora tenha os inconvenientes da informalidade e da ambiguidade associadas às línguas naturais, tem a vantagem de fornecer uma perspectiva intuitiva da linguagem.
{% endhint %}

Por exemplo, a sintaxe da instrução **if** da linguagem **Python** é: 

```sql
if condition :
    true-block
    several instructions that are executed
    if the condition evaluates to True
else:
    false-block
    several instructions that are executed
    if the condition evaluates to False
```

e a  semântica da instrução **if**  é: 

> Se o valor da condição for verdadeiro, o bloco  **true-block** constituído por um conjunto de  instruções  será executado pelo programa, caso contrario o bloco **false-block** constituído por outro conjunto de  instruções  será executado pelo programa.

Cada frase em **Python** tem uma semântica, a qual corresponde as acções tomadas pelo Python ao executar essa frase, ou seja, o significado que o Python atribui à frase.

### Erro Semântico

Os erros de natureza semântica, ou erros semânticos \(também conhecidos por erros de lógica\) são erros em geral muito mais difíceis de detectar do que os erros de caracter sintáctico. Estes erros resultam do facto de o programador não ter expressado correctamente, através da linguagem de programação, as acções a serem executadas \(o programador queria dizer uma coisa mas disse outra\).

No exemplo apresentado pretendiamos calcular a média de dois números introduzidos pelo utilizador, mas ao executar o programa  este não produz o resultado esperado porque, devido as regras de avaliação de uma expressão. é realizado primeira a divisão de **y/2** antes da **soma x+y.**

```sql
x = float(input('Enter a number: '))
y = float(input('Enter a number: '))

z = x+y/2 #É feita primeira a divisão y/2 e só depois a soma
print ('The average of the two numbers you have entered is:',z)
```

Exemplo com o erro semântico corrigido.

```sql
x = float(input('Enter a number: '))
y = float(input('Enter a number: '))

z = (x+y)/2 #É feita primeira a soma x+y e depois a devisão
print ('The average of the two numbers you have entered is:',z)
```

## Depuração

Ao processo de deteccao e correccao, tanto dos erros sintacticos como dos erros semanticos, da-se o nome de depuracao. Em ingles, este processo ́e denominado “debugging” e aos erros que existem num programa, tanto sinta cticos como semanticos, chamam-se “**bugs” - insecto .**

{% hint style="info" %}
O termo “bug” foi criado por Grace Murray Hopper \(1906– 1992\). Em Agosto de 1945, Hopper e alguns dos seus associados estavam a trabalhar em Harvard com um computador experimental, o Mark I, quando um dos circuitos deixou de funcionar. Um dos investigadores localizou o problema e, com auxılio de uma pinca, removeu-o: uma traca com cerca de 5 cm. Hopper colou a traca, com fita gomada, no seu livro de notas e disse: “A partir de agora, sempre que um computador tiver problemas direi que ele contem insectos
{% endhint %}

![](.gitbook/assets/09.09.1947-first-computer-bug.png)

## Exercícios práticos

1. Proponha uma gramática **BNF** que descreva a sintaxe para chamar uma shell de comandos chamada “fred”, que precisa de um valor numérico não negativo como seu argumento. Por exemplo: **fred 12        fred 23        fred 567**
2. A partir dos seguintes exemplos de um codigo, escreva a respective notação BNF: **K1N 6N5  ;  M5W 2E4 ;  X0A 1A1**
3. Escreva a notação BNF que permita representar palavras do tipo palindromes \(espaços são ignorados\) :  **Aba**  ;   **pop    pop a pop**  ;  **elu par cette crapule**
4. A partir dos seguintes exemplos de um numero binário  escreva a respective notação BNF:  **1010 ; 00110 ; 01011**
5. A partir da seguinte gramática:

```sql
<simb> ::= <simb> XX | XX
```

* Diga, justificando, quais das seguintes frases pertencem ou não à linguagem definida pela gramática:
  1.  XXX
  2. XXXX
  3. AXX
  4. XX
  5. XXXXXX



