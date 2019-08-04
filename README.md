# Introdução a Javascript

> linguagem de alto nível:

> dinâmica:

> interpretada:

> não tipada:

> estilo de programação orientada a objeto e funcional:

> depuração de código:

## 1.1 Javascript básica

Um **objeto** é uma coleção de pares **propriedade/valor**:

```js

var book = {
    topic: 'Javascript', // topic é a propriedade e tem o valor 'Javascript'
    fat: true            // a propriedade fat tem o valor true
};

```

Para acessar as propriedades do objeto:

```js

book.topic  // => 'Javascript'
book['fat'] // => true: outro modo de acessar valores de propriedade 
book.author = 'Jane Austen' // crie uma nova propriedade por meio de atribuição 
book.content = {} // é um objeto vazio sem qualquer propriedade 

```

Javascript também aceita **arrays** (listas indexadas numericamente) de valores:

```js

var primes = [2, 3, 5, 7]; // um array de 4 valores
primes[0] // => 2: primeiro elemento (índice 0) do array
primes.lenght // => 4: quantidade de elementos do array
primes[primes.leght-1] // 7: o último elemento do array
primes[4] = 9 // adiciona um novo elemento por meio de atribuição
primes = [2, 3, 5, 7, 9] // valor 9 adicionado ao índice 4 do array
primes[4] = 11 // ou altera um elemento existente por meio de atribuição
primes = [2, 3, 5, 7, 11] // valor 9 foi substituído pelo novo valor 11
 
```

Os arrays e objetos podem conter outros arrays e objetos:

```js

var points = [ // um array com dois elementos, onde cada elemento é um objeto 
    {x: 0, y: 0}, 
    {x: 1, y: 1}
];

var data = { // um objeto com 2 propriedades 
    trial1: [[1, 2],[3, 4]], // o valor de cada propriedade é um array
    trial2: [[2, 3],[4, 5]], // os elementos dos arrays são arrays 
};

points[1].x - points[0].x // => 1

```

> instruções: normalmente terminam com ponto e vírgula ; e alteram o estado do programa 

> expressões: calcula um valor mas não altera o estado do programa 

As **funções** são blocos de código parametrizados: 

```js

function plus1(x) { // define uma função chamada 'plus1', com parâmetro 'x'
    return x + 1; // retorna um valor 
} // as funções são incluídas em chaves 

plus(y) // => se y = 3, o valor de x é igual a 4

var square = function(x) { // as funções são valores e podem ser atribuídas a variáveis 
    return x * x; // calcula o valor da função 
}; // ; marca o fim da atribuição 

square(plus(y)) // => 16: chama duas funções em uma única expressão 

```

Quando **combinamos** funções com objetos, obtemos **métodos**:

```js

// quando funções recebem as propriedades de um objeto, as chamamos de métodos, todos
// os obejtos de javascript têm métodos: 
var a = []; // cria um array vazio 
a.push(1, 2, 3); // o método push() adiciona elementos em um array
a.reverse(); // outro método, o reverse() inverte a ordem dos elementos

```

