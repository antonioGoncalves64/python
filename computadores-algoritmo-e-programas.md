# Computadores, algoritmo e programas

### Slides PowerPoint

{% file src=".gitbook/assets/computadores-algoritmos-programas.pdf" caption="Slides Computadores, Algoritmos e Programas" %}

## O que é um Computador

Um computador  é uma artefacto que podem diferir em  tamanho, aparência e custo,  mas que partilham  partilham quatro características fundamentais: são **automáticos, universais, electrónicos e digitais**.

### Automático

Um computador uma vez alimentado com a informação necessária, trabalha por si só, sem a intervenção humana.  isto é, uma vez o trabalho começado, ele será levado até ao final sem a intervenção humana. Para isso, o computador recebe um programa.

### Universal

Pode efectuar qualquer tarefa cuja solução possa ser expressa através de um programa.

### **Electrónico**

É composto por  componentes  responsáveis pela grande velocidade das operações efectuadas por um computador.

### **Digital**

Toda a informação contida num computador é expressa por duas grandezas discretas, normalmente referidas como sendo 0 e 1 ou falso e verdadeiro.

{% hint style="info" %}
Por exemplo, num computador o símbolo **“J”**, poder ́a ser representado por **1001010.**
{% endhint %}

## O que é um Algoritmo

 Um algoritmo é uma sequência finita de instruções bem definidas e não ambíguas, cada uma das quais pode ser executada mecanicamente num período de tempo finito com uma quantidade de esforço finita. A compreensão do conceito de algoritmo é relevante porque um programa corresponde a um algoritmo escrito numa linguagem que é entendida pelo computador, chamada uma linguagem de programação.

{% hint style="info" %}
**Sequência finita de instruções** quer dizer que existe uma ordem pela qual as instruções aparecem no algoritmo, e que estas instruções são em numero finito.
{% endhint %}

{% hint style="info" %}
O significado de cada uma das instruções é claro, não havendo lugar para múltiplas interpretações do significado de uma instrução.
{% endhint %}

{% hint style="info" %}
A execução das instruções não requer imaginação por parte do executante.
{% endhint %}

Um algoritmo está sempre associado com um dado objectivo, ou seja, com a solução de um dado problema. A execução das instruções oes do algoritmo garante que o seu objectivo é atingido.

### Exemplo de um Algoritmo

![](.gitbook/assets/picture-1.png)

#### **Rebuçado de Ovos**

* 500 g de açúcar; 
* 2 colheres de sopa de amêndoas peladas e raladas; 
* 5 gemas de ovos; 
* 250 g de açúcar para a cobertura; e farinha.

> Leva-se o açúcar ao lume com um copo de ́agua e deixa-se ferver até fazer ponto de pérola. Junta-se a amêndoa e deixa-se ferver um pouco. Retira-se do calor e adicionam-se as gemas. Leva-se o preparado novamente ao lume e deixa-se ferver até se ver o fundo do tacho. Deixa-se arrefecer completamente. Em seguida, com a ajuda de um pouco de farinha, molda-se a massa de ovos em bolas. Leva-se o restante açúcar ao lume com 1 dl de agua e deixa-se ferver até fazer ponto de rebuçado. Passam-se as bolas de ovos por este açúcar e põem-se a secar sobre uma pedra untada, após o que se embrulham em papel celofane de varias cores.

## O que é um Programa e uma Linguagem de Programação

Um algoritmo, escrito de modo a poder ser executado por um computador, tem o nome de programa. Por sua vez uma linguagem de programação é uma linguagem utilizada para escrever programas de computador. Existem muitos tipos de linguagens de programação. De acordo com as afinidades que estas apresentam com o modo como os humanos resolvem problemas, podem ser classificadas em linguagens máquina, linguagens “Assembly” e linguagens de alto nível.

### Exemplo de um Programa em Linguagem Máquina

```python
01001000 01100101 01101100 01101100 01101111 00100000 
01010111 01101111 01110010 01101100 01100100
```

{% hint style="info" %}
Códigos numéricos associados a operações básicas  
Linguagem específica de cada micro-processador  
Única linguagem directamente executável pelo computador  
Difícil escrever programas diretamente em código máquina  
Concebida para facilitar a implementação usando circuitos eletrónicos
{% endhint %}

### Exemplo de um Programa em Assembly

```python
;------------------------------------------------------------
FibonacciByMemory PROC 
; Receives: ECX as input n 
; Returns: EAX as nth Fibonacci number calculated
;------------------------------------------------------------
   mov   eax,1         
   mov   previous,0         
   mov   current,0         
L1:
   add eax,previous       ; eax = current + previous      
   mov edx, current       ; previous = current
   mov previous, edx
   mov current, eax
loop   L1
   ret
FibonacciByMemory ENDP
```

{% hint style="info" %}
Representação do código máquina usando mnemónicas   
Mais legível do que a linguagem máquina   
Pode ser traduzida automaticamente para código máquina   
Continua a ser específica para cada micro-processador   
Exige programação lenta, fastidiosa e susceptível a erros  
Usada apenas em contextos muito específicos
{% endhint %}

### Exemplo de um Programa  em Python

_Programa Hello Word_

```python
# This program prints Hello, world!
print('Hello, world!')
```

### Exemplo de um Programa em C

_Programa Hello Word_

```python
#include <stdio.h>
int main() {
   // printf() displays the string inside quotation
   printf("Hello, World!");
   return 0;
}
```

{% hint style="info" %}
Mais próximas da formulação matemática dos problemas  
Permitem o desenvolvimento de programas mais rápido  
Facilitam a deteção e a correção de erros  
Permitem desenvolver programas independentes do processador específico em cada computador
{% endhint %}

## Exercícios Práticos

Coleção de de exercicios sobre algoritmia proposto

### Problema 1

{% tabs %}
{% tab title="Problema" %}
```bash
Faça um algoritmo para fritar um ovo.
```
{% endtab %}

{% tab title="solução" %}
```fsharp
preparar frigideira, ovo, óleo e sal 
colocar óleo na frigideira 
acender o fogo
colocar a frigideira no fogo 
esperar o óleo aquecer 
por  o ovo
retirar quando pronto 
```
{% endtab %}
{% endtabs %}

### Problema 2

{% tabs %}
{% tab title="problema" %}
```python
Faça um algoritmo para planear um fim-de-semana
```
{% endtab %}

{% tab title="solução" %}
```css
vejo a previsão do tempo; 
se (fizer sol) 
vou à praia; 
senão
vou estudar; 
almoçar 
ver televisão 
dormir
```
{% endtab %}
{% endtabs %}

### Problema 3

{% tabs %}
{% tab title="problema" %}
```python
Pedir 2 notas e calcular média ponderada com pesos 2 e 3 
respetivamente e escreva o valor da média.    
```
{% endtab %}

{% tab title="solução" %}
```text
Variaveis 
  N1, N2, Media:real

inicio 

  escreval("Digite a nota 1")
  leia(N1) 
  escreval("Digite a nota 2")
  leia(N2) 
 Media <- (N12+N23)/5 
 escreval(Media)

Fimalgoritmo
```
{% endtab %}
{% endtabs %}

### Restantes problemas

1. Pedir o valor base do salário e o valor de vendas. Em seguida calcule o valor do salário tendo em conta que o salário é base + 4% das vendas. Apresente o valor do salário.
2. Pedir 4 notas e calcular média ponderada com pesos 2, 3, 4 e 6 respetivamente. Caso a média seja menor que 7 exibir "reprovado" juntamente com o valor da média, caso contrário exibir “Aprovado" juntamente com o valor da média.
3. Solicite os valores A e B.  Se A for igual a B calcule a soma de A com B, caso contrário calcule o produto.
4. Pedir o tempo de serviço e salário de um funcionário, caso o tempo for menor que 10 anos o aumento será de 10%, caso contrário o aumento será de 25%
5. Pedir 4 notas e calcular média ponderada com pesos 2, 3, 4 e 6 respetivamente. Caso a média seja menor que 7 exibir "reprovado" juntamente com o valor da média, caso contrário exibir “Aprovado" juntamente com o valor da média
6. Solicite um valor X em seguida apresente os  X primeiros valores inteiros.
7. Faça um algoritmo para planear um fim-de-semana.
8. A imobiliária Remus vende apenas terrenos retangulares. Faça um algoritmo para ler as dimensões de um terreno e depois exibir a área do terreno. 
9. A padaria SuperPão vende uma certa quantidade de papos secos e uma quantidade de broas em cada dia. Cada papo seco custa 0,15 Euros e  cada  broa custa 1,50 Euros . No final do dia, o dono quer saber quanto arrecadou com a venda dos pães, e quanto deve guardar numa conta de poupança \(10% do total arrecadado\). Com base nestes fatos, faça um algoritmo para ler as quantidades de papos e de broas, e depois calcular os dados solicitados. 
10. Escreva um algoritmo para ler o nome e a idade de uma pessoa, e exibir quantos dias de vida ela possui. Considere sempre anos completos, e que um ano possui 365 dias. Ex: uma pessoa com 19 anos possui 6935 dias de vida.
11. Um condutor deseja colocar no seu tanque X euros de gasolina. Escreva um algoritmo para ler o preço do litro da gasolina e o valor que deve ser pago, e exibir quantos litros ele armazenou no tanque. 
12. Entrar com o dia e o mês de uma data e informar quantos dias se passaram desde o início do ano. Esqueça a questão dos anos bissextos e considere sempre que um mês possui 30 dias. 
13. Uma fábrica de camisas produz os tamanhos pequeno, médio e grande, cada uma sendo vendida respectivamente por 30, 45 e 75 Euros. Faça um algoritmo em que o utilizador forneça a quantidade de camisas pequenas, médias e grandes referentes a uma venda, e informe quanto será o valor arrecadado. 
14. Faça um algoritmo para ler o salário de um funcionário e aumentá-Io em 15%. Após o aumento, desconte 8% de impostos. Imprima o salário inicial, o salário com o aumento e o salário final. 
15. Alguns países medem temperaturas em graus Celsius, e outros em graus Fahrenheit. Faça um algoritmo para ler uma temperatura Celsius e imprimi-Ia em Fahrenheit \(pesquise como fazer este tipo de conversão\). 
16. A empresa Sorus paga Euros 50,00 por hora normal de trabalho, e Euros 90,00 por hora extra. Faça um algoritmo para calcular e imprimir o salário bruto e o salário líquido de um determinado funcionário. Considere que o salário líquido é igual ao salário bruto descontando-se 25% de impostos. 
17. Faça um algoritmo que receba duas notas, calcule e mostre a média ponderada dessas notas, considerando peso 2 para a primeira nota e peso 3 para a segunda nota.
18. Faça um algoritmo que receba o preço de um produto, calcule e mostre o novo preço, sabendo-se que este sofreu um desconto de 10%. 
19. Faça um algoritmo que receba o peso de uma pessoa, calcule e mostre: o novo peso se a pessoa engordar 15% sobre o peso digitado e o novo peso se a pessoa emagrecer 20% sobre o peso digitado. 
20. Faça um algoritmo permite calcular o máximo divisor comum – mdc\(m,n\) – entre dois números inteiros.  
21. Faça um algoritmo para receber um número qualquer e informar na tela se é par ou ímpar. 
22. Faça um algoritmo que leia dois valores inteiros A e B se os valores forem iguais deverá se somar os dois, caso contrário multiplique A por B. Ao final de qualquer um dos cálculos mostrar seu conteúdo na tela. 
23. Encontrar o dobro de um número caso ele seja positivo e o seu triplo caso seja negativo, imprimindo o resultado. 
24. Escreva um algoritmo que leia dois valores e mostre-os em ordem decrescente. 
25. Escreva um algoritmo que leia três valores e mostre-os em ordem decrescente. 
26. Escreva um algoritmo que leia dois valores e mostre-os em ordem crescente. 
27. Escreva um algoritmo que leia três valores e mostre-os em ordem crescente. 
28. O IMC – Índice de Massa Corporal é um critério da Organização Mundial de Saúde para dar uma indicação sobre a condição de peso de uma pessoa adulta. A fórmula é IMC = peso / \(altura \)2  Elabore um algoritmo que leia o peso e a altura de um adulto e mostre sua condição de acordo com  os seguintes valores: Abaixo de 18,5 Abaixo do peso;  Entre 18,5 e 25 Peso normal:  Entre 25 e 30 Acima do peso e  Acima de 30 obeso.
29. Escreva um algoritmo que leia 3 notas obtidas por um aluno nas 3 verificações e a média dos exercícios que fazem parte da avaliação, e calcule a média de aproveitamento, utilizando a seguinte fórmula. Nota Final := \(nota1 + nota 2  _2 + nota 3_  3 \)/6
30. Imprima todos os números pares no intervalo de 1 a 30. 
31. Imprima o somatório de todos os números inteiros no intervalo de 0 \(zero\) a N. Onde N deve ser um número inteiro maior ou igual a zero e será escolhido pelo utilizador. 
32. Desenvolver um algoritmo que efetue a soma de todos os números ímpares que são múltiplos de três e que se encontram no conjunto dos números de 1 até 500. 
33. Desenvolver um algoritmo que leia a altura de 15 pessoas. Este programa deverá calcular e mostrar: A menor altura do grupo e a maior altura do grupo; 
34. Desenvolver um algoritmo que leia um número não determinado de valores e calcule e escreva a média aritmética dos valores lidos, a quantidade de valores positivos, a quantidade de valores negativos e o percentual de valores negativos e positivos. 
35. Escrever um algoritmo que gera e escreve os números ímpares entre 100 e 200. 
36. Escreva um algoritmo que leia um valor inicial A e imprima a sequência de valores do cálculo de A! e o seu resultado. Ex: 5! = 5 X 4 X 3 X 2 X 1 = 120 



