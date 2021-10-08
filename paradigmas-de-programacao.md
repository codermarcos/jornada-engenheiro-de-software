 # ✨ Paradigmas de programação

Vamos entender oque é um paradigma, qual sua importância, quais existem e como eles funcionam e oque muda de um para o outro.

------------------------

- [✨ Paradigmas de programação](#-paradigmas-de-programação)
  - [❓ O que é um paradigma](#-o-que-é-um-paradigma)
  - [🧰 Os paradigmas](#-os-paradigmas)
    - [Programação Funcional](#programação-funcional)
    - [Programação orientada a eventos](#programação-orientada-a-eventos)
    - [Programação orientada a objetos](#programação-orientada-a-objetos)
    - [Programação Imperativa](#programação-imperativa)
    - [Programação Declarativa](#programação-declarativa)
  - [🧠Objetivo de aprendizagem](#objetivo-de-aprendizagem)
  - [✔️ Entrega mínima](#️-entrega-mínima)


## ❓ O que é um [paradigma](https://pt.wikipedia.org/wiki/Paradigma_de_programa%C3%A7%C3%A3o)

Um paradigma é uma forma de classificar uma linguagem, baseado nas suas funcionalidades. É comum nos referirmos a um paradigma como uma forma de programar similar a um padrão, isso porque muitas linguagens são multi paradigmas ou seja tem influencias de muitos paradigmas e na hora de programar sempre podemos optar por um deles.

Muitos paradigmas tem forte influencia de outros paradigmas então quanto mais paradigmas você conhece mais fácil se torna de aprender outro paradigma, e outras linguagens. A parte mais complicada de aprender uma linguagem é o paradigma então foque em entender o paradigma que mais influencia sua linguagem.

Alem de eles influenciarem a forma como escrevemos nosso código eles tambem podem mudar a forma como nosso software se comporta, ou interage com a plataforma na qual esta rodando.

## 🧰 Os paradigmas

Hoje temos muitos paradigmas diferentes, vamos falar dos mais comuns aceitos nas linguagens mais comuns. Não se preocupe em entender todos eles, apenas os mais importantes nesse momento (Funcional, Orientando a Eventos).

Todas as linguagens das quais recomendamos suportam todos os seguintes paradigmas, que vamos abordar se quiser ver um pouco mais sobre as linguagens e paradigmas pode ver [aqui](https://en.wikipedia.org/wiki/Comparison_of_programming_languages).

[video - pt](https://www.youtube.com/watch?v=pbUS-1-cjqk) [video - pt](https://www.youtube.com/watch?v=uwPP4oO9w8s)

### [Programação Funcional](https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_funcional)

Como o nome sugere, ele é muito baseado em funções, como na matemática usando [imutábilidade](https://segredo.dev/o-que-e-imutabilidade/) e [funções puras](https://en.wikipedia.org/wiki/Pure_function) ou seja elas não podem gerar [efeitos colaterais (side-effects)](https://en.wikipedia.org/wiki/Side_effect_(computer_science)) ou seja alterar algo que esteja fora de seu escopo como consequência devem ser sempre [sem estado (stateless)](https://www.redhat.com/pt-br/topics/cloud-native-apps/stateful-vs-stateless) isso porque não armazenam ou alteram valores fora de seu escopo.

Exemplos de linguagens que suportam programação funcional: **Prolog**, **Lisp**

```javascript
function soma(a, b) {
  return a + b;
}

const resultado = soma(1 + 1);
```

Apesar de ter surgido antes da Orientada a objetos ela só veio se tornar popular agora. Isso porque o cenário que temos hoje dos hardwares esta mais favorável para o comportamento desse paradigma.

Links uteis para estudar:
[video - pt](https://www.youtube.com/watch?v=BxbHGPivjdc) [pt](https://medium.com/trainingcenter/programa%C3%A7%C3%A3o-funcional-para-iniciantes-9e2beddb5b43)


### [Programação orientada a eventos](https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_orientada_a_eventos)

É um paradigma baseado em acontecimentos os "Eventos" que podem se repetir ou mesmo nunca acontecer.  Muito usado quando estamos trabalhando com operações que não tem ordem ou momento certo para acontecer. Por exemplo:

- Trabalhar com interface e capturar ações do usuário.
- Comunicação assíncrona entre serviços, filas etc.
- Comunicação real-time como Websockets.

Exemplos de linguagens que suportam programação orientadas a evento: **Javascript**, **JAVA**

```javascript
function handler() {
  // EXECUTADO QUANDO TIVER ALGUM NOVO ELEMENTO NA FILA
  // OU 
  // EXECUTANDO QUANDO ALGUEM CLICAR NO ELEMENTO
}

queue.on('new', handler);

document.body.addEventListener('click', handler);
```

### [Programação orientada a objetos](https://pt.wikipedia.org/wiki/Orienta%C3%A7%C3%A3o_a_objetos)

Fez muito sucesso e teve forte influencia do paradigma funcional, seu pilar esta nos objetos que nada mais são do que conjuntos de dados que pode ter origem de uma classe ou mais classes  e tem comportamentos similares ou relacionados. Imagine uma classes como uma forma de ovo de pascoa e o chocolate como os dados assim a forma é usada para dar forma para o chocolate. 

```javascript
class Pessoa {
  constructor(nome, anoNascimento) {
    const ano = new Date().getFullYear();
    this.idade = ano - anoNascimento;
    this.nome = nome;
  }

  maiorIdade() {
    return this.idade > 18;
  }
}
```
### [Programação Imperativa](https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_imperativa)

Um paradigma que foi muito usado no passado, e ainda é predominante sendo um dos primeiros paradigmas aprendidos por todos que iniciam na programação. 

Os paradigmas [procedural](https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_procedural) e **orientada a objetos** se enquadram no paradigma imperativo.

Para entender ele um pouco melhor basta entender a palavra [**imperativo**](https://www.dicio.com.br/imperativo/), (Que impõe, Que se impõe de forma argumentativa...) ou seja suas principais caracteristicas são:

- Funcões que representavam comandos ou procedimentos
- Um estado (variaveis globais, locais) que sofre modificações durante a execução do software

Sua principal diferença entre o funcional esta na atribuição que permite mutar o estado durante a execução.

Exemplos de linguagens impereativas: **C**, **JAVA**

```javascript
let saldo = 0;

function adicionaSaldo(valor) {
  saldo += valor;
}

adicionaSaldo(10);
```

### [Programação Declarativa](https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_declarativa)

É considerada o extremo oposto a imperativa, equanto a programação imperativa foca no como as coisas devem ocorrer a declarativa foca apenas em oque deve acontecer.

A programação funcional, [lógica](https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_l%C3%B3gica) e de [consulta como um subconjunto do SQL o DML](https://pt.wikipedia.org/wiki/SQL) podem ser classificados como declarativos.

Exemplos de programação declarativa: **SQL**, **HTML**

```sql
SELECT * FROM pessoas WHERE nome = 'Marcos'
```

## 🧠Objetivo de aprendizagem

O Objetivo deste estudo é entender oque são os paradigmas e que existem muitos deles eles são muitos influenciados um pelos outros. Tambem saber oque eles influenciam no modo como nosso software se comporta.

## ✔️ Entrega mínima

Escolha um paradigma para estudar, e explique sobre ele.
