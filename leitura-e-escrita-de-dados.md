# Leitura  e escrita de dados

## Introdução

Durante a execução de um programa, o computador necessita normalmente de obter valores do exterior para efectuar a manipulação da informação. A obtenção de valores do exterior  é feita através das operações de leitura de dados.

Apos efectuar a manipulação da informação, é importante que o computador possa comunicar ao exterior os resultados a que chegou. Isto é feito através das operações de escrita de dados. As operações de escrita de dados permitem transmitir informação  do programa para o exterior.

## Leitura de dados

As operacoes de leitura de dados em que os dados sao fornecidos atraves do teclado é realizado pela função **input**. Esta funcao tem a seguinte sintaxe em notação **BNF**:

```sql
<leitura de dados> ::= input()  | 
                       input(<cadeia de caracteres>)
```

A seguinte interacção apresenta o uso da função **input\(\) :**

```sql
s = input()
ola mundo !

s
'ola mundo !'
```

Neste caso o Python nao é mostrada nenhuma indicação no écran do computador, ficando o Python à espera que seja escrita qualquer informação escrevendo no teclado **"ola mundo !"** seguido de **“Return”** a função **input** devolve a cadeia de caracteres **"ola mundo !"** 

A seguinte interacção apresenta o uso da função **input\(\) :**

```sql
s = input('->')
-> Ola Portugal !

s
'Ola Portugal !'
```

Neste caso o Python mostra o valor da cadeia de caracteres **’-&gt; ’**, o qual corresponde a  **-&gt;** , e lê o que é fornecido atraves do teclado, neste caso, **"ola Portugal"** seguido de **“Return”**, sendo devolvida a cadeia de caracteres **’Ola Portugal !’**.

{% hint style="warning" %}
**`input()`** sempre retorna uma cadeia de caracteres. Se pretender um valor **inteiro** ou **real** é necessário fazer a **conversão** através da função **int\( \), float \( \)** 
{% endhint %}

A seguinte interacção apresenta o uso das funções de conversão **int \( \)** e **float \( \)** com a função **input\(\) :**

```sql
n = input('Enter a number: ')
Enter a number: 50
n + 100
 
 Traceback (most recent call last):
 File "<stdin>", line 1, in <module>
 TypeError: must be str, not int
 
 >>> n = int(input('Enter a number: '))
 Enter a number: 50
>>> n + 100
150
```

## Escrita de dados

As operações de escrita de dados permitem transmitir informação do programa para o exterior. No caso do ècran a instrução utilizada é **print \( \).** Esta função tem a seguinte sintaxe em notação **BNF**:

```sql
<escrita de dados> ::= print()  | 
                       print(<expressões>)
```

A seguinte interacção apresenta o uso da função **print\(\) :**

```sql
fname = 'António'
lname = 'Gonçalves'

print('Nome:', fname, lname)
Nome: António Gonçalves

print('foo', 42, 'bar')
foo 42 bar


```

**print** pode receber  dois parâmetros que são passados ao final com as palavras reservadas _**sep** ou_  _**end**_   

A seguinte interacção apresenta o uso de **sep** com a  função **print\(\) :**

```sql
print('foo', 42, 'bar', sep='/')
foo/42/bar

print('foo', 42, 'bar', sep='...')
foo...42...bar

print('foo', 42, 'bar', sep='')
foo42bar
```

Por norma cada execução de **print \(\)** termina com uma mudança de linha, mas com o uso de **end** é  possivel alterar este comportamento. A seguinte interacção apresenta o uso de **end** com a função **print\(\):**

```sql
print('foo')
print(42)
print('bar')
foo
42
bar

print('foo', end='/')
print(42, end='/')
print('bar')

foo/42/bar
```

A seguinte interacção apresenta o uso de **sep** e **end**  com a função **print\(\):**

```sql
ano1 = '1980'
ano2 = '1990'
ano3 = '2000'
ano4 = '2010'

texto = "Alterar o valor de sep e end"

print(texto)
print(ano1, ano2, ano3, ano4, sep='--->', end='...\n')
print('Fim')

Alterar o valor de sep e end
1980--->1990--->2000--->2010...
Fim
```

### Formatar cadeias de caracteres

Podemos utilizar o método **format\( \)**  para criar uma cadeia de caracteres que contem campos entre chaves a serem substituídos pelos argumentos de format. 

```sql
<cadeia de caracteres formatada> ::= <cadeia de caracteres> % <values>
```

 A seguinte interacção apresenta o uso do método **format\( \):**

```sql
str = 'O filme {0} merece {1} estrelas'
str.format('Exterminador do Futuro', 4)
'O filme Exterminador do Futuro merece 4 estrelas'

str = '{0} é um {1} companheiro, {1} companheiro é o {0}, ninguém pode negar'
str.format('Paulo', 'bom')
'Paulo é um bom companheiro, bom companheiro é o Paulo, ninguém pode negar'
```

Os campos de substituição na cadeia de caracteres estão associadas aos parâmetros de **format** por numeração dentro das chaves começando em zero para o primeiro parâmetro, 1 para o segundo parâmetro e continuando assim sucessivamente. Nada impede que se use um parâmetro mais de uma vez e fora de sua ordem como no  segundo exemplo apresentado.

### Formatar números

Python permite formatar números de acordo com a seguinte **sintaxe**:

```sql
%[flag][tamanho].[precisão][conversor]
```

Onde flag pode ser:

| Flag | Significado |
| :--- | :--- |
| \# | Prefixa os inteiros com 0, 0o, 0O, 0x, 0X. o ou O para octais e x ou X hexadecimais |
| + | Força a saída com sinal. |

e os conversores podme ser:



| Conversor | Significado |
| :--- | :--- |
| d | Inteiro. |
| i | Inteiro. |
| f | Float. |
| F | Float. |
| o | Inteiros em octal. |
| x | Inteiros em hexadecimal minuscula |
| X | Inteiros em hexadecimal maiúsculas |
| e | Float em formato exponencial minusculo |
| E | Float em formato exponencial maiúsculo |
| g | Mesmo que “e” se expoente é maior do que -4 ou inferior a precisão, “f” de outra forma. |
| G | Mesmo que “E” se expoente é maior do que -4 ou inferior a precisão, “F” de outra forma. |
| c | Um único caractere. |
| s | String \(converte qualquer objeto python usando str \(\)\). |

A seguinte interacção apresenta a formatação de números**:**

```sql
 "{0:4}".format(-123)
'-123'
 "{0:4}".format(123)
' 123'
 "{0:4.2f}".format(33.3287)
'33.33'
 "{0:+4.2f}".format(33.3287)
'+33.33'
 "{0:+4.2e}".format(33.3287)
'+3.33e+01'
 "{0:b}".format(123)
'1111011'

```

O Uso da formação permite melhorar bastante comunicação dos resultados de um programa.  Veja  a seguinte interacção onde é calculado a média  de duas notas de um aluno, neste caso a média é apresentad com 4 digitos sendo dois utilizados na parte decimal.

```sql
print('Programa para calcular a media de um aluno')
print()

nome = input('Digite o nome do aluno: ')
print()

nota1 = float(input("Digite a primeira nota: "))
print()

nota2 = float(input("Digite aa segunda nota: "))
print()

media = (nota1 + nota2)/2
print('{0} teve media igual a: {1:4.2f}'.format(nome, media))

#resultado produzido 
Programa para calcular a media de um aluno

Digite o nome do aluno: Antonio

Digite a primeira nota: 16

Digite aa segunda nota: 17

Antonio teve media igual a: 16.50
```

## Exercícios práticos

1. Crie um programa que mostre na tela a frase "Olá Mundo!".
2. Crie um programa que pede para o utilizador digitar seu nome e, em seguida, escreve o seu  nome no ecrã.
3. Crie um programa que leia 2 variáveis inteiras e troque os seus valores.
4. Faça um programa que solicite dois números e imprima a sua soma.
5. Escreva um programa que calcule o quadrado e o cubo de um valor introduzido pelo utilizador.
6. Escreva um programa que leia dois valores e apresente o valor que representa a relação percentual entre esses dois valores.
7. Crie um programa para calcular conversões métricas \(polegadas-metros milhas-km, etc.\).
8. Crie um programa para verificar se um número inteiro positivo é múltiplo de outro. Ambos os números devem ser introduzidos pelo utilizador.
9. Faça um programa que solicite  as 4 notas  e aprsente  a sua média.
10. Crie um programa que permite determinar o perímetro e área de uma circunferência, a partir do valor do raio.
11. Faça um programa que converta metros para centímetros.
12. Escreva um programa que solicite ao utilizador uma determinada data e escreva-a de seguida no formato dd/mm/aaaa.
13. Escreva um programa que tenha o seguinte output: Viva o IPS
14. Desenvolver um programa  para ler o número de uma sala de aula, sua capacidade e o total de alunos matriculados na mesma e imprimir uma linha mostrando o número da sala, sua capacidade, o número de cadeiras ocupadas.
15. Criar um programa  que leia um valor de hora \(hora:minutos\) e informe \(calcule\) o total de minutos se passaram desde o início do dia \(0:00h\).
16. Antes das preocupações  com o consumo de energia, quase ninguém falava em quilowatts; mas, agora, todos incorporaram essa palavra em seu vocabulário. Sabendo-se que 100 quilowatts de energia custa um sétimo do salário base, fazer um programa que receba o valor do salário base e a quantidade de quilowatts gasta por uma residência e calcule \(imprima\). o valor em euros de cada quilowatt;  o valor em euros a ser pago e o novo valor a ser pago por essa residência com um desconto de 10%
17. Criar um programa  que leia o valor de um depósito e o valor da taxa de juros. Calcular e imprimir o valor do rendimento e o valor total depois do rendimento.
18. Uma P.A. \(progressão aritmética\) fica determinada pela sua razão \(r\) e pelo primeiro termo\(a1\). Escreva um programa  que seja capaz de determinar qualquer termo de uma P.A., dado a razão e o primeiro termo, sendo an = a1 + \(n - 1\)\* r
19. Dada a razão de uma P.A. \(progressão aritmética\) e um termo qualquer, k \(ak\). Escreva um programa  para calcular qualquer outro termo, n, \(an\), sendo an = ak + \(n - k \) \* r
20. Considere que o número de uma placa de veículo é composto por quatro algarismos. Construa um programa  que leia este número e apresente o algarismo correspondente à casa dos milhares.

## Exercícios laboratoriais

1. Crie um programa que lê nome e idade e mostra no ecrã
2. Faça um programa que peça um número e então mostre a mensagem _O número digitado foi \[número\]_.
3. Crie um programa que lê nome, idade e altura e mostra no ecrã as informações.
4. Escreva um programa que calcule o resto da divisão inteira entre 2 números introduzidos pelo utilizador.
5. Faça um programa para uma loja de tintas. O programa deverá pedir o tamanho em metros quadrados da área a ser pintada. Considere que a cobertura da tinta é de 1 litro para cada 6 metros quadrados e que a tinta é vendida em latas de 18 litros, que custam euros 80,00 ou em galões de 3,6 litros, que custam Euros 25,00.
6. Crie um programa para determinar se um aluno passou na disciplina de TP I a partir dos valores das duas frequências \(F1, F2\) e do trabalho \(T\). A fórmula para obter a nota final \(NF\) é a seguinte: F = \(F1+F2\)/2 \(arredondado às unidades\) NF = F \* \(20-T\) / 20 + T \(arredondado às unidades\)
7. Um stand  que venda  carros paga a seus empregados um salário deEuros 1000,00 por mês mais uma comissão de Euros 500,00 para cada carro vendido e mais 5% do valor da venda. Elabore um programa para calcular e imprimir o salário do vendedor num dado mês recebendo como dados de entrada o nome do vendedor, o número de carros vendidos e o valor total das vendas.
8. Calcule a média de um aluno na disciplina de MDS. Para isso solicite o nome do aluno, a nota da prova e a nota qualitativa. Sabe-se que a nota da prova tem peso 2 e a nota qualitativa peso 1. Mostre a média como resultado.
9. Escreva um programa  que leia dois números inteiros e imprima o resultado da divisão destes dois valores. Antes do resultado, deve ser impressa a seguinte mensagem “divisão”
10. Tendo como dados de entrada a altura de uma pessoa, construa um programa que calcule seu peso ideal, usando a seguinte fórmula: \(72.7\*altura\) - 5
11. Escreva um programa que solicite ao utilizador dois inteiros e apresente o resultado da realização das operações aritméticas tradicionais.
12. Escreva um programa que solicite um determinado número real e escreva a sua parte inteira e fraccionária.
13. Escreva um programa que leia 4 numeros inteiros e apresente a multiplação dos svalores entre si. Utilize a propriedade comutativa.
14. Escreva um programa que leia um numero com 3 digitos e acrescente um novo digoto na unidade, desigando por  digito de validação. O digito de validação é calculado pelo resto da  soma dos três digitos por 5. Por exemplo:  123 ficaria 1231 \(porque 1+2+3 =6 e  resto de 6/5 é 1\).
15. Escreva um programa que solicite ao utilizador uma determinada data no formato aaaa-mm-dd e escreva-a de seguida no formato dd/mm/aaaa.
16. Faça um programa que solicite o tamanho de um arquivo para download \(em MB\) e a velocidade de um link de Internet \(em Mbps\), calcule e informe o tempo aproximado de download do arquivo usando este link \(em minutos\).
17. Faça um programa que solicite  2 números inteiros e um número real. Calcule e mostre: o produto do dobro do primeiro com metade do segundo; a soma do triplo do primeiro com o terceiro e o terceiro elevado ao cubo.
18. Todo restaurante, embora por lei não possa obrigar o cliente a pagar, cobra 10% de comissão para o empregado de mesa. Crie um programa  que leia o valor gasto com despesas realizadas em um restaurante e imprima o valor da gorjeta e o valor total com a gorjeta.
19. Em épocas de pouco dinheiro, os comerciantes estão procurando aumentar suas vendas oferecendo desconto. Faça um programa que possa entrar com o valor de um produto e imprima o novo valor tendo em vista que o desconto foi de 9%. Além disso, imprima o valor do desconto.
20. Seja uma sequência A,B,C, ... determinando um Progressão Aritmética \(P.A.\), o termo médio \(B\) de uma P.A. é determinado pela média aritmética de seus termos, sucessor \(C\) e antecessor \(A\). Com base neste enunciado construa um programa que calcule o termo médio \(B\) através da formula  B= \(A + C\)/2

