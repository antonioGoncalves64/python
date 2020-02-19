# Repetição

## Introdução

Em programação é também frequente repetir instruções em função dos dados de entrada ou em função de determinadas condições durante a execução de um programa. 

Em programação, uma sequencia de instrucoes executada repetitivamente é chamada um **ciclo**.

Um **ciclo** é caracterizado por uma estrutura que controla a execução de um bloco de instruções, desigando por **corpo do ciclo**. A estrutura de controle é  uma expressao do tipo lógico que é avaliada e enquanto a avaliação resultar em **True** o corpo do ciclo é executado.

Cada vez que as instruções do corpo do ciclo sao executadas, dizemos que se efectuou uma passagem pelo ciclo ou uma iteração. Em cada iteração, antes de se executar o corpo do ciclo, a condição  é avaliada e apenas se passa à execução do corpo se essa condição for verdadeira. 

É importante que o ciclo termine, ou por **interrupção** do ciclo a partir do corpo do mesmo, ou garantindo que ao fim de um número finito de passos a condição  é **falsa**. 

{% hint style="info" %}
A existência de ciclos que não terminam, i.e., ciclos infinitos, é um dos erros semânticos mais comuns.
{% endhint %}

Em Python existe duas instruções que permitem especificar ciclos, a instrução **`while`** e a instrução **`for`**. 

A instrução **`while`** permite executar um bloco de instruções enquanto uma dada condição for verdadeira. Note-se que, se a condição for falsa à partida, então o bloco de instruções não é executado de todo. Note-se também que o número de iterações depende inteiramente do valor que a condição de guarda toma em função da execução das instruções no bloco, não sendo possível determinar a priori o número de iterações. 

A sintaxe desta instrução, em notação **BNF**, é: 

```sql
<instrução while> ::=
    while <condição>: NEWLINE
    <bloco de instruções>
```

O fluxo de execução do comando **`while`** é:

1. É avaliada a **`<condição>`**, que deve resultar em **`False`** ou **`True`**.
2. Se o resultado for **`False`**, sai do comando **`while`** e continue o programa executando a próxima linha com um comando.
3. Se o resultado da condição for **`True`**, execute os comandos dentro do corpo do **`while`** e, ao final, retorne ao **passo 1,** isto é a avaliação da condição.

{% hint style="info" %}
Para que o ciclo `while` termine, é necessário que as instruções no corpo do ciclo, i.e., no bloco de instruções, modifiquem o valor da condição para falso ao fim de um número finito de passos.
{% endhint %}

A seguinte interacção apresenta o uso da instrução **`while`**:

```python
soma = 0
x = float(input('Introduza um número (negativo para terminar): '))

while x >= 0:
    soma = soma + x
    x = float(input('Introduza um número (negativo para terminar): '))

print(soma)
```

Estas instruções começam por estabelecer o valor inicial da variável **soma** como sendo **zero**, após o que efectuam a leitura de uma sequência de números inteiros positivos, calculando a sua **soma**. A quantidade de números a ler é desconhecida à partida. Para assinalar que a sequência de números terminou, fornecemos ao **Python** um número especial, no nosso exemplo, qualquer número negativo. Este valor é chamado o **valor sentinela**, porque assinala o fim da sequência a ser lida.

Em alternativa o ciclo **`while`** pode ser interrompido se no bloco de instruções for executada a instrução **`break`**, cuja sintaxe em notação **BNF** é a seguinte: 

```sql
<instrução break> ::= break 
```

Quando a instrução **`break`** é executada, o ciclo cujo corpo inclui a instrução em questão é interrompido, independentemente do valor da condição de guarda. A seguinte interacção apresenta o uso do **`break`** na  instrução **`while`**:

```python
n = int(input('Introduza um número inteiro: '))
d = 2

print('Os pares de divisores de', n, 'são')

print(1,'x',n)
while True:
    if d > n//d:
        break
    elif n%d == 0:
        print(d, 'x', n//d)
    d = d + 1
```

O  corpo do ciclo **`while`** pode ser interrompido se no bloco de instruções for executada a instrução **`continue`**, cuja sintaxe em notação BNF é a seguinte: 

```sql
<instrução continue> ::= break 
```

Quando a instrução **`continue`** é executada, o corpo do ciclo que inclui a instrução em questão é interrompido e volta ao incio do ciclo ou seja a  avaliação da condição de guarda. A seguinte interacção apresenta o uso do **`continue`** na  instrução **`while`**:

```python
n = 5
 2 while n > 0:
 3     n -= 1
 4     if n == 2:
 5         continue
 6     print(n)
 7 print('Loop ended.')
```

{% hint style="info" %}
De um modo geral, o numero de vezes que o corpo do ciclo é executado não pode ser calculado antecipadamente: a condição que especifica o termino do ciclo é testada durante a execucao do próprio ciclo, sendo impossivel saber de antemão como vai prosseguir a avaliação
{% endhint %}

{% hint style="info" %}
Pode acontecer que o corpo do ciclo não seja executado nenhuma vez. Com efeito, a semântica da instrução **`while`** especifica que o valor da expressão que controla a execução do ciclo é calculado antes do inıcio da execução do ciclo. Se o valor inicial desta expressão é **`False,`**o corpo do ciclo nao é executado.
{% endhint %}

A seguinte interacção apresenta o uso da instrução **`while`** em que o  corpo do ciclo não seja executado nehuma vez:

```python
num = int(input('Escreva um inteiro positivo\n?'))
soma = 0

while num > 0 :
    digito = num % 10 
    num = num // 10
    soma = soma + digito

print('Soma dos dígitos: ', soma)
```

Este programa começa por  ler um inteiro positivo atribuindo-o à variável **`num`** e  inicializa o valor da soma dos dígitos \(variável **`soma`**\) para zero, por fim no corpo do ciclo  calcula a soma dos seus dígitos.  se **`num`** for negativo ou igual a 0 o corpo do ciclo nunca é executado.

## Exercícios práticos

1. Escrever um programa que escolha número e em seguida pergunte ao utilizado qual é o seu palpite. O programa deve dar dicas ao utilizador, isto diz-lhe se o palpite é menor ou maior do que o número escolhido. O programa termina quando o utilizador acertar no número. Considere como o valor escolhido 23.
2. Escreva um programa que repetidamente lê números até que o utilizador insira "Done". Uma vez lido "Done", deve imprime no écran, o valor total dos números lidos, a contagem dos números lidos e a média dos números lidos.
3. Escrever um programa Python que pergunte ao utilizador quanto s números pretende ler e de seguida leia os números e mostre a média dos números lidos:
4. Escrever um programa que faça a validação de uma senha de acesso que faça o controle de quantas vezes o utilizador inseriu a senha errada. Se for mais de 3 vezes, imprima:  foi-lhe negado o acesso e encerrar o programa. Se a palavra-passe estiver correta, imprima: “sessão iniciada com sucesso”. e encerre o programa. Considere como senha de acesso a String “dee234”
5. Faça um programa que leia e valide as seguintes informações: 

   a.    Nome: maior que 3 caracteres; 

   b.    Idade: entre 0 e 100; 

   c.    Salário: maior que zero; 

   d.    Sexo: 'f' ou 'm'; 

   e.    Estado Civil: 's', 'c', 'v', 'd';

6. Supondo que a população de um país A seja da ordem de 80 000 habitantes com uma taxa anual de crescimento de 3% e que a população de B seja 200 000 habitantes com uma taxa de crescimento de 1.5%. Faça um programa que calcule e escreva o número de anos necessários para que a população do país A ultrapasse ou iguale a população do país B, mantidas as taxas de crescimento.
7. Faça um programa que imprima na tela os números de 1 a 5, um abaixo do outro. Depois modifique o programa para que ele mostre os números um ao lado do outro.
8. Faça um programa que imprima no visor apenas os números ímpares entre 1 e 50.
9. Faça um programa que receba dois números inteiros e gere os números inteiros que estão no intervalo compreendido por eles.
10. Faça um programa que resolva o seguinte problema. Pretende-se determinar o produto dos números inteiros entre N1 e N2. O programa deverá dar erro se N2 for inferior ou igual a N1 e voltar a pedir estes valores. 
11. Desenhe um programa que resolva o seguinte problema. Pretende-se determinar o maior e o menor número duma sequência de N números inteiros dados pelo utilizador. O valor de N deverá ser superior ou igual a 2. Se não for o seu valor deverá ser pedido novamente até ser introduzido um valor válido.

    A introdução de números deverá terminar quando forem inseridos N números. Nessa altura a aplicação deverá mostrar o valor máximo e mínimo de entre os valores introduzidos. 

12. Faça um programa que resolva o seguinte problema. Pretende-se determinar o maior e o menor número duma sequência de números inteiros dados pelo utilizador. A introdução de números deverá terminar quando for inserido o valor zero e nessa altura a aplicação deverá mostrar o valor máximo e mínimo de entre os valores introduzidos. Deverão ser introduzidos pelos menos dois números. 
13. Faça um programa que resolva o seguinte problema. Pretende-se determinar a média aritmética duma sequência de N números inteiros. A introdução de números deverá terminar quando forem inseridos N números e nessa altura a aplicação deverá mostrar o valor da média. O valor de N deverá ser no mínimo dois caso contrário deverá voltar a ser pedido. 
14. Faça um programa que resolva o seguinte problema. Pretende-se determinar a média aritmética duma sequência de números inteiros. A introdução de números deverá terminar quando for inserido o valor zero. Nessa altura a aplicação deverá mostrar o valor da média. Deverão ter sido introduzidos pelo menos dois números, caso contrário deverá ser mostrado um erro. 
15. Faça um programa que resolva o seguinte problema. Pretende-se determinar a soma dos dígitos dum dado número inteiro positivo. 
16. Faça um programa que resolva o seguinte problema. Pretende-se escrever os primeiros N números da sequência de Fibonacci. A sequência de Fibonacci é a seguinte: 1, 1, 2, 3, 5, 8, 13, 21, ... \(a seguir ao primeiro 1 cada número na sequência é a soma dos dois números anteriores\). 
17. Faça um programa que resolva o seguinte problema. Pretende-se converter um número binário em número decimal. Por exemplo: 100102 =1_2^4+0_2^3+0_2^2+1_2^1+0\*2^0=1810
18. Faça um programa que resolva o seguinte problema. Pretende-se converter um número decimal em número binário. 
19. Faça um programa que resolva o seguinte problema. Pretende-se determinar se um determinado número inteiro positivo é primo. Um número é primo se só for divisível por ele próprio e pela unidade. Por exemplo: 13. Não deverão ser aceites números negativos. Nesse caso a aplicação deverá pedir números até que seja introduzido um número válido. 
20. Faça um programa que resolva o seguinte problema. Pretende-se determinar se um determinado número inteiro é capicua. Um número é capícua se for o mesmo número lido da esquerda para a direita ou da direita para a esquerda. Por exemplo: 202. 
21. Escreva um programa em que o utilizador vai introduzindo as idades dos alunos de uma determinada turma até ser introduzido o número -1. No fim deverá indicar o número de alunos e a média de idades. O programa deverá garantir que apenas são introduzidos números positivos \(com a exceção do -1 final\).
22. Escreva um programa em que o utilizador vai introduzindo números positivos até ser introduzido o valor 0 \(zero\). No fim o programa indicará a percentagem de números pares introduzidos.
23. Escreva um programa para ler as notas de n alunos \(sendo n introduzido pelo utilizador\). As notas deverão estar entre 1 e 5. O programa deverá contar quantos alunos tiveram cada uma das notas possíveis.
24. Escreva um programa que leia 10 números inteiros e indique se um número é igual ao anterior. No final deverá indicar quantos números introduzidos são iguais ao anterior.
25. Escreva um programa que leia n números \(sendo n introduzido pelo utilizador\) e indique se os números são todos iguais.

## Exercícios laboratoriais

1. Escreva um programa que imprime na tela os n primeiros números perfeitos

       Nota: Um número perfeito é aquele que é igual à soma dos seus divisores. Por exemplo, 6 = 1 + 2 + 3. 

2. Um número inteiro é considerado triangular se este for o produto de 3 números inteiros consecutivos, como, por exemplo, 120 = 4 x 5 x 6. Elabore um programa que, após ler um número n do teclado, verifique se n é triangular. 
3. Elabore um programa que leia n valores e mostre a soma de seus quadrados. 
4. faça um programa que leia dois valores x e y, e calcula o valor de x dividido por y, além do resto da divisão. Nota: Não é permitido usar as operações de divisão e resto de divisão do Python \(use apenas soma e subtração\). 
5. faça um programa que calcule o número de dias corridos entre duas datas, para vários pares de datas, considerando a possibilidade de ocorrência de anos bissextos, sendo que: 
   1. A primeira data é sempre a mais antiga 
   2. O ano é fornecido com 4 dígitos 
   3. A data fornecida com ZERO dias é o sinal para encerrar a entrada de dados 
6. Foi realizada uma pesquisa em Lisboa, com um número desconhecido de pessoas. De cada entrevista foram colhidos os seguintes dados: 
   1. Qual o seu clube de futebol de preferência \(1 – Benfica, 2 – Sporting, 3 – Porto, 4 – Outros\) 
   2. Qual o seu salário 
   3. Qual a sua cidade natal \(1 – Lisboa, 2 – Outra\) 
   4. 
7. faça um programa em Python que calcule o valor de Pi, utilizando a fórmula de Leibniz

   π/4 = 1 – 1/3 + 1/5 – 1/7 + 1/9 – 1/11 + 1/13 - ...

   Nota: Adicione parcelas no cálculo até que a diferença de uma interação para a seguinte seja menor do que um valor de erro aceitável x digitado pelo utilizador.

8. Num café, um cliente pode comprar Nuggets apenas em pacotes contendo 6, 9 ou 20 pedaços. Escreva um programa em Python que lê um valor inteiro num e que imprima True se é possível comprar num Nuggets no café, ou Falso, caso contrário. 

   Por exemplo, se num = 44, o programa deve retornar True \(seria um pacote de 6, dois de 9 e 1 um de 20, por exemplo\). Mas se num = 34, o programa deve retornar False. 

9. O quadrado de um número natural n é dado pela soma dos n primeiros números ímpares consecutivos. Por exemplo, 12=1, 22=1+3, 32=1+3+5, 42=1+3+5+7, etc. Escreva um programa que dado um número n, calcule seu quadrado usando a soma de ímpares ao invés de produto. 
10. faça um programa que simula uma calculadora que aceita as seguintes operações: soma, subtração, divisão e multiplicação. O programa inicia pedindo para ao utilizador escolher uma opção do menu

    1. Somar
    2. Subtrair
    3. Dividir
    4. Multiplicar 
    5. Sair 

    Ao escolher a opção, o programa solicita os dois números a serem operados \(exceto se a opção escolhida for a 5\), efetua a operação, mostra o resultado na tela e volta para o menu para que o utilizador escolha outra opção. 

11. Escreva um programa que imprime na tela os n primeiros números perfeitos. Um número perfeito é aquele que é igual à soma dos seus divisores. Por exemplo, 6 = 1 + 2 + 3.
12. Um número inteiro é considerado triangular se este for o produto de 3 números inteiros consecutivos, como, por exemplo, 120 = 4 x 5 x 6. Elabore um programa que, após ler um número n do teclado, verifique se n é triangular.
13. Faça um programa que leia dois valores x e y, e calcula o valor de x dividido por y, além do resto da divisão. Não é permitido usar as operações de divisão e resto de divisão do Python \(use apenas soma e subtração\).
14. Crie um programa que lê dois números inteiros e faz a multiplicação sem utilizar o operador de multiplicação \*.
15. Escreva um programa para imprimir os números inteiros entre 1 e 10 na mesma linha, primeiro em ordem crescente e depois em ordem decrescente \(utilizado ciclos\).
16.  Escreva um programa que peça ao utilizador um nome e um número inteiro \(entre 1 e 20\). Deverá mostrar esse nome um número de vezes igual a esse valor inteiro.
17.  Escreva um programa que leia n números \(sendo n introduzido pelo utilizador\) e indique se os números são todos iguais.
18.  Escreva um programa que calcule o factorial de um número.
19.  Escreva um programa que some os algarismos de um número.
20.  Escreva um programa para imprimir todos os números inteiros entre dois valores introduzidos pelo utilizador. O programa deverá verificar qual dos dois valores é o maior.
21. Escreva um programa que apresente a tabuada dum número inteiro entre 1 e 9 dado pelo utilizador. Se o número estiver fora dessa gama, o programa deverá dar uma mensagem.
22. Crie um programa que escreva os números inteiros entre 0 e 100 em intervalos \(incremento\) dados pelo utilizador. O intervalo deverá ser um número entre 1 e 10. \(Por exemplo, com intervalos de 4\).
23. Escreva um programa que leia 10 números inteiros introduzidos pelo utilizador e indique o máximo, a média, o mínimo e a soma dos valores.
24. Escreva um programa que leia n números \(sendo n introduzido pelo utilizador\) e indique se os números são todos pares, se são todos ímpares ou se há ambos os tipos.
25. Escreva um programa que apresente todos os números inteiros entre dois números reais introduzidos pelo utilizador.
26. Escreva um programa que some os algarismos de um número.

