# Dicionários

Um dicionário é conjunto de pares. em que o primeiro elemento é a chave e o segundo é o valor associado a essa chave. Num dicionário não podem existir dois pares com a mesma chave. Os dicionários são também conhecidos por [mapas ou vectores de associação](https://en.wikipedia.org/wiki/Associative_array) uma vez que mapeiam/associam cada chave em/a um valor.

Os dicionários podem ser implementados recorrendo a [tabelas de dispersão](https://en.wikipedia.org/wiki/Hash_table) ou [árvores binários de pesquisa](https://en.wikipedia.org/wiki/Binary_search_tree), que serão objecto de estudo na disciplina de Algoritmos e Estruturas de Dados.

Em Python existe o tipo [`dict`](https://docs.python.org/3/library/stdtypes.html#typesmapping), um tipo mutável que representa um dicionário. Em BNF temos 

```text
<dicionário> ::= {} | {<pares>}
<pares> ::= <par> | <par>, <pares>
<par> ::= <chave> : <valor>
<chave> ::= <expressão>
<valor> ::= <expressão> | <tuplo> | <lista> | <dicionário>
```

Nota-se que em Python um dicionário vazio é representado por `{}` e que cada chave tem de ser elemento de um tipo imutável.

Tal como acontece com os tuplos e com as listas, também os elementos de um dicionário são referenciados por indexação. No entanto, contrariamente aos primeiros em que os elementos são acedidos por um índice que corresponde à sua posição, num dicionário os elementos são acedidos/referenciados por chave.

Exemplos: 

```text
>>> { 'numero' : 12345, 'disciplina' : 'FP', 'nota' : 16.4 }
{'numero': 12345, 'disciplina': 'FP', 'nota': 16.4}
>>> classificacao = { 'numero' : 12345, 'disciplina' : 'FP', 'nota' : 16.4 }
>>> classificacao['numero']
12345
>>> classificacao['nota'] = 17.5
>>> classificacao
{'numero': 12345, 'disciplina': 'FP', 'nota': 17.5}
>>> classificacao['nota'] += 1
>>> classificacao['nota']
18.5
>>> classificacao['nome']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'nome'
>>>
```

Existem algumas operações sobre [dicionários](https://docs.python.org/3/library/stdtypes.html#typesmapping) pré-definidas. Exemplos: 

```text
>>> classificacao = { 'numero' : 12345, 'disciplina' : 'FP', 'nota' : 16.4 }
>>> 'nome' in classificacao
False
>>> 'nota' in classificacao
True
>>> len(classificacao)
3
>>> del(classificacao['disciplina'])
>>> classificacao
{'numero': 12345, 'nota': 16.4}
>>> 'disciplina' not in classificacao
True
>>> classificacao['nota'] = 17.5
>>> classificacao
{'numero': 12345, 'nota': 17.5}
>>> classificacao['disciplina'] = 'FP'
>>> classificacao
{'numero': 12345, 'disciplina': 'FP', 'nota': 17.5}
>>> for x in classificacao:
...    print (x, '->', classificacao[x])
... 
numero -> 12345
disciplina -> FP
nota -> 17.5
>>> list(classificacao.keys())
['numero', 'disciplina', 'nota']
>>> list(classificacao.values())
[12345, 'FP', 17.5]
>>>
```

### Exemplo: contagem de símbolos

Consideremos um programa que pede ao utilizador uma sequências de caracteres e que conta o número de ocorrências de cada palavra na sequência de caracteres fornecida. Neste exemplo não queremos distinguir minúsculas de maiúsculas e queremos ignorar a pontuação. 

```text
def symbolstable(str):
    import string
    toexclude = string.punctuation + string.whitespace
    
    str = str.lower()        
    table = {}
    
    j = 0
    for i in range(len(str)):
        if str[i] in toexclude:
            if j < i:
                table[str[j:i]] = 1 if str[j:i] not in table else table[str[j:i]] + 1
            j = i+1
    
    if j < i:
        table[str[j:i]] = 1 if str[j:i] not in table else table[str[j:i]] + 1
    
    return table
```

Exemplo de utilização: 

```text
>>> str = 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt.'
>>> symbtable = symbolstable(str)
>>> for k, v in sorted(map(lambda k : (k, symbtable[k]), symbtable), key = lambda x : x[0]):
...     print(k, '->', v)
...
ab -> 1
accusantium -> 1
aperiam -> 1
architecto -> 1
aspernatur -> 1
aut -> 2
beatae -> 1
consequuntur -> 1
dicta -> 1
doloremque -> 1
dolores -> 1
eaque -> 1
enim -> 1
eos -> 1
error -> 1
et -> 1
explicabo -> 1
fugit -> 1
illo -> 1
inventore -> 1
ipsa -> 1
ipsam -> 1
iste -> 1
laudantium -> 1
magni -> 1
natus -> 1
nemo -> 1
nesciunt -> 1
odit -> 1
omnis -> 1
perspiciatis -> 1
quae -> 1
quasi -> 1
qui -> 1
quia -> 2
ratione -> 1
rem -> 1
sed -> 2
sequi -> 1
sit -> 2
sunt -> 1
totam -> 1
unde -> 1
ut -> 1
veritatis -> 1
vitae -> 1
voluptas -> 1
voluptatem -> 3
>>> sorted(map(lambda k : (k, symbtable[k]), symbtable), key = lambda x : x[1], reverse=True)[0:3]
[('voluptatem', 3), ('sit', 2), ('sed', 2)]
>>>
```

### Exemplo: dicionários de dicionários

Vamos processar tweets obtidos através da [Streaming API do Twitter](https://dev.twitter.com/streaming/overview): 

```text
import tweepy, json
from tweepy import StreamListener

# OAuth stuff
consumer_key = "YOUR_CONSUMER_KEY"
consumer_secret = "YOUT_CONSUMER_SECRET"
access_token = "YOUR_ACCESS_TOKEN"
access_token_secret = "YOUR_ACCESS_TOKEN_SECRET"
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)

# Our listener
class FPStreamListener(StreamListener):

  def on_data(self, data):
    decoded = json.loads(data.strip())
    print(decoded['user']['name'], ": ", decoded['text'], sep='')

  def on_error(self, status):
    print(status)

listen = FPStreamListener()

stream = tweepy.Stream(auth, listen)
stream.filter(track = ['portugal'])
```

Um tweet quando é processado na função `on_data` é descodificado como um dicionário de dicionários, e não só!

