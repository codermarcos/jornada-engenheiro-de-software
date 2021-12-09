# 🥚 POO no Javascript

Vamos entender como podemos trabalhar com orientação a objetos no Javascript. Não se preocupe se não entender os primeiros paragrafos entramos primeiro em uma parte conceitual, vamos praticar mais a frente.

------------------------

- [🥚 POO no Javascript](#-poo-no-javascript)
  - [Como trabalhar com POO no Javascript](#como-trabalhar-com-poo-no-javascript)
    - [Diferença entre uma orientação objetos classica vs orientação a objetos baseado em prototipos](#diferença-entre-uma-orientação-objetos-classica-vs-orientação-a-objetos-baseado-em-prototipos)
    - [Instanciar um object](#instanciar-um-object)
    - [Protototipar um objeto](#protototipar-um-objeto)
    - [Herança](#herança)
  - [Sugar syntax para Prototypar objetos](#sugar-syntax-para-prototypar-objetos)
  - [🧠 Objetivo de aprendizagem](#-objetivo-de-aprendizagem)
  - [✔️ Entrega mínima](#️-entrega-mínima)


## Como trabalhar com POO no Javascript

O primeiro passo é entender que o Javascript é uma [linguagem orientada a prótotipos](https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_baseada_em_prot%C3%B3tipos), e uma das unicas que trabalha com
orientação a objetos usando prototipo. 

✔️ **Herança**: é implementada através do processo de clonagem de objetos existentes que servem como protótipos.  
✔️ **Encapsulamento**: é implementada através de variaveis locais dentro do escopo das funções (objetos).  
✔️ **Polimorfismo**: é implementando re-definindo os comportamentos do objeto base.  

Para alguns esses recursos não são o sulficiente para ser uma [linguagem orientada a objetos](https://pt.wikipedia.org/wiki/Orienta%C3%A7%C3%A3o_a_objetos) por falta de:

❌ **Classe abstra** ou **Abstração** (até é possivel atravez de algumas implementações porem não de forma nativa)  
❌ **[Sobrecarga (Overload)](https://pt.wikipedia.org/wiki/Sobrecarga_de_fun%C3%A7%C3%A3o)**

Contudo esses recursos não são os pilares da Orientação a objetos, os pilares são:

- [Herança](https://pt.wikipedia.org/wiki/Heran%C3%A7a_(programa%C3%A7%C3%A3o_orientada_a_objetos))
- [Abstração](https://pt.wikipedia.org/wiki/Abstra%C3%A7%C3%A3o_(ci%C3%AAncia_da_computa%C3%A7%C3%A3o))
- [Polimorfismo](https://pt.wikipedia.org/wiki/Polimorfismo_(ci%C3%AAncia_da_computa%C3%A7%C3%A3o))
- [Encapsulamento](https://en.wikipedia.org/wiki/Encapsulation_(computer_programming))

E mesmo com isso quando utilizamos [typescript](https://www.typescriptlang.org/) temos todos os recursos nescessarios e mais algumas vatagens que uma linguagem orientada a protótipo tem como:

- **Flexibilidade**: Podemos alterar um objeto sem a necessidade de criar uma nova classe 

### Diferença entre uma orientação objetos classica vs orientação a objetos baseado em prototipos

Na **classica** classe e objeto são coisas diferenetes. Quando definimos uma subclasse, criamos uma nova classe que herda propriedades e comportamentos de sua classe base. E só possivel manipular
os dados da subclasse após instanciar ela e neste momento ela se torna um objeto. 

Já na orientada a **protótipo** não temos essa distinção temos apenas objetos, e objetos tem seus prototipos (prototypes) que podem ser usados para gerar outros objetos. Todos objetos instanciado tem referencia 
a seu objeto prototypo de origem através do [__proto__](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Object/proto). Cada objeto pode definir suas propriedades.

IMAGEM HERE

### Instanciar um object

Quando criamos um objeto literal o javascript automaticamente "instancia um novo objeto" apartir da "classe" [Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) 
(que na verdade não é uma classe e sim um construtor), na verdade ele criar um novo objeto copiando todo o prototype do `Object` como vemos a alguns encontros atrás.

```javascript
const pessoa = {};

console.log(pessoa instanceof Object); // true
```

### Protototipar um objeto

Podemos criar uma função que defina o comportamento daquele objeto.

```javascript
function createPessoa(nome) {
  const pessoa = {};

  pessoa.nome = nome;

  pessoa.apresentacao = () => alert(`Olá, eu sou ${pessoa.nome}`);

  return pessoa;
}

const pessoa1 = createPessoa('Marcos');

console.log(pessoa);
// {nome: 'Marcos', apresentacao: ƒ}
// apresentacao: () => alert(`Olá, eu sou ${pessoa.nome}`)
// nome: "Marcos"
// [[Prototype]]: Object
```

Porem não é muito legivel, e se torna quase impossivel saber qual a instancia dessa classe se não indentificando por suas propriedades e comportamentos. 

Outro caminho mais interessante é definir um construtor como os existentes [Object](), [Date](), [Array]() que são nativos do Javascript. Para isso basta usar uma função:

```javascript
function Pessoa(nome) {
  this.nome = nome;
  this.apresentacao = () => this.nome;
}

const pessoa2 = new Pessoa('Marcos');

console.log(pessoa);
// {nome: 'Marcos', apresentacao: ƒ}
// apresentacao: () => alert(`Olá, eu sou ${pessoa.nome}`)
// nome: "Marcos"
// [[Prototype]]: Object
```

Assim se quiser verificar sua instancia podemos usar o [instanceof](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Operators/instanceof):

```javascript
console.log( pessoa1 instanceof Pessoa ); // false
console.log( pessoa1 instanceof Object ); // true

console.log( pessoa2 instanceof Object ); // true
console.log( pessoa2 instanceof Pessoa ); // true

console.log( Pessoa.prototype instanceof Object ); // true

console.log( pessoa1.constructor.name ); // Object
console.log( pessoa2.constructor.name ); // Pessoa
```

Porem como disse antes para criar uma nova instancia o Javascript copia o prototipo de um objeto para o outro desta forma se verificar de quem `pessoa2` herdou suas propriedades de `Object`, 
por este motivo ele tem as propriedades padrões do `Object`.

```javascript
console.log(pessoa2.hasOwnProperty); // ƒ hasOwnProperty() { [native code] }
```

Outra forma de fazer isso pode ser usando o prototype do objeto:

```javascript
function Pessoa(nome) {
  this.nome = nome;
}

Pessoa.prototype.apresentacao = function () { return this.nome; };
```

### Herança

Para herdar as propriedades de outro objeto podemos usar o [call](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Function/Call) assim ele passa o escopo do objeto que esta sendo criado
para a chamada do objeto pai que ele herdara as propriedades desta forma:

```javascript
function Pessoa(nome) {
  this.nome = nome;
}

function Medico(nome, crm) {
  Pessoa.call(this, ...arguments);
  this.crm = crm;
}

const medico1 = new Medico('Antonio', 'xxx');

console.log( medico1 );
// Medico {nome: 'Marcos', crm: 'xxx'}
// [[Prototype]]: Object

console.log( medico1 instanceof Pessoa ); // false
console.log( medico1 instanceof Medico ); // true
console.log( medico1 instanceof Object ); // true
```

Se prestar atenção ele ainda mantem o Object como sua herança para mudar isso basta definir seu protótipo com o objecto que ele herdara suas propriedades assim: 

```javascript
Medico.prototype = Object.create(Pessoa.prototype);
Object.defineProperty(Medico.prototype, 'constructor', { value: Medico, enumerable: false, writable: true });

const medico2 = new Medico('Antonio', 'xxx');

console.log( medico2 );
// Medico {nome: 'Marcos', crm: 'xxx'}
// [[Prototype]]: Pessoa

console.log( medico1 instanceof Pessoa ); // true
console.log( medico1 instanceof Medico ); // true
console.log( medico1 instanceof Object ); // true
```

## Sugar syntax para Prototypar objetos

Com a [ECMAScript 2015 ou es6](https://262.ecma-international.org/6.0/) acima podemos utilizar classes para ter o mesmo resultado que antes era preciso usar toda aquela sintax verbosa:

```javascript
class Pessoa {
  constructor(nome) {
    this.nome = nome;
  }  
}
```

Inclusive aplicar herança de forma mais curta:

```javascript
class Medico extends Pessoa {
  constructor(nome, crm) {
    super(nome);

    this.crm = crm;
  }  
}
```

Definir propriedades getter e setter:

```javascript
class Carro {
  get documento() {
    return this._documento;
  }

  set documento(documento) {
    this._documento = documento;
  }
}
```

Mesmo ainda não tendo uma sintax para acessar variaveis privadas a comunidade criou uma convenção para usar `_` o underline para dizer que não podemos usar mecher no valor pois é privado.
Porem isso não impede de acessar aquele valor. Tem uma proposta de implementação de [propriedades privadas](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/Private_class_fields) 
em andamento você pode [conferir os status disso aqui](https://github.com/tc39/proposal-private-fields). Ficaria próximo disso:

```javascript
class ClassWithPrivateField {
  #privateField;

  constructor() {
    this.#privateField = 42;
  }
}
```


## 🧠 Objetivo de aprendizagem

O Objetivo deste estudo é aprender os conceitos fundamentais ao trabalhar com dados estruturados, usando objetos.

## ✔️ Entrega mínima
