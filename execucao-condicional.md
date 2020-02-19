# Execução condicional

## Introdução

Para desenvolver programas complexos, é importante que possamos especificar a execucao condicional de instruções: devemos ter a capacidade de decidir se uma instrução ou grupo de instruções deve ou não ser executado, dependendo do valor de uma condição.

A execução condicional  permite decidir, durante a execução do programa, se uma sequência de instruções deve ou não ser executada. Em **Python** a instrução que permite a execução condicional é desiganda por **`if.`**

A instrução **`if`** permite a selecção entre duas ou mais alternativas.  A sintaxe em notação **BNF** é: 

```sql
<instrução if> ::=
    if <condição>: NEWLINE
    <bloco de instruções>
    <outras alternativas>*
    {<alternativa final>}

<outras alternativas> ::=
    elif <condição>: NEWLINE
    <bloco de instruções>

<alternativa final> ::=
    else: NEWLINE
    <bloco de instruções>

<bloco de instruções> ::=
    INDENT <sequência de instruções> DEDENT

<condição> ::= <expressão>
```

Em que **`INDENT`** corresponde à indentação de todas as instruções no bloco e **`DEDENT`** ao recuo da indentação após a última instrução no bloco. 

{% hint style="info" %}
 A condição é em geral uma **expressão** que toma um **valor lógico**, embora possa ser uma qualquer **expressão** se tivermos em conta a conversão automática para valores lógicos.
{% endhint %}

## Instrução condicional simples

Ao encontrar uma instrução da forma:

```sql
if <condição>: 
    <instrução 1>
    <instrução 2>
    ..........
    <instrução n>
```

O **Python** comeca por avaliar a expressao  **&lt;condição&gt;** se o valor da expressao **&lt;condição&gt;** for **True**, o Python executa as instruções correspondentes a **&lt;instrucão 1&gt;  ....   &lt;instrução n&gt;** se for  **False**, o **Python** nao faz mais nada relativamente a esta instrucao **if**.  

A seguinte interacção apresenta o uso da instrução if na  versão apresentada. **Notar a indentação.**

```python
idade = int(input("Digite a sua idade? "))
msg = 'Maior'

if idade < 18:
    msg ='Jovem'

print (msg)
```

A  seguinte interacção  **não corresponde** ao  uso da instrução if pois falta o a identação do bloco de instruções a seguir a condição.

```python
>>>idade = int(input("Digite a sua idade? "))
>>>msg = 'Maior'

>>>if idade < 18:
>>>msg ='Jovem' #Erro falta a identação para a direita

>>>print (msg)

File "<ipython-input-3-447485422e61>", line 5
    msg ='Jovem' #Erro falta a identação para a direita
      ^
IndentationError: expected an indented block
```

## Instrução condicional binária

Ao encontrar uma instrução da forma:

```sql
if <condição>: 
    <instrução a1>
    ..............
    <instrução an>
else :
    <instrução b1>
    ..............
    <instrução bn>
```

O **Python** comeca por avaliar a expressao  **&lt;condição&gt;** se o valor da expressao **&lt;condição&gt;** for **True**, o **Python** executa as instruções correspondentes a **&lt;instrucão a1&gt;  ....   &lt;instrução an&gt;** se for  **False**, o **Python** executa as instruções correspondentes a **&lt;instrucão b1&gt;  ....   &lt;instrução bn&gt;**.  

A seguinte interacção apresenta o uso da instrução **`if`** na  versão apresentada. Notar mais uma vez a indentação:

```python
idade = int(input("Digite a sua idade? "))
msg = 'Maior'

if idade < 18:
   msg ='Jovem'
else:
   msg ='Maior'

print (msg)
```

A  seguinte interacção  **não corresponde** ao  uso da instrução **`if`** devido a falta de  identação do comando **`else:`**

```python
idade = int(input("Digite a sua idade? "))
msg = 'Maior'

if idade < 18:
   msg ='Jovem'
   else:
    msg ='Maior'


File "<ipython-input-5-8696200507bf>", line 6
    else:
       ^
SyntaxError: invalid syntax
```

## Instrução condicional encadeada

Ao encontrar uma instrução da forma:

```sql
if <condição A>: 
     <instrução a1>
     .............
     <instrução an>
elif <condição b>: 
     <instrução b1>
    .............
     <instrução bn>
elif <condição n>: 
     <instrução n1>
     .............
     <instrução nn>
..................
else :
     <instrução f1>
     .............
     <instrução fn>

```

O **Python** comeca por avaliar a expressão  **&lt;condição A&gt;** se o valor da expressao **&lt;condição A&gt;** for **`True`**, o **Python** executa as instruções correspondentes a **&lt;instrucão a1&gt;  ....   &lt;instrução an&gt;**  e a execução de **`if`** termina. ****Se  o seu valor for   **`False`**, o **Python**  avalia a condição **&lt;condição B&gt;  se for `True`** executa as instruções correspondentes a **&lt;instrucão b1&gt;  ....   &lt;instrução bn&gt;** e a execução de **`if`** termina.  Em caso contrario o **Python** avalia a **** expressão referente a expressão seguinte e assim sucessivamente.  Se todas as condições forem **`False`** o **Python** executa as instruções referente ao bloco final ou seja **&lt;instrucão f1&gt;  ....   &lt;instrução fn&gt;**

A seguinte interacção apresenta o uso da instrução **`if`** na  versão apresentada:

```python
x = int(input('Introduza um número inteiro: '))

if x < 0 and x%2 == 0:
    print(x, 'é negativo e par')
elif x < 0:
    print(x, 'é negativo e ímpar')
elif x%2 == 0:
    print(x, 'é um número par')
else:
    print(x, 'é um número ímpar')
```

## Instrução condicional aninhado

O **`if`** aninhado é  um **`if`**dentro da declaração de um outro **`if`** externo. É necessário saber exatamente a qual **`if`** um determinado **`else`** está ligado, para não ocasionar erro na semântica do programa. A seguinte interacção apresenta o uso da  **`if`** aninhados:

```python
x = int(input("Digite x: "))
y = int(input("Digite y: "))

if x < y:
    print("x e' menor do que y.")
else:
    if x > y:
        print("x e' maior do que y.")
    else:
        print("x e y devem ser iguais.")
```

## Exercícios práticos

1. Crie um programa que lê dois números inteiros distintos e diz qual desses dois números é o maior.
2. Escrever um programa Python que pergunte ao utilizador um número e de seguida calcule o seu valor absoluto.
3. Crie um programa que leia um número inteiro e verifique se o número tem 4 algarismos.
4. Escreva um programa que leia 2 números inteiros do teclado e indique qual deles é o maior.
5. Altere o programa anterior para ler 3 números e indicar o maior. Se os números forem todos iguais o programa também o deverá indicar.
6. Escrever um programa Python que pergunte ao utilizador um número. Dependendo se o número é par ou ímpar, imprima uma mensagem apropriada para o utilizador.
7. Escrever um programa Python que converta uma nota numérica para uma nota qualitativa \(i.e. ' A ', ' B ', ' C', ' d’ou ' F '\), onde os pontos de corte para ' A ', ' B ', ' C' e ' d' são 90, 80, 70 e 60 respectivamente
8. Escreva um programa Python que faça uma advertência tendo e m conta a velocidade de um carro.   Se a velocidade exceder 200 km/h deve escrever "que Loucura, muita veloz!!!". E se o carro se mover em algum lugar entre 70 e 80 km/h deve imprimir "velocidade correta para o seu carro".
9. Escreva um programa em Python que dado o número faça os seguintes testes:
   1. Caso o número seja divisível por 17 e tenha mais do que 12 dígito escreva **Super17**.
   2. Caso a condição anterior falhe teste se o número é divisível por 13 e tenha mais de 10 dígitos. Neste caso deve escrever **Fantástico13**.
   3. Por fim, caso falhe ambas as condições, deve escrever: **Humm, é somente um número aleatório!**
10. Escreva um programa Python que faça a correspondência da idade de um cão para a idade de uma pessoa. Tenha em conta o seguinte algoritmo:
    1. Um cão com um ano corresponde aproximadamente a uma criança de quatorze anos de idade.
    2. Um cão que tem dois anos corresponde a um homem de 22 anos de idade.
    3. Cada ano adicional, do cão, corresponde a cinco anos humanos.
11. Escrever um programa Python que faça a correspondência da das mensagens as condições de temperatura e humidade presente na tabela que se segue.
12. Escreva um programa que leia 3 números inteiros do utilizador, garantindo que todos eles são positivos e diferentes entre si. Se o utilizador tentar introduzir um valor igual a um valor já introduzido, o programa deverá repetir o pedido de introdução do valor.
13. Crie um programa que leia o valor das vendas de uma empresa em 4 anos consecutivos: 2010, 2011, 2012 e 2013. Os valores deverão ser positivos. O programa deverá indicar em quantos anos neste período o valor de vendas cresceu em relação ao ano anterior \(o valor de saída será entre 0 e 3\). Deverá indicar ainda o crescimento percentual entre o ano 2010 e 2013. \(utilizado ciclos\).
14. Crie um programa que lê os coeficientes de uma equação do 2º grau e calcula suas raízes. O programa deve mostrar, quando possível, o valor das raízes calculadas e a classificação das raízes \(imaginárias, única, distintas\);
15. Faça um Programa que leia três números e mostre o maior deles. 
16. Faça um programa que leia um valor e escrever a mensagem É MAIOR QUE 10! se o valor lido for maior que 10, caso contrário escrever NÃO É MAIOR QUE 10!
17. Dados 3 valores x, y e z, verificar se eles podem ser os comprimentos dos lados de um triângulo e, se forem, verificar se é um triângulo equilátero, isósceles ou escaleno.
18. Crie um programa para verificar se um número inteiro positivo é múltiplo de outro. Ambos os números devem ser introduzidos pelo utilizador. Deve verificar se o maior é divisível pelo menor.
19. Crie um programa para verificar se um número inteiro positivo é múltiplo de outro. Ambos os números devem ser introduzidos pelo utilizador. Deve verificar se o maior é divisível pelo menor.

| **TEMPERATURA** | **HUMIDADE** | **MENSAGEM** |
| :--- | :--- | :--- |
| Temperature &gt;= 100 |  | Cancel School, and recommend a good movie |
| Temperature &gt;= 92 | Humidity &gt; 75 | Cancel schoool |
| Temperature &gt; 88 | Humidity &gt;= 85 | Cancel schoool |
| Temperature == 75 | Humidity &lt;= 65 | Encourage students to skip school and enjoy the great outdoors |
| Temperature &lt;= -25 |  | You had better panic, because the world is clearly ending |
| Temperature &lt; 0 |  | Cancel school |

## Exercícios laboratoriais

1. Faça um Programa que peça dois números e imprima o maior deles. 
2. Faça um Programa que leia um valor e escrever se é positivo ou negativo \(considere o valor zero como positivo\).
3. Crie um programa que lê três números distintos e mostra o maior dos 3.
4. Faça um Programa que peça um valor e mostre na tela se o valor é positivo ou negativo. 
5. Faça um Programa que verifique se uma letra digitada é "F" ou "M". Conforme a letra escrever: F - Feminino, M - Masculino, Sexo Inválido. 
6. Faça um Programa que verifique se uma letra digitada é vogal ou consoante. 
7. Faça um programa para a leitura de duas notas parciais de um aluno. O programa deve calcular a média alcançada por aluno e apresentar: 

   A mensagem "Aprovado", se a média alcançada for maior ou igual a sete; 

   A mensagem "Reprovado", se a média for menor do que sete; 

   A mensagem "Aprovado com Distinção", se a média for igual a dez. 

8. Faça um Programa que leia três números e mostre o maior e o menor deles. 
9. Faça um programa que pergunte o preço de três produtos e informe qual produto você deve comprar, sabendo que a decisão é sempre pelo mais barato. 
10. Faça um Programa que leia três números e mostre-os em ordem decrescente.
11. Faça um Programa que peça os 3 lados de um triângulo. O programa deverá informar se os valores podem ser um triângulo. Indique, caso os lados formem um triângulo, se o mesmo é: equilátero, isósceles ou escaleno. Dicas: 
    1. Três lados formam um triângulo quando a soma de quaisquer dois lados for maior que o terceiro; 
    2. Triângulo Equilátero: três lados iguais; 
    3. Triângulo Isósceles: quaisquer dois lados iguais; 
    4. Triângulo Escaleno: três lados diferentes;
12. Faça um programa que calcule as raízes de uma equação do segundo grau, na forma ax2 + bx + c. O programa deverá pedir os valores de a, b e c e fazer as consistências, informando ao usuário nas seguintes situações: 
    1. Se o utilizador  informar o valor de A igual a zero, a equação não é do segundo grau e o programa não deve fazer pedir os demais valores e  termine o programa; 

       Se o delta calculado for negativo, a equação não possui raizes reais. Informe a utilizador e termine o programa; 

    2. Se o delta calculado for igual a zero a equação possui apenas uma raiz real; mostre o resultado;
    3. Se o delta for positivo, a equação possui duas raiz reais; mostre o resultado;
13. Faça um Programa que leia um número inteiro menor que 1000 e imprima a quantidade de centenas, dezenas e unidades do mesmo. 
    1. Notas:
    2. Observando os termos no plural a colocação do "e", da vírgula entre outros. 
    3. Exemplo: 
       1. 326 = 3 centenas, 2 dezenas e 6 unidades 
       2. 12 = 1 dezena e 2 unidades 
14. Faça um Programa para leitura de três notas parciais de um aluno. O programa deve calcular a média alcançada por aluno e apresentar: 
    1. A mensagem "Aprovado", se a média for maior ou igual a 7, com a respectiva média alcançada;
    2. A mensagem "Reprovado", se a média for menor do que 7, com a respectiva média alcançada; 
    3. A mensagem "Aprovado com Distinção", se a média for igual a 10.
15. Faça um programa para um multibanco. O programa deverá perguntar ao utilizador a valor do saque e depois informar quantas notas de cada valor serão fornecidas. As notas disponíveis serão as de 5, 10, 20, 50 e 100 Euros. O valor mínimo é de 10 Euros e o máximo de 600 Euros. Exemplo: Para sacar a quantia de 255 Euros, o programa fornece duas notas de 100, uma nota de 50, uma nota de 5
16. Crie um programa que leia 3 valores reais correspondendo aos 3 lados de um triângulo. O programa deve indicar se esses valores podem criar um triângulo e, em caso afirmativo, que triângulo se trata \(isósceles, escaleno, equilátero\).
17. Escreva um programa que leia 3 notas de um aluno \(teórica, prática e projecto\). As notas deverão estar no intervalo 0-20. A nota final é dada pela soma pesada das notas \(TEOR=50% PRAT=30% PROJ=20%\). O aluno será aprovado se a soma das 3 notas for superior a 30 ou no caso de a nota prática e teórica serem ambas iguais ou superiores a 13. O aluno deverá ser submetido a um exame oral se a nota teórica for 8 ou 9 ou no caso de a média final ser superior a 14. O programa deverá indicar todos os resultados. Para passar o aluno deverá ter uma nota igual ou superior a 8 em ambas as frequências e uma nota igual ou superior a 10 na média das duas frequências \(F\). O programa deverá verificar se os valores introduzidos para as frequências estão no intervalo entre 0 e 20. O trabalho deverá ter um valor entre 0 e 4.
18. Crie um programa que leia 3 notas de um aluno: N1, N2, N3 e indique se o aluno passou à disciplina. Para passar à disciplina o aluno deverá ter uma nota igual ou superior a 8 nas 3 notas e a soma de N1 e N2 deverá ser igual ou superior a 20. As notas deverão estar no intervalo de 0 a 20.
19. O clube Remo irá promover eliminatórias para o próximo festival de natação. Recebendo a idade de um nadador escreve no monitor a sua categoria segundo a tabela seguinte:

| Categoria | Idade |
| :--- | :--- |
| Infantil A | 5 – 7 Anos |
| Infantil B | 8 – 10 Anos |
| Juvenil A | 11 – 13 Anos |
| Juvenil B | 14 – 17 Anos |
| Sénior | 18 - 35 Anos |
| Não pode participar | Outras idades |

