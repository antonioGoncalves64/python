# Funções

## Introdução

Nao é possıvel que uma linguagem de programacao forneca todas as operacoes que sao necessarias para o desenvolvimento de uma certa aplicacao. Por isso, durante o desenvolvimento de um programa, é necessario utilizar operacoes que nao estao previamente definidas na linguagem. Este problema pode ser resolvido porque o Python, tal como a maior parte das linguagens de programacao através de  mecanismos para a criacao de novas operacoes e para a sua utilizacao num programa.  

 Em Python podemos definir funções indicando o nome da mesma, os seus argumentos e a sequência de instruções a executar pela função, i.e., o corpo da função. Esta sequência de instruções ou corpo corresponde ao algoritmo que se pretende executar quando utilizamos a função. 

{% hint style="info" %}
A utilização de funções em **Python** compreende: a definição da função e a aplicação de função 
{% endhint %}

## Definição de uma função em Python 

Para definir funcoes em **Python**, é necessario indicar o nome da função, os seus argumentos  e o  corpo. A sintaxe desta instrução, em notação **BNF**, é:  

```sql
<definição de função> ::=
    def <nome> (<parâmetros formais>): NEWLINE
    INDENT <corpo> DEDENT

<parâmetros formais> ::= <nada> | <nomes>

<nomes> ::= <nome> | <nome>, <nomes>

<nada> ::= 

<corpo> ::= <definição de função>* <instruções em função>

<instruções em função> ::=
    <instrução em função> NEWLINE |
    <instrução em função> NEWLINE <instruções em função>

<instrução em função> :: <instrução> | <expressão> | <instrução return>

<instrução return> ::= return | return <expressão>
```

O seguinte exemplo apresenta a definição de uma função em **Python**:

```python
def dobro (x):
    return x + x 
```

A semântica da definicao de uma função é a seguinte: ao encontrar a definição de uma função, o **Python** cria um nome, correspondente ao nome da função, e associa esse nome com um processo de cálculo. Ao definir uma função, o **Python** adiciona ao ambiente o nome correspondente ao nome da função, associando-o ao algoritmo para calcular o resultado da função.

No exemplo apresentado podemos dizer:

1. O nome **`x`** representa o **argumento** da função;
2. A instrução **`return x + x`** corresponde ao corpo da função.

{% hint style="info" %}
Os argumentos da função,  quando da sua definição, são designados por **parâmetros formais** e servem para identificar os valores no corpo da função.
{% endhint %}

## Aplicação de funções em Python

As funções uma vez definidas podem ser utilizadas tal como as funções pré-definidas do Python. Para utilizarmos umas função basta invocar a mesma utilizando o seu nome e passando parâmetros concretos, i.e., expressões em número igual aos parâmetros formais indicados na definição da função. Em notação BNF,

```python
<aplicação de função> ::= <nome>(<parâmetros concretos>)

<parâmetros concretos> ::= <nada> | <expressões>

<expressões> ::=
    <expressão> |
    <expressão>, <expressões>
```

Consideremos o seguinte exemplo em que utilizamos a função `dobro` definida acima: 

```c
>>> dobro(100)
200
>>> dobro(50,75
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: dobro() takes 1 positional argument but 2 were given
>>> dobro()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: dobro() missing 1 required positional argument: 'n'
>>>
```

A interaccao anterior mostra como aplicar \(i.e chamar a função soma previamente definida\).  que se fornecermos  a função  soma o argumento **7**, o valor da funcao  é **200**. Se fornecermos dois argumentos a funcao, o **Python** gera um erro indicando-nos que esta função recebe apenas um argumento.

{% hint style="info" %}
Quando aplicamos uma função \(i.e., utilizamos\)  os valores passados nos parâmetros são desigandos por **parâmetros concretos**
{% endhint %}

Quando uma função é invocada em **Python** ocorrem os seguintes passos: 

1. Os parâmetros concretos são avaliados \(por uma ordem arbitrária\).
2. Os parâmetros formais da função são associados aos valores dos parâmetros concretos  pela mesma ordem respectivamente.
3. As instruções do corpo da função são executadas e que apenas existe enquanto a função não terminar, sendo apagado após o término da mesma.

O resultado de uma função é passado para o ambiente envolvente da função através da execução da instrução `return` a qual retorna o valor \(se existir uma expressão a avaliar, caso contrário não retorna nada\) e termina a função. Se não existir uma instrução `return` no corpo da função, esta termina sem retornar qualquer valor.

## Abstracção procedimental

A abstracção procedimental consiste em abstrair de como as funções operam e focar no que as funções realizam, i.e., separar o "como" do "o que". Por outro lado consiste em dar um nome à sequência de operações que serve para produzir um determinado resultado e/ou efeito, sendo que podemos utilizar esse nome para invocar a função.

Isto permite, ao desenvolver um programa complexos,  identificar os principais problemas que têm que ser resolvidos. espeficificando-se as funções que realizam estas tarefas sem entrar em detalhes de como o fazem.  Depois da escrita de uma primeira versão do programa, vamos abordar o desenvolvimento de cada uma das funções, utiliando o mesmo conceito de **abstração procedimental** 

O seguinte exemplo apresenta outra  definição de uma função em **Python** que permite somar todos os numeros interios até a um valor **`n`** passado por parâmetro

```python
def soma(n):
    iter = 1
    soma = 0
    while iter <= n:
        soma = soma + iter
        iter = iter + 1
    return soma
```

Usando a abstraccao procedimental consideramos funcoes como caixas – sabemos o que eles fazem, mas nao nos interessa saber como o fazem. Para ilustrar este aspecto, reltivsmente a função soma aprsentada, para a finalidade da sua utilizacao, os pormenores da realizacao da funcao soma sao irrelevantes. Poderíamos ter definido a função soma do seguinte modo, porque obtemos  exactamente o mesmo comportamento. \(i.e., resultado esperado\).

```python
def soma(n):
    if n < 1:
        return 0
    return n*(n+1)//2
```

{% hint style="info" %}
A **abstracção procedimental** permite-nos desenvolver programas complexos sem nos perdermos em pormenores em relação à especificação minuciosa do algoritmo, porque ao utilizarmos uma função o que nos interesse saber é o que ela faz e não como o faz.
{% endhint %}



## Exercícios práticos

1. Escreva um programa em que determine que determine se um dado número inteiro é par ou ímpar. Para isso, deverá usar a função **`int par (int)`** que  retorna 1 se o inteiro passado como parâmetro for par e 0 caso contrário. 
2. Escreva um programa que determine o maior de três números inteiros. Deverá usar a função int **`maiorDeTres (int, int, int)`** que devolve o maior dos inteiros passados como parâmetro.
3. Escreva um programa que permita determinar o maior e o menor número duma sequência de N números inteiros dados pelo utilizador. O valor de N deverá ser superior ou igual a 2. Se não for o seu valor deverá ser pedido novamente até obter um valor válido. A introdução de números deverá terminar quando forem inseridos N números. Nessa altura a aplicação deverá mostrar o valor máximo e mínimo de entre os valores introduzidos.  Deverá usar as funções maximo e minimo, cujos protótipos a seguir se apresentam: 

       f**`loat maximo (float, float)`** : Devolve o maior dos reais passados como parâmetros. 

       **`float minimo (float, float)`**: Devolve o maior dos reais passados como parâmetros. 

4. Escreva um programa que determine a média duma sequência de N números inteiros dados pelo utilizador .

   Deverá usar a função **`float media (int)`** que devolve a media dos inteiros. O argumento passado à função media é o valor N, sendo que os números inteiros são fornecidos pelo utilizador. 

5. Faça uma função que imprima no visor apenas os números ímpares entre 1 e 50.
6. Faça uma função que receba dois números inteiros e gere os números inteiros que estão no intervalo compreendido por eles.
7. Defina a função `soma_nat` que recebe como argumento um número natural n e devolve a soma de todos os números naturais até n.
8. Defina a função `num_perf` que recebe como argumento um número inteiro positivo e devolve `True` se esse número for um número perfeito e `False` em caso contrário. Recorde que um número perfeito é um número natural que é igual à soma de todos os seus divisores próprios, isto é, a soma de todos os divisores excluindo o próprio número. Pode se assim o entender, definir funções auxiliares, desde que definidas no paradigma funcional.
9. Crie uma função que determine se um número inteiro é primo.
10. Escreva um programa em que o utilizador vai introduzindo números inteiros positivos até o número introduzido ser um número primo. Faça uso de uma função para determinar se o número é primo.
11. Escreva um programa que leia 10 números do utilizador e indique, no fim, quantos números são primos, quantos são pares e quantos são divisíveis por 3. Faça uso de  funções para determinar se o número é primo, par e divisível por 3. 
12. Escreva um programa em que o utilizador introduza números até introduzir um número par seguido de um número ímpar. Faça uso de funções.
13. Crie uma função que receba 2 valores inteiros como argumentos e retorne a sua soma. Se o valor da soma for negativo o método deverá retornar o valor 0.
14. Crie uma função que receba 3 valores reais como argumento e retorne o maior valor.
15. Crie uma função que receba dois valores reais como argumentos e retorne o valor da raiz quadrada da soma dos quadrados.
16. Crie uma função que receba um número inteiro como argumento e retorne o maior valor primo inferior a esse argumento. Se o argumento for negativo, a função deverá retornar o valor zero.
17. Crie uma função ContaPrimos\(\) que receba dois valores inteiros como argumentos e retorne o número de números primos entre estes dois números, inclusive. P. Ex. ContaPrimos\(3,10\) deverá retornar o valor 3 \(3, 5, 7\).
18. Crie uma função que receba 2 notas \(F1 e F2\) de um aluno e retorne um booleano indicando se o aluno passou. Para passar, a soma das notas deve ser igual ou superior a 19 e ambas devem ser superiores a 7.
19. Um ano é bissexto se é divisível por 4, excepto se, além de ser divisível por 4, for também divisível por 100. Então ele só é bissexto se também for divisível por 400. Escrever um algoritmo que leia o valor de um ano e escreva se o ano é ou não bissexto.

## Exercícios laboratoriais

1. Faça a função int **`somaDigitos(int)`** que devolve a soma dos dígitos dum dado número inteiro positivo. 
2. Faça a função **`fibonacci (int n)`** que escreva os primeiros N números da sequência de Fibonacci. A sequência de Fibonacci é a seguinte: 1, 1, 2, 3, 5, 8, 13, 21, ... \(a seguir ao primeiro 1 cada número na sequência é a soma dos dois números anteriores\). 
3. Faça a função **`binToDecimal(string s)`** que converte e devolve  um número binário, passado por parâmetro, em um número decimal. **Por exemplo: 100102 =1**_**2^4+0**_**2^3+0**_**2^2+1**_**2^1+0\*2^0=1810**
4. Faça a função **`int decimalToBin(int n)`** que converte e devolve  um número decimal, passado por parâmetro, em um número binario. **Por exemplo:  1810 = 100102**  
5. Faça a função boolean **`ePrimo(int n)`** que  determinar se um determinado número inteiro  n positivo é primo. Um número é primo se só for divisível por ele próprio e pela unidade. Por exemplo: 13. Não deverão ser aceites números negativos. Nesse caso a aplicação deverá pedir números até que seja introduzido um número válido. 
6. Faça a função boolean **`eCapicua(int n)`** que que  determinar se  um determinado número inteiro é capicua. Um número é capícua se for o mesmo número lido da esquerda para a direita ou da direita para a esquerda. **Por exemplo: 202.** 
7. Defina a função `quadrados` que recebe como argumento um número natural n devolve a lista dos  n primeiros quadrados perfeitos.  Nota um quadrado perfeito é um número cuja raiz quadrada é um número inteiro.  A sequencia dos quadros perfeitos pode ser obtido pela soma da sequência de numeros ímpares, começando do zero. Por exemplo: 0 + 1 = 1 ; 0 + 1 + 3 = 4 ;  0 + 1 +3 + 5 = 9;  0 + 1 +3 +5 + 7 = 16.
8. Defina a função `quadrados_inv` que recebe como argumento um número natural n devolve a lista dos  n primeiros quadrados perfeitos, por ordem decrescente.
9. Escreva um programa que leia 10 valores do utilizador e indique no fim se foi introduzido algum número divisível por 7. Faça uso de funções.
10. Escreva um programa em que o utilizador introduz números inteiros até introduzir um número em que a soma dos algarismos seja superior a 20.
11. Escreva um programa que indique ao utilizador todos os números primos entre dois números inteiros introduzidos pelo utilizador.
12. Crie um programa que imprima um número de 4 dígitos invertido \(ex. 4536 -&gt; 6354\).
13. Escreva um programa que reduza uma fração.
14. Crie uma função que receba dois valores inteiros como argumentos e retorne um valor booleano indicando se os números são divisíveis.
15. Crie uma função que receba um número inteiro e retorne a soma dos seus algarismos.
16. Crie uma função que receba 3 valores inteiros \(a, b, c\) e retorne um valor booleano true se a&gt;b&gt;c e false em caso contrário.
17. Crie uma função que verifique se um número é primo \(deverá retornar um valor booleano\).
18. Crie uma função que receba um número inteiro n e retorne o n-ésimo número primo.
19. Crie uma função que receba três inteiros como argumentos \(ano, mês, dia\) e verifique se se trata de um data válida. O ano deverá estar entre 1900 e o presente ano. Deverá retornar um valor booleano.

