# 🏁 Por onde começar a estudar Javascript

Como qualquer linguagem exige muito pratica então nesta issue você verá como iniciar montando seu ambiente e alguns lugares onde buscar conteúdo e alguns exercícios para praticar.

------------------------

- [📌 Aprender o Javascript](#AoJ)
- [📑 Entendendo como a linguagem pode ser usada](#Ecalpsu)
   - [O Javascript no Navegador](#OJnN)
   - [O Javascript no Servidor](#OJnS)
- [🔧 Preparando o ambiente](#Poa)
- [🔎 Encontrando conteúdo](#Ec)
- [📦 Packages ou pacotes](#Pop)
   - [Gerenciador de pacotes](#Gdp)
- [🧠Objetivo de aprendizagem](#Oa)
- [✔️ Entrega mínima](#Em)

## <a name="AoJ"></a> 📌 Aprender o Javascript

O primeiro passo é entender que temos dois caminhos um client-side ou seja no navegador e o outro server-side no servidor. Ambos tem pontos em comum vamos iniciar por ele mas lembre-se de certificar se oque esta vendo é do server ou client side.

### O básico da linguagem 

* [Sintax e variáveis](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Grammar_and_types)
* [Controle de fluxo](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)
* [Laços de repetição](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Loops_and_iteration)
* [Funções](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Functions)
* [Expressões e operadores](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Expressions_and_Operators)
* [Formatação de texto](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Text_formatting)
* [Números e datas](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Numbers_and_dates)
* [Expressões regulares](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Regular_Expressions)
* [Array - Listas indexadas](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Indexed_collections)
* [Objetos - Listas chaveadas](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Keyed_collections)
* [Usar objetos](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Working_with_Objects)
* [Prototipar objetos](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Details_of_the_Object_Model)
* [Interators ou Generators](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Iterators_and_Generators)
* [Proxy e Reflect](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Meta_programming)

Tente ver se já sabe algo se tem alguma duvida sobre algum revisite o conhecimento, é muito importante que esta parte esteja muito clara, pois isso ira facilitar tanto se quiser aprender o Javascript para o navegador quanto para o servidor.

## 📑 Entendendo como a linguagem pode ser usada

Neste ponto vamos entender muitas [características](https://pt.wikipedia.org/wiki/JavaScript#Caracter%C3%ADsticas) dele isso é muito importante para um conhecimento aprofundado. Não se preocupe se não entender todos esses pontos inicialmente, não se apegue neles neste momento mas é muito importante que entenda se quiser ter um profundo conhecimento.

Como disse antes o Javascript pode ser usado quase em qualquer lugar isso graças ao seu interpretador mais famoso a [v8](https://v8.dev/) que gera um [bytecode](https://pt.wikipedia.org/wiki/Bytecode) que pode ser usado de diferentes formas.

![v8 works digram](https://images.ponyfoo.com/uploads/addy-ad3b2ea8f9be48a18c4bdad5041a3237.png)

### O Javascript no Navegador

Uma das formas mais importantes onde o Javascript é usando é no navegador no caso por diversas [render engines](https://pt.wikipedia.org/wiki/Mecanismo_de_renderiza%C3%A7%C3%A3o) nem todas usam a v8 um exemplo disso é o [Gecko](https://pt.wikipedia.org/wiki/Gecko_(software)) a render engine do Firefox que usa o [SpiderMonkey](https://spidermonkey.dev/) um interpretador alternativo a v8.

As principais render engines existentes são o [WebKit](https://pt.wikipedia.org/wiki/WebKit) e primo dele o [Blink](https://pt.wikipedia.org/wiki/Blink_(motor_de_layout)) que são usados por grande parte dos navegadores como Chrome, Opera, Safari, Edge porem elas não são as únicas existentes um exemplo é o [Trident](https://pt.wikipedia.org/wiki/Trident_(motor_de_layout)) usado pelo IE contudo esse projeto foi abandonado hoje o IE se tornou o Edge que também usa o Blink. 

![Navegadores, suas render engines e suas Javascript engines](https://drive.google.com/u/0/uc?id=1mxXSsiYW_H8a2Bm5haWxhyLHlnlARoT5&export=download)

Neste caso vamos ver um pouco mais sobre o mais recente e popular deles o Blink. Ele tem esse nome foi influenciado pela [tag blink](https://en.wikipedia.org/wiki/Blink_element) que ele nunca deu suporte.

### O Javascript no Servidor

É chamado de [NodeJS](https://pt.wikipedia.org/wiki/Node.js) tem uma versão estável oficial para todos os principais OS, pode ser usado de muitas maneiras diferentes. Abaixo vamos ver como ele funciona e algumas de suas principais caracteristicas.

#### NodeJS não é uma linguagem

Ele é apenas um [Runtime](https://pt.wikipedia.org/wiki/Tempo_de_execu%C3%A7%C3%A3o) escrito em C/C++ (*uma maquina virtual que executa oque é entendido do [interpretador](https://pt.wikipedia.org/wiki/Interpretador)*). A linguagem usada no Node é Javascript. 

O mesmo Javascript que é entendido no navegador com algumas funcionalidades a mais e outras a menos, por exemplo no Javascript que é executado na runtime do Node podemos criar arquivos diretamente no sistema operacional já no navegador não por [motivos de segurança](https://stackoverflow.com/questions/371875/local-file-access-with-javascript).

Como disse antes o interpretador neste caso também é a V8 ela entende o que foi escrito em Javascript e gera o bytecode. Apartir deste bytecode a runtime executa as ações no sistema operacional em [linguagem de maquina](https://pt.wikipedia.org/wiki/C%C3%B3digo_de_m%C3%A1quina), por este motivo temos uma runtime para cada sistema operacional, onde todos usam a v8.

O responsável por boa parte das ações no sistema operacional é a [LIBUV](https://libuv.org/), uma biblioteca em C++ para lidar com [I/O](https://pt.wikipedia.org/wiki/Entrada/sa%C3%ADda) desenvolvida inicialmente para NodeJS porem hoje usada por outras linguagens como Luvit, Julia, pyuv, etc... 

![arquitetura node](https://drive.google.com/u/0/uc?id=1jWpfQXnRWfY_1iF88zi6cwstGaYbJwkE&export=download)


### Caracteristicas do Javascript

Como toda linguagem Javascript tem algumas caracteristas importantes, que podem te ajudar a ter mais dominio sobre ela.


#### Suporte universal

Graças a **V8** hoje é possivel usar a linguagem para praticamente qualquer coisa como:

- Criar uma aplicação web para com NodeJS. 
- Manipular o [DOM]() / HTML no [browser]().
- Computação embarcada como Arduino usando [Jhonyfive].

Entre muitas outras possibilidades.

#### Dinamica

Você consegue executar trechos de códigos digitados em [run-time (tempo de execução)](https://pt.wikipedia.org/wiki/Tempo_de_execu%C3%A7%C3%A3o), graças ao [`eval`](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/eval)

#### Multi-paradgima

Suporta diferentes [paradgimas](https://pt.wikipedia.org/wiki/Paradigma_de_programa%C3%A7%C3%A3o) como **orientados a eventos**, **funcional** e **imperativos** (incluindo orientado a objetos e prototype-based). Para entender um pouco melhor sobre paradgimas veja alguns passos anteriores nas issues.

#### [Tipagem fraca e dinamicamente](https://pt.wikipedia.org/wiki/Linguagem_tipada)

O fato de você não ter que inferir o tipo não significa que ela não tenha tipos. Em ambos temos vantagens e desvantagens. Com a linguagens fortemente tipadas, identificamos erros no código mias facilmente, por outro lado sua curva de aprendizagem pode se tornar maior.

#### É Single [Thread](https://pt.wikipedia.org/wiki/Thread_(computa%C3%A7%C3%A3o))

A verdade é que a **V8** single thread é, não entraremos muito nesse ponto neste momento mais a frente entenderemos como isso funciona. Por hora entenda que ele só pode tratar uma coisa de cada vez, então o processamento de cada uma não pode ser demorado.

Se quiser entender isso neste momento recomendamos essas leituras:

[en](https://betterprogramming.pub/is-node-js-really-single-threaded-7ea59bcc8d64) [pt](https://imasters.com.br/front-end/node-js-o-que-e-esse-event-loop-afinal) [pt](https://imasters.com.br/front-end/node-js-v8-single-thread-e-io-nao-bloqueante)

#### Não é a mesma coisa que [EcmaScript](https://pt.wikipedia.org/wiki/ECMAScript)

É muito comum as pessoas confundirem afinal o Ecmascript é a especificação de como o Javascript deve ser tanto no navegador quando no runtime do Node.

## 🔧 Preparando o ambiente

Independente se vai aprender o Javascript para *client-side* ou para *server-side* é importante ter o NodeJS instalado na sua maquina pois ele é muito usado para ambos os casos.

Para iniciar precisamos preparar nossa maquina para conseguirmos executar nosso código. Para isso precisamos instalar o NodeJS no ambiente de **desenvolvimento** geralmente usamos o [NVM (Node version manager)](https://github.com/nvm-sh/nvm) isso porque diferentes de outras linguagens o node não controla sua própria versão de maneira automática. Baixe de acordo com seu sistema operacional:

* [Windows](https://github.com/coreybutler/nvm-windows)
* [Linux ou Mac](https://github.com/nvm-sh/nvm)

> ⚠️ **Atenção**: Se instalou o Node diretamente recomendamos desinstalar e usar o NVM.
> *Isso porque aplicações podem usar diferentes versões do Node e a mudança de uma Versão para a outra pode tomar muito tempo*

## 🔎 Encontrando conteúdo

Como toda linguagem tem lugares em comum que pode ser usado para busca conteúdo. Aqui você verá alguns pontos exclusivos do NodeJS.

* Acompanhar o futuro da linguagem
> [TC39 - ECMA262](https://github.com/tc39/ecma262) é quem cuida das especificações Javascript o famoso EcmaScript. Então se quiser antecipar oque pode ser desenvolvido ou até mesmo mandar sua própria sugestão.
> [Repositório oficial do Node](https://github.com/nodejs/node) é onde esta o código então se quiser saber oque esta sendo desenvolvido pode acompanhar os commits ou as releases.

* Buscar pacotes como código
> [NPM](https://www.npmjs.com/) aqui é o repositório oficial do node onde tem milhões de pacotes que você pode usar.

* Coisas para estudar
> [Node DEV](https://nodejs.dev/learn)
> [MDN](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript) um dos melhores lugares para estudar sobre Javascript.

## 🧠 Objetivo de aprendizagem

O Objetivo deste estudo é entender a fundo as partes mais conceituais, e os pontos mais comuns por onde começar a estudar.

## ✔️ Entrega mínima

Escolha onde deseja se aprofunda, como frontend ou backend e estude o básico da linguagem encontrando 2 pontos que não conhece e criando exemplos de uso sobre.