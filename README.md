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

Também podemos definir nossos próprios **métodos**. A palavra-chave **this** se refere ao objeto no qual o método é definido: nesse caso, o array de pontos exemplificado acima, observe:

```js

points.dist = function() { // define um método para calcular a distância entre pontos
    var p1 = this[0]; // primeiro elemento do array que chamamos 
    var p2 = this[1]; // segundo elemento do objeto 'this'
    var a = p2.x - p1.x; // diferença em coordenadas X
    var b = p2.y - p1.y; // diferença em coordenadas Y
    return Math.sqrt(a * a + b * b); // o teorema de pitágoras (a * a + b * b = c * c)
}; // Math.sqrt() calcula a raiz quadrada 
points.dist() // => 1.414: distância entre nossos 2 pontos  

```

As instruções javascript também podem incluir **condicionais** e **laços**:

```js

function abs(x) { // uma função para calcular o valor absoluto
    if(x >= 0) { // a instrução if executa esse bloco de código se a instrução for verdadeira
        return x; 
    } else { // a cláusula opcional else executa este bloco se a comparação do if anterior for falsa
        return -x;
    }
}

function factorial(n) { // uma função para calcular fatoriais 
    var product = 1; // começa com o produto de valor 1
    while(n > 1) { // repete as instruções que estão dentro das {}, enquanto a expressão em () for verdadeira
        product *= n; // product = product * n
        n--; // n = n - 1
    } // fim do laço 
    return product; // retorna o produto 
}
factorial(4) // => 24: 1 * 4 * 3 * 2

function factorial2(n) { // outra versão, usando um laço diferente
    var i, product = 1; // começa com o produto de valor 1
    for(i = 2; i <= n; i++){ // incrementa o i automaticamente, de 2 até n
        console.log(n)
        product *= i; // faz este calculo a cada vez
        console.log(product) 
    } return product; // retorna o fatorial 
}
factorial2(5) // => 120: 1 * 2 * 3 * 4 * 5

```

Uma breve demonstração de como definir uma **classe** javascript, neste caso ela irá representar pontos geométricos
bidimensionais. Os objetos que são instâncias dessa classe têm um único método chamado **r()** que calcula a distância
do ponto a partir da origem:

```js

// defini uma função construtora pra inicializar um novo objeto Point
function Point(x, y) { // por convenção, as construtoras começam com letras maiúsculas 
    this.x = x; // a palavra-chave this é o novo objeto que está sendo inicializado 
    this.y = y; // this armazena os argumentos da função como propriedades do objeto 
} // nenhum return é necessário 

// usa uma função construtora com a palavra 'new' para criar instâncias 
var p = new Point(1, 1) // o ponto geométrico é (1, 1)

// define métodos para objetos Point atribuindo-os ao objeto prototype associado à função construtora
Point.prototype.r = function() {
    return Math.sqrt( 
        this.x * this.x + this.y * this.y // este é o objeto point no qual o método é chamado 
    );
};

// Agora o objeto Point b (e todos os futuros objetos Point) herda o método r()
p.r() // => 1.414

```

## 1.2 Javascript do lado do cliente 

### 1.2.1 Exemplo: uma calculadora de empréstimos em Javascript 