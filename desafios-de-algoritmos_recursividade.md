# ⭐ Desafios de algoritmos: Recursividade

Nesses desafios vamos focar em desenvolver sua lógica, usando recursos básicos da linguagem que podem ser encontrados em todas as linguagens. 

------------------------

- [⭐ Desafios de algoritmos: Recursividade](#-desafios-de-algoritmos-recursividade)
  - [📚  A recursividade](#--a-recursividade)
    - [Exemplo](#exemplo)
  - [💪 Desafios para praticar](#-desafios-para-praticar)
  - [🧠 Objetivo de aprendizagem](#-objetivo-de-aprendizagem)
  - [✔️ Entrega mínima](#️-entrega-mínima)


## 📚  A recursividade

[Algoritmos recursivos](https://pt.wikipedia.org/wiki/Recursividade_(ci%C3%AAncia_da_computa%C3%A7%C3%A3o)) são muito usados quando temos uma possibilidade muito grande de ocorrências do mesmo problema. Basicamente é um bloco de código que chama ele mesmo dado a necessidade usando outra técnica chamada [Divisão e conquista](https://pt.wikipedia.org/wiki/Divis%C3%A3o_e_conquista).

### Exemplo 

Imagine um cenario onde temos uma lista com dois tipos de dados operações matematicas simples parecido com esta `5 + 1`, e outra lista com os mesmos dados. Logo teriamos uma recursividade que pode ter inifinidade de possibilidades. Visualmente teriamos algo parecido com isso:

```javascript
[
  '2 + 1', 
  [ 
    '5 * 5', 
    [
      '10 - 5',
      '10 + 5',
      …
    ],
    '1 + 1',
    […]
    …
  ],
  […]
  …
]
```

Imagine que precisamos resolver todas as operações e somar o resultado delas para obter um total. Seria praticamente impossivel dizer quantas listas temos nas listas abaixo com isso seria impossivel escrever um código para acessar cada operação manualmente de forma estatica.

Para lidar com dados recursivos tente sempre dividir o problema em pequenas partes por exemplo, neste caso:

1. Vamos focar em resolver uma unica operação
2. Depois como repetir a operação em listas dentro das listas
3. Por fim vamos resolver o problema da recursividade com repitir para os subitems

Para resolver a operação podemos criar uma função que receba uma string com a operação e resolva a mesma. Para isso podemos usar o [split](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/String/split) para dividir a string em pedaços:

```javascript
function resolva(operacao) = {
  const [v1, op, v2] = operacao.split(' '); // ['1', '+', '2']

  switch (op) {
    case '*':
      return parseInt(v1) * parseInt(v2); 

    case '-':
      return parseInt(v1) - parseInt(v2);

    case '+': // condição correspondente
      return parseInt(v1) + parseInt(v2);
  }
}

console.log( resolva('1 + 2') );  // 3
```
 
Pronto temos uma função para resolver UMA operação. Agora temos que fazer ele se repetir para cada item em uma lista e ao final somar os items. Ainda não vamos nós preocupar com os subitems apenas com os items primarios da lista.
Para isso vamos usar um reduce:

```javascript
function resolva(operacao) {
  const [v1, op, v2] = operacao.split(' '); // ['1', '+', '2']

  switch (op) {
    case '*':
      return parseInt(v1) * parseInt(v2); 

    case '-':
      return parseInt(v1) - parseInt(v2);

    case '+':
      return parseInt(v1) + parseInt(v2);
  }
}

function repitaParaCadaListaDeItens(items) {
  const resultado = items
    .reduce(
      (anterior, calculo) => {
        const total = resolva(calculo);        
        return anterior + total;
      },
      0
    );

  return resultado;
}
console.log( repitaParaCadaListaDeItens(['1 + 2', '5 - 3']) );  // 5
```

Agora basta apenas cuidar dos sub items, para isso temos que identificar quando há subitems e chamar uma função para revolver esse problema:

```javascript
function resolva(operacao) {
  const [v1, op, v2] = operacao.split(' '); // ['1', '+', '2']

  switch (op) {
    case '*':
      return parseInt(v1) * parseInt(v2); 

    case '-':
      return parseInt(v1) - parseInt(v2);

    case '+':
      return parseInt(v1) + parseInt(v2);
  }
}

function repitaParaCadaListaDeItens(items) {
  const resultado = items
    .reduce(
      (anterior, calculo) => {
        const total = typeof calculo === 'string' ? resolva(calculo) : repitaParaCadaListaDeItens(calculo);        
        return anterior + total;
      },
      0
    );

  return resultado;
}
console.log( repitaParaCadaListaDeItens(['1 + 2', '5 - 3', ['1 + 1', '2 - 1']]) );  // 8
```

[Link do exemplo no replit.](https://replit.com/@codermarcos/recursive-pair#script.js)

## 💪 Desafios para praticar

Para realizar esses dois desafios você pode usar ou não recursividade, tente identificar a necessidade e resolve-los da melhor forma mais adequada:

* [one](https://replit.com/@codermarcos/challenge-one#script.js)
* [two](https://replit.com/@codermarcos/challenge-two#script.js)

## 🧠 Objetivo de aprendizagem

Aprender um pouco mais sobre recursividade, entender os prós e contras quando usar e não usar.

## ✔️ Entrega mínima

Estudar um pouco mais sobre recursividade, para conseguir resolver os desafios usando ou não essa técnica.  