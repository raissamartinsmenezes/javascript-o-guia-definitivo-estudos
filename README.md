# Introdução a Javascript

linguagem de alto nível:
dinâmica:
interpretada:
não tipada:
estilo de programação orientada a objeto e funcional:
depuração de código:

## 1.1 Javascript básica

Um **objeto** é uma coleção de pares **propriedade/valor**

```js

var book = {
    topic: 'Javascript', // topic é a propriedade e tem o valor 'Javascript'
    fat: true            // a propriedade fat tem o valor true
};

```

Para acessar as propriedades do objeto

```js

book.topic  // => 'Javascript'
book['fat'] // => true: outro modo de acessar valores de propriedade 
book.author = 'Jane Austen' // crie uma nova propriedade por meio de atribuição 
book.content = {} // é um objeto vazio sem qualquer propriedade 

```

Javascript também aceita **arrays** (listas indexadas numericamente) de valores: