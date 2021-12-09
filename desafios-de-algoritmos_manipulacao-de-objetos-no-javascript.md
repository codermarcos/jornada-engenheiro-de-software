# ⭐ Desafios de algoritmos: Manipulação de Objetos no Javascript

Vamos entender oque é um objeto como podemos usar ele, e como o Javascript trabalha com objetos.

------------------------

- [⭐ Desafios de algoritmos: Manipulação de Objetos no Javascript](#-desafios-de-algoritmos-manipulação-de-objetos-no-javascript)
  - [📚 Oque é um objeto](#-oque-é-um-objeto)
    - [Propriedades](#propriedades)
  - [🐣 O básico sobre objetos](#-o-básico-sobre-objetos)
    - [Como criar um objeto](#como-criar-um-objeto)
    - [Como acessar propriedades e valores de um objeto](#como-acessar-propriedades-e-valores-de-um-objeto)
    - [Adicionar propriedades em um objeto](#adicionar-propriedades-em-um-objeto)
    - [Remover propriedades de um objeto](#remover-propriedades-de-um-objeto)
  - [💪 Desafio para praticar](#-desafio-para-praticar)
    - [Exemplo](#exemplo)
  - [🧠 Objetivo de aprendizagem](#-objetivo-de-aprendizagem)
  - [✔️ Entrega mínima](#️-entrega-mínima)

## 📚 Oque é um objeto 

Para começar precisamos entender oque é um objeto um objetos, como na vida real um objeto é a figura dominante que pode conter atributos/propriedades diferente da vida real esse objeto não é derivado da matéria
e sim apenas uma forma de organizar os dados estrututuradamente. 

Na programação ele é um tipo de dado que pode conter diferentes tipos de dados dentro dele que são chamados de propriedades.

### Propriedades

São variáveis que estão vinculadas a um objeto elas definem as características dele. Por exemplo: Um **carro** ele poderia ter as seguintes propriedades -> **cor**, **placa**, **ano**, **modelo**.

## 🐣 O básico sobre objetos

Um objeto pode ter **qualquer tipo de dado** como valor de suas propriedades como `string`, `number`, `function` inclusive outros objetos:

```javascript
nulos: null, 
numeros: 1,
arrays: [],
objetos: {},
strings: 'alo',
funcoes: () => {},
symbols: Symbol('valor'),
```

Porem o **nome das propriedades** sempre devem ser um tipo primitivo como `string`, `number` ou [`Symbol`](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Symbol).

```javascript
[Symbol('nome')]: 'nome como symbol',
nome: 'nome como string',
[0]: 'nome como number',
```

### Como criar um objeto

Para criar um objeto no Javascript temos algumas formas todas elas são usadas em diferentes momentos.

**Literal** muito usada quando queremos criar um objeto com propriedades já definidas ou um objeto simples.

```javascript
const simples = {} // <- objeto com propriedades nativas
console.log(simples); 
/*
{} [[Prototype]]: Object
  constructor: ƒ Object()
  hasOwnProperty: ƒ hasOwnProperty()
  toString: ƒ toString()
  …
*/

const pessoa = {
  nome: 'Marcos' // <- propriedades 
};
console.log(pessoa); 
/*
{nome: 'Marcos'} [[Prototype]]: Object
constructor: ƒ Object()
  constructor: ƒ Object()
  hasOwnProperty: ƒ hasOwnProperty()
  toString: ƒ toString()
  …
*/

const nomeDaPropriedade = 'cor';
const carro = {
  [nomeDaPropriedade]: 'roxo' // <- propriedade dinamica 
};
console.log(carro); 
/*
{cor: 'roxo'} [[Prototype]]: Object
constructor: ƒ Object()
  constructor: ƒ Object()
  hasOwnProperty: ƒ hasOwnProperty()
  toString: ƒ toString()
  …
*/
```

**Instancia** muito usada quando queremos criar um [objeto global](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects) ou estanciar uma classe.

```javascript
const objeto = new Object(); // <- objeto global com propriedades nativas
/*
{} [[Prototype]]: Object
  constructor: ƒ Object()
  hasOwnProperty: ƒ hasOwnProperty()
  toString: ƒ toString()
  …
*/

const data = new Date(); // <- objeto global para trabalhar com datas
console.log(simples); 
/*
Date Fri Oct 08 2021 12:25:28 GMT-0300 (Brasilia Standard Time) [[Prototype]]: Date
  constructor: ƒ Date()
  getDate: ƒ getDate()
  getDay: ƒ getDay()
  …
*/

const pessoa = new Pessoa('Marcos'); // <- classe personalizada
console.log(pessoa); 
/*
{nome: 'Marcos'} [[Prototype]]: Object
constructor: ƒ Object()
  constructor: ƒ Object()
  hasOwnProperty: ƒ hasOwnProperty()
  toString: ƒ toString()
  …
*/
```

Quando usamos tanto o `new Object()` quanto o `{}` o objeto vem com [propriedades nativas](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object#instance_properties) como [hasOwnProperty](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty) usando para verificar se o objeto tem determinada propriedade ou [toString](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/toString) usado para converter o objeto em string entre outros.

**Puro** para objeto puro ou limpo, ou seja sem nenhuma propriedade nativa, devemos criar um objeto usando o [Object.create](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Object/create):

```javascript
const limpo = Object.create(null); // <- objeto limpo
console.log(pessoa); 
/*
{}
*/
```

Quando vamos iniciar o objeto puro com propriedades precisamos usar um objeto com as mesmas propriedades de retorno do [Object.getOwnPropertyDescriptor](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptor) semelhante quando vamos criar uma propriedade com comportamentos especificos usando o [Objet.defineProperty](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty) elas definem o comportamento de cada propriedade. Da seguinte forma:

```javascript
const pessoa = Object.create(null, {
  nome: { 
    value: 'Marcos' // objeto usado para descrever a propriedade
  },
});
console.log(pessoa); 
/*
{nome:'Marcos'}
*/
```

> ⚠️ **Antenção**: Não pense que porque o objeto não contem as propriedades nativas ele se torna mais rapido. Essa é uma operação custosa como podemos ver abaixo, por isso só deve ser usado em momentos especificos.

{COLOCAR IMAGEM AQUI}

### Como acessar propriedades e valores de um objeto

Para acessar as propriedades de um objeto no Javascript temos algumas formas todas elas são usadas em diferentes momentos.

**Acessar apenas o valor de forma estatica** basta usar o ponto:

```javascript
const pessoa = { nome: 'Marcos' };

console.log( pessoa.nome ); // <- Acessar uma propriedade 
/*
{nome: 'Marcos'} [[Prototype]]: Object
constructor: ƒ Object()
  constructor: ƒ Object()
  hasOwnProperty: ƒ hasOwnProperty()
  toString: ƒ toString()
  …
*/
```

**Acessar apenas o valor de forma dinamica** imagine o cenario onde você precisar acessar uma propriedade mas não sabe o nome dela por exemplo:

```javascript
const nomeDoCampo = 'cor';

const carro = { cor: 'vermelho' };

console.log( carro[nomeDoCampo] ); // <- Acessar uma propriedade de formadinamica
/* vermelho */
```

**Ver o comportamento das propriedades**, com esse metodo podemos ver se a propriedade pode se alterada ou somente lida entre outras caracteristicas...

```javascript
const descricao = Object.getOwnPropertyDescriptors(Date); // <- captura a descrição das propriedades
console.log(descricao); 
/*
{length: {…}, name: {…}, prototype: {…}, now: {…}, parse: {…}, …} [[Prototype]]: Object
  UTC: [[Prototype]]: Object {
    configurable: true
    enumerable: false
    value: ƒ UTC()
    writable: true
  },
  name: [[Prototype]]: Object {
    configurable: true
    enumerable: false
    value: "Date"
    writable: false
  }
  now: [[Prototype]]: Object {
    configurable: true
    enumerable: false
    value: ƒ now()
    writable: true
  }
  …
*/
```

Podemos ver de uma propriedade em especifico tambem usando o [Object.getOwnPropertyDescriptor](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptor)

### Adicionar propriedades em um objeto

Para adicionar as propriedades em um objeto no Javascript temos algumas formas todas elas são usadas em diferentes momentos.

**Adicionar um propriedade estatica** basta usar o ponto e atribuição:

```javascript
const pessoa = {};

pessoa.nome = 'Marcos'; // <- Criar uma propriedade estatica

console.log( pessoa ); 
/*
{nome: 'Marcos'} [[Prototype]]: Object
constructor: ƒ Object()
  constructor: ƒ Object()
  hasOwnProperty: ƒ hasOwnProperty()
  toString: ƒ toString()
  …
*/
```


**Adicionar um propriedade com nome dinamico** basta usar `[]` como o valor e atribuição:

```javascript
const cadastro = {};
const id = Date.now();

cadastro[id] = 'Marcos'; // <- Criar uma propriedade dinamica

console.log( cadastro ); 
/*
{1633715068273: 'Marcos'} [[Prototype]]: Object
constructor: ƒ Object()
  constructor: ƒ Object()
  hasOwnProperty: ƒ hasOwnProperty()
  toString: ƒ toString()
  …
*/
```


**Adicionar um propriedade com comportamento especifico** devemos usar o [Object.defineProperty](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty):

```javascript
const pessoa = {};

Object
  .defineProperty(
    pessoa, // <- Objeto que a propriedade vai ser criada
    'nome', // <- Nome da propriedade que vai ser criada
    {
      configurable: false, // <- Verdadeiro se a propriedade poder ser re-configurada
      enumerable: false, // <- Verdadeiro se a propriedade deve aparecer no Object.keys()
      writable: false, // <- Verdadeiro se a propriedade poder ser re-atribuida
      value: 'Marcos', // <- Valor inicial da propriedade
    },
  );

pessoa.nome = 'Outro nome'; 

console.log( pessoa ); 
/*
{nome: 'Marcos'} [[Prototype]]: Object
constructor: ƒ Object()
  constructor: ƒ Object()
  hasOwnProperty: ƒ hasOwnProperty()
  toString: ƒ toString()
  …
*/
```

### Remover propriedades de um objeto

Para remover uma propriedade de um objeto temos duas formas:

1. **Criar outro objeto sem determinada propriedade**, dessa forma temos inumeras abordagens:

* **Criar outro objeto manualmente**:

```javascript
let pessoa = { id: 1, nome: 'Marcos', nascimento: '06/08/1998' };

pessoa = { id: pessoa.id, nascimento: pessoa.nascimento };

console.log( pessoa ); // <- Exibe como o objeto esta
/*
{id: 1, nascimento: '06/08/1998'} [[Prototype]]: Object
constructor: ƒ Object()
  constructor: ƒ Object()
  hasOwnProperty: ƒ hasOwnProperty()
  toString: ƒ toString()
  …
*/
```

Existem muitas outras formas de fazer isso como usar o [spred operator](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Operators/Spread_syntax) ou criar:

* **Criar outro objeto manualmente**:

```javascript
let pessoa = { id: 1, nome: 'Marcos', nascimento: '06/08/1998' };

pessoa = { id: pessoa.id, nascimento: pessoa.nascimento };

console.log( pessoa ); // <- Exibe como o objeto esta
/*
{id: 1, nascimento: '06/08/1998'} [[Prototype]]: Object
constructor: ƒ Object()
  constructor: ƒ Object()
  hasOwnProperty: ƒ hasOwnProperty()
  toString: ƒ toString()
  …
*/
```


2. **Deletar determinada propriedade da memoria**, usando uma das [palavras reservadas](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Lexical_grammar#palavras-chave) do javascript o 
[delete](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete),
dessa forma alteramos o objeto original:

```javascript
const pessoa = { nome: 'Marcos', nascimento: '06/08/1998' };

delete pessoa.nome;

console.log( pessoa ); // <- Exibe como o objeto esta
/*
{id: 1, nascimento: '06/08/1998'} [[Prototype]]: Object
constructor: ƒ Object()
  constructor: ƒ Object()
  hasOwnProperty: ƒ hasOwnProperty()
  toString: ƒ toString()
  …
*/
```

## 💪 Desafio para praticar

Crie funções para estruturar os dados de uma **escola**, lembre-se de incluir os objetos **aluno**, **professor**, **matérias**.
Se sentir a necessidade de criar mais objetos sinta-se livre para estruturar como quiser. Para fazer o desafio use alguma dessas ferramentas:

- [codepen](https://codepen.io/)
- [replit](https://replit.com/)

Para fazer o desafio você precisa de no minimo 3 funções:

Uma para a criação do objeto que:

- Deve retornar um objeto
- Pode chamar outras funções dentro dela
- Pode retornar outras funções dentro dos objetos
- Pode retornar outros objetos dentro do objeto principal

Uma para matricular um aluno em uma materia que: 

- Deve adicionar algum vinculo de um aluno a uma materia
- Pode receber um objeto como parametro ou estar dentro de um objeto

Uma para remover um aluno de uma materia que: 

- Deve remover o vinculo de um aluno a uma materia
- Pode receber um objeto como parametro ou estar dentro de um objeto

### Exemplo

Imagine um cenario onde teria que estruturar os dados de uma concessionária, onde os principais dados seriam o **carro**, **vendedor**, **comprador**.

```javascript
// Função para criar um carro
function criaCarro(ano, modelo, cor) {
  return {
    id: Math.random().toString(36).substring(7),
    ano, modelo, cor
  };
}

// Função que cria um objeto pessoa
function criaPessoa(nome) {
  return {
    nome,
  };
}

// Função que cria um objeto vendedor
function criaVendedor(pessoa) {
  return {
    codigo: Math.random().toString(36).substring(7),
    ...pessoa,
  };
}

// Função que cria um objeto vendedor
function criaVenda(carro, vendedor) {
  return {
    data: new Date(), carro, vendedor
  };
}

// Função que rotorna o objeto principal
function criaConcessionaria() {
  const carros = [
    criaCarro(2021, 'fusca', 'preto'),      
    criaCarro(1996, 'fusca', 'azul'),
  ];

  const vendedores = [
    criaVendedor(criaPessoa('Marcos')),      
  ];

  const vendidos = [];

  const venderCarro = (carroVendido, vendedor) => {
    const idx = carros.findIndex((carro) => carroVendido.id === carro.id);

    vendidos.push(criaVenda(carros.splice(idx, 1), vendedor);
  };

  return { carros, vendedores, vendidos, venderCarro };
}

const concessionaria = criaConcessionaria();

concessionaria.venderCarro(a.carros[0], a.vendedores[0]);
```


## 🧠 Objetivo de aprendizagem

O Objetivo deste estudo é aprender os conceitos fundamentais ao trabalhar com dados estruturados, usando objetos.

## ✔️ Entrega mínima

Estude bastante sobre objetos, e faça o maximo que conseguir dos desafios.
