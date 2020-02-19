# Listas

## Introdução

As listas em Python são idênticas aos tuplos, mas com uma diferença fundamental: as listas são mutáveis, i.e., os seus elementos podem ser modificados, adicionados ou removidos.

A definição de listas é também semelhante à definição de tuplos, em que se utilizam `[]` em vez de `()`. Em notação BNF: 

```python
<lista> ::= [] | [<elementos>]

<elementos> ::= <elemento> | <elemento>, <elementos>

<elemento> ::= <expressão> | <tuplo> | <lista> | <dicionário>
```

Notar que, dada a inexistência de ambiguidade em relação ao uso de `[]`, contrariamente ao que acontece com o uso de `()` como vimos no caso da representação de tuplos, as listas com um elemento não contêm `,` no final.

Exemplos, incluindo o uso de algumas funções pré-definidas: 

```python
>>> lst1 = [2, 3, 5, 7]
>>> lst2 = [0, 1, 1, 2, 3, 5, 8]
>>> lst1 + lst2
[2, 3, 5, 7, 0, 1, 1, 2, 3, 5, 8]
>>> lst1*5
[2, 3, 5, 7, 2, 3, 5, 7, 2, 3, 5, 7, 2, 3, 5, 7, 2, 3, 5, 7]
>>> 3*lst1
[2, 3, 5, 7, 2, 3, 5, 7, 2, 3, 5, 7]
>>> lst2[2:5]
[1, 2, 3]
>>> del(lst2[2:5])
>>> lst2
[0, 1, 5, 8]
>>> 8 in lst2
True
>>> 8 in lst1
False
>>> 8 not in lst1
True
>>> len(lst1)
4
>>> list((8,9,4))
[8, 9, 4]
>>> list('Fundamentos')
['F', 'u', 'n', 'd', 'a', 'm', 'e', 'n', 't', 'o', 's']
>>> lst1[1] = 'FP'
>>> lst1
[2, 'FP', 5, 7]
>>>
```

Associação de nomes e listas: 

```python
>>> lst1 = [2, 3, 5, 7]
>>> lst2 = lst1
>>> lst1[2] = 6
>>> lst1
[2, 3, 6, 7]
>>> lst2
[2, 3, 6, 7]
>>> lst2[1] = 4
>>> lst1
[2, 4, 6, 7]
>>>
```

## Passagem por valor e por referência

É comum falarmos em passagem de argumentos por valor e por referência quando estudamos linguagens de programação. Em Python todas as entidades são objectos e esses objectos são passados como argumentos por referência. No entanto as referências são passadas por valor. Numa primeira análise pode parecer confuso, mas basta pensar na passagem de parâmetros como associações entre nomes e objectos/valores.

Neste contexto uma referência denota a localização na memória em que se encontra um dado valor/objecto. A associação de um nome a um valor pode ser visto aqui como a atribuição da referência do valor/objecto ao nome.

Na passagem de argumentos por valor, os valores associados aos argumentos formais de uma função são distintos dos valores associados aos parâmetros concretos utilizados na invocação da função. Ou seja, as referência ou localizações na memória são distintas.

Na passagem de argumentos por referência dos objectos, os valores associados aos argumentos formais de uma função são os mesmos que os valores associados aos parâmetros concretos na invocação da função. Ou seja, as referências ou localizações na memória são as mesmas. Isto implica que alterações aos valores/objectos realizadas pela função são observáveis fora do ambiente da mesma. No entanto essas alterações apenas são possíveis em Python sobre objectos mutáveis, como as listas. Se os objectos/valores forem imutáveis, como os tuplos ou as cadeias de caracteres ou os números, podemos ficar com a falsa impressão de que a passagem de argumentos é por valor.

Antes de passarmos a alguns exemplos nota-se que distingue-se aqui _passagem por referência dos objectos_ de _passagem por referência_ no sentido em que, em geral, a passagem por referência permite muitas vezes alterar numa função o valor da referência em ambientes externos à função, o que em Python corresponderia a uma função alterar a associação entre nomes e objectos fora do ambiente da mesma. Como vimos em aulas anteriores, este não é o caso em Python.

```python
>>> def addtoall(t, x):
...     for l in t:
...         l.append(x)
...     t = ()
... 
>>> t = ([], [])
>>> addtoall(t, 2)
>>> addtoall(t, 3)
>>> addtoall(t, 5)
>>> t
([2, 3, 5], [2, 3, 5])
>>>
```

Neste exemplo pode observar-se que o argumento `t` é passado por referência para o valor/objecto associado, caso contrário as alterações sobre as listas não seriam observáveis fora do ambiente da função. No entanto a referência em si foi passada por valor uma vez que a atribuição no final da função não tem efeito no ambiente global, facto que já tínhamos visto quando analisámos os ambientes e a associação de nomes.

## Exercícios práticos

1. Defina a função `indices_pares` que recebe como argumento uma lista de números inteiros w e devolve a lista dos elementos de w em posições pares. Exemplo:  indices\_pares\(\[4,3,7,1,2,9\]\); Out\[34\]
2. Dada uma variável representando uma cadeia de DNA, “ATTATTATTATTA”, faça um programa que: substitua todos os Ts por Cs;  substitua  os primeiros 2 As por Gs e encontre a posição do primeiro .
3. Defina a função prod\_lista que recebe como argumento uma lista de números inteiros e devolve o produto dos seus elementos. Exemplo:  prod\_lista\(\[2,4,6\]\)  saida : 48
4. Defina a função contem\_parQ que recebe como argumento uma lista de números inteiros w e devolve True se w contém um número par e False em caso contrário.  Exemplos: contem\_parQ\(\[3,5,7,9,11\]\)  saída; False;  contem\_parQ\(\[3,4,7,9,11\]\); saída: TrueDefina a função
5. pertenceQ que recebe como argumentos uma lista de números inteiros w e um número inteiro n e devolve True se n ocorre em w e False em caso contrário. Exemplo: pertenceQ\(\[1,2,3,4\],5\); saída:  False;  pertenceQ\(\[1,2,3,4\],2\); saída: True;
6. Defina a função nat\_listaQ que recebe com argumento uma lista e devolve True se a lista for constituida exclusivamente por números naturais e False em caso contrário. In \[121\]: nat\_listaQ\(\[1,2,3,-1\]\) Out\[121\]: False In \[122\]: nat\_listaQ\(\[1,2,3,4\]\) Out\[122\]: True
7. Defina a função escolhe\_pares que recebe como argumento uma lista de números inteiros w e devolve a lista dos elementos pares de w . In \[130\]: escolhe\_pares\(\[1,2,3,4,5,6,7,8\]\) Out\[130\]: \[2, 4, 6, 8\];
8. Defina a função retira\_negativos que recebe como argumento uma lista de números inteiros e devolve a lista resultante de retirar todos os números negativos. In \[135\]: retira\_negativos\(\[1,2,3,-4,5,-6\]\) Out\[135\]: \[1, 2, 3, 5\]
9. Defina a função prim\_alg que recebe como argumento um número natural n e devolve o primeiro algarismo \(o mais significativo\) na representação decimal de n . In \[215\]: prim\_alg\(8935\) Out\[215\]: 8
10. Defina a função permutacao que recebe como argumentos duas listas w1 e w2 e devolve True se w2 for permutação de w1 , e devolve False em caso contrário. In \[191\]: permutacao\(\[1,2,3\],\[3,2,1\]\) Out\[191\]: True In \[193\]: permutacao\(\[1,1,2,3\],\[3,2,1\]\) Out\[193\]: False
11. Defina a função intercala que recebe como argumentos duas listas w1 e w2 e devolve a lista resultante de intercalar os elementos de w1 com os de w2 . In \[11\]: intercala\(\[1,3,5\],\[2,4,6\]\) Out\[11\]: \[1, 2, 3, 4, 5, 6\] In \[12\]: intercala\(\[1,3,5,7\],\[2\]\) Out\[12\]: \[1, 2, 3, 5, 7\]
12. Defina a função maximo que recebe como argumento uma lista não vazia de números inteiros e devolve o seu máximo. In \[203\]: maximo\(\[14,-1,5,19,0\]\) Out\[203\]: 19
13. Defina a função pos\_max que recebe como argumento uma lista de números inteiro e devolve a lista das posições onde ocorre o máximo da lista. In \[208\]: pos\_max\(\[1,2,3,1,2,3\]\) Out\[208\]: \[2, 5\]
14. Escreva uma função chamada cumsum que receba uma lista de números e retorne a soma cumulativa; isto é, uma nova lista onde o i-ésimo elemento é a soma dos primeiros i+1 elementos da lista original. Por exemplo: t = \[1, 2, 3\]; cumsum\(t\) ; saída: \[1, 3, 6\];
15. Escreva uma função chamada chop que tome uma lista alterando-a para remover o primeiro e o último elementos. Por exemplo: t = \[1, 2, 3, 4\]; chop\(t\) ; saída: \[2, 3\]
16. Escreva uma função chamada is\_sorted que tome uma lista como parâmetro e retorne True se a lista estiver classificada em ordem ascendente, e False se não for o caso.  Por exemplo: is\_sorted\(\[1, 2, 2\]\); True e is\_sorted\(\['b', 'a'\]\); False
17. Escreva uma função chamada has\_duplicates que tome uma lista e retorne True se houver algum elemento que apareça mais de uma vez

## Exercícios laboratoriais

1. Escreva uma função chamada middle que receba uma lista e retorne uma nova lista com todos os elementos originais, exceto os primeiros e os últimos elementos. Por exemplo:  t = \[1, 2, 3, 4\]; middle\(t\);   saída: \[2, 3\]
2. Dada uma string “GCTAATGCTTGGTTAATTCCTTGGAC”, faça um programa que imprima a posição inicial de cada uma das sequências TT
3. Defina a função `inverte_lista` que recebe como argumento uma lista e devolve essa lista invertida.
4. Defina a função `triangulo` que recebe como argumento um número natural n e devolve uma lista em que o primeiro elemento é a lista `[1]`, o segundo elemento é a lista `[1, 2]` e assim sucessivamente até a n.In \[58\]. Exemplo: triangulo\(4\), saida: \[\[1\], \[1, 2\], \[1, 2, 3\], \[1, 2, 3, 4\];
5. Defina a função conta que recebe como argumentos uma lista de números inteiros w e um número inteiro x e devolve o número de ocorrências de x em w . Exemplo:  conta\(\[1,2,3,2,1,2\],1\) saída:  2
6. Defina a função todos\_imparesQ que recebe como argumento uma lista de números inteiros w e devolve True se w contém apenas números ímpares e False em caso contrário. Exemplo: todos\_imparesQ\(\[3,5,7,9,11\]\); saída True;  todos\_imparesQ\(\[3,4,7,9,11\]\); saída:  False
7. Defina a função int\_listaQ que recebe com argumento uma lista e devolve True se a lista for constituida exclusivamente por números inteiros e False em caso contrário. In \[116\]: int\_listaQ\(\[1,2,-3,4,9\]\) Out\[116\]: True In \[117\]: int\_listaQ\(\[1.1,3,-3\]\) Out\[117\]: False
8. Defina a função int\_lista\_listaQ que recebe com argumento uma lista e devolve True se a lista for constituida exclusivamente por listas de números inteiros e False em caso contrário. In \[126\]: int\_lista\_listaQ\(\[\[1,2,3\],\[4,5,6\]\]\) Out\[126\]: True In \[127\]: int\_lista\_listaQ\(\[\[1,2,3\],\["ola",3\]\]\) Out\[127\]: False In \[128\]: int\_lista\_listaQ\(\[1,\[1,2,3\],\[4,5,6\]\]\) Out\[128\]: False;
9. Defina a função int\_matrizQ que recebe como argumento uma lista m e devolve True se m for uma matriz de números inteiros e False em caso contrário. In \[138\]: int\_matrizQ\(\[\[1,2\],\[4,5\],\[7,8\]\]\) Out\[138\]: True In \[139\]: int\_matrizQ\(\[\[1,2\],\[4\],\[7,8\]\]\) Out\[139\]: False In \[141\]: int\_matrizQ\(\[\[1,2\],\[4\],7\]\) Out\[141\]: False;
10. Defina a função div que recebe como argumentos dois números naturais m e n e devolve o resultado da divisão inteira de m por n . Neste exercício não pode recorrer às operações aritméticas de multiplicação, divisão e resto da divisão inteira. In \[217\]: div\(7,2\) Out\[217\]: 3
11. Defina a função media\_digitos que recebe como argumento um número natural e devolve a média dos seus digitos. In \[213\]: media\_digitos\(14276\) Out\[213\]: 4.0
12. Defina função comprimento que recebe como argumento uma lista e devolve o seu comprimento. Não pode, como é óbvio, recorrer à função len. In \[195\]: comprimento\(\[2,3,5,2,2\]\) Out\[195\]: 5
13. Defina a função apaga que recebe como argumentos uma lista de inteiros w e um número inteiro k e devolve a lista que resulta de apagar de w todas as ocorrências de k . In \[199\]: apaga\(\[1,2,1,3,1,4,1,5\],1\) Out\[199\]: \[2, 3, 4, 5\]
14. Defina a função lposicoes que recebe como argumentos uma lista de números inteiros w e um número inteiro k e devolve a lista das posições em que k ocorre em w . In \[206\]: lposicoes\(\[1,2,3,4,12,2,4,3,2\],2\) Out\[206\]: \[1, 5, 8\]
15. Defina a função ind\_pares que recebe como argumento uma lista de listas de números inteiros w={w1,...,wn} e devolve a lista r={r1,...,rn} em que ri é composta pelas posições dos números pares em wi . In \[35\]: pos\_pares\(\[\[1,2,3\],\[4,5,6\],\[7,8,9,10\]\]\) Out\[35\]: \[\[1\], \[0, 2\], \[1, 3\]\]
16. Escreva uma função chamada nested\_sum que receba uma lista de listas de números inteiros e adicione os elementos de todas as listas aninhadas. Por exemplo: t = \[\[1, 2\], \[3\], \[4, 5, 6\]\]; nested\_sum\(t\); saída: 21
17. Escrever no monitor os números inteiros múltiplos de 5 de um intervalo de números inteiros introduzidos pelo utilizador.

