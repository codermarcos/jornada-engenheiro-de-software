# 👣 Primeiros passos no backend

Neste estudo vamos começar a entender um pouco melhor a atuação de um desenvolvedor backend e suas areas de estudo.

------------------------

- [👣 Primeiros passos no backend](#-primeiros-passos-no-backend)
  - [👷 Oque é um desenvolvedor backend?](#-oque-é-um-desenvolvedor-backend)
    - [♾️ Ciclo de vida de um software](#️-ciclo-de-vida-de-um-software)
  - [Oque estudar?](#oque-estudar)
    - [3️⃣ Definição](#3️⃣-definição)
    - [4️⃣ Modelagem](#4️⃣-modelagem)
    - [4️⃣ Desenvolvimento](#4️⃣-desenvolvimento)
    - [5️⃣ Testes](#5️⃣-testes)
    - [6️⃣ Implantação](#6️⃣-implantação)
    - [7️⃣ Manutenção](#7️⃣-manutenção)
  - [🧠 Objetivo de aprendizagem](#-objetivo-de-aprendizagem)
  - [✔️ Entrega mínima](#️-entrega-mínima)

## 👷 Oque é um desenvolvedor backend?

Para desempenhar o papel como um bom backend é importante entender muito alem do backend, é preciso entender que oque estamos desenvolvendo
não é apenas código isso vai impactar as pessoas e por isso precisa de atenção desde a ideação, e durante toda sua vida.

### ♾️ Ciclo de vida de um software

Para entender qual o ciclo de vida de um software existem diversos métodos eles são usados para guiar uma aplicação durante sua vida desde a sua concepção, até operação e manutenção. 

Um deles é o [ALM](https://pt.wikipedia.org/wiki/Application_lifecycle_management) este é focado em olhar para o ciclo de vida de um software como um todo existem outros focados apenas no desenvolvimento como [SDLC (software development life cycle)](https://pt.wikipedia.org/wiki/Processo_de_desenvolvimento_de_software), porem é muito importante ter uma visão ampla do produto que esta desenvolvimento.

1️⃣ **Ideação** é a primeira parte do ciclo nela temos a ideia e precisamos trabalhar nela até este momento.  
Dentro da ideação tab

2️⃣ **Planejamento** é onde verificamos as possibilidades e a viabilidade levantando os riscos, custos e recursos necessarios.

3️⃣ **Definição** é o primeiro passo do desenvolvimento onde levantamos os requisitos de quem idealizou.

4️⃣ **Modelagem** é onde definimos e documentamos a arquitetura, e tomamos algumas decisões relacionadas a tecnologia.

5️⃣ **Desenvolvimento** é onde realmente codificamos a aplicação, documentamos tudo e tomamos pequenas decisões que surgiram durante o desenvolvimento. É aqui onde temos a maior atuação.

6️⃣ **Teste** é onde validamos oque foi desenvolvido pode ser feito antes do desenvolvimento como quando trabalhamos com [TDD](https://pt.wikipedia.org/wiki/Test-driven_development) durante o desenvolvimento ou até mesmo durante a implantação como é feito com [canary deployment](https://www.infoq.com/br/news/2013/04/versao-canary-aumenta-qualidade/).

7️⃣ **Implantação** é onde nosso software entra em atividade, quando o usuario esta usando inicia o uso da aplicação.

8️⃣ **Manutenção** é quando começamos a monitorar e observar o uso afins de implantar melhorias e correção de possiveis erros.

Tudo isso para que 3 partes fundamentais governança, desenvolvimento e operação estarem sempre alinhadas e seguindo um fluxo. 

*É muito importante para você como desenvolvedor tentar participar de todo o ciclo de vida do software do qual você contribui*, porem como sabemos nem sempre é possivel, oque podemos fazer neste caso é o *tentar trilhar o caminho inverso e entender o que levou a aplicação estar como ela esta estruturada hoje*. 

## Oque estudar?

Vamos seguir o ciclo de desenvolvimento do software vamos passar pelos principais pontos de atuação por isso vamos acabar pulando alguns.

### 3️⃣ Definição

Essa parte pode ser feita pelo time de desenvolvimento ou não. Aqui geralmente temos um time de [designers](https://pt.wikipedia.org/wiki/Designer) que estudam e definem os melhores caminhos para o produto em conjunto com o Product Owner que tambem pode ser Project Manager. 


### 4️⃣ Modelagem

Com base nas definições podemos inciar a modelagem, nesse ponto escolhemos algumas tecnologias, desenhamos a arquitetura escolhendo modelos de representação para auxiliar na documentação.

Como por exemplo diagramas de [caso de uso](https://pt.wikipedia.org/wiki/Diagrama_de_caso_de_uso), [sequencia](https://pt.wikipedia.org/wiki/Diagrama_de_sequ%C3%AAncia), [classe](https://pt.wikipedia.org/wiki/Diagrama_de_classes), [entidade e relacionamento](https://pt.wikipedia.org/wiki/Modelo_entidade_relacionamento), [transição de estados](https://pt.wikipedia.org/wiki/Diagrama_de_transi%C3%A7%C3%A3o_de_estados) para partes especificas do software para uma visão mais completa [C4model](https://en.wikipedia.org/wiki/C4_model) ou como pode acontecer muitas vezes não ter a parte de ideação muito clara e precisar documentar essas parte de negocios podemos usar um [bpmn](https://pt.wikipedia.org/wiki/Business_Process_Model_and_Notation).

Nesta parte de modelagem é sempre bom ter pessoas que já tiveram forte atuação em outras criações e sustentações de outro software similar.

Existem muitas ferramentas para isso como:

Para Bpmn:

- [bpmn](https://bpmn.io/)

Diagrama de sequencia:

- [sequencediagram](https://sequencediagram.org/)

Diagrama de banco de dados:

- [dbdiagram.io](https://dbdiagram.io/home)

Para todo tipo de documentação:

- [draw.io](https://app.diagrams.net/)

Com essas ferramentas documentamos a [arquitetura](https://pt.wikipedia.org/wiki/Arquitetura_de_software) escolhida do software, e de cada [componente](https://pt.wikipedia.org/wiki/Componente_de_software) dele tambem podemos documentar os [processos](https://pt.wikipedia.org/wiki/Processo_de_neg%C3%B3cio) envolvidos.

Neste ponto tambem escolhemos se nossa aplicação vai usar um [iaas](https://pt.wikipedia.org/wiki/HaaS) com uma [maquina virtual](https://pt.wikipedia.org/wiki/M%C3%A1quina_virtual), ou em um [saas](https://pt.wikipedia.org/wiki/Software_como_servi%C3%A7o) como [serveless](https://en.wikipedia.org/wiki/Serverless_computing) para tomar essas decisões precismos entender o cenario da aplicação.

essas decisões impactam diretamente:

- No custo de uso, desenvolvimento e manutenção da aplicação
- Na dificuldade de mudanças de tecnologia, cloud providers etc...

Por este motivo é uma das partes que sempre voltamos e devemos avaliar se tudo esta como planejado ou se precisamos tomar novas decisões.

### 4️⃣ Desenvolvimento

Esta é a parte mais importante para o desenvolvedor, aqui ele vamos desenvolver e documentar nosso código baseado no que documentamos, é muito importante que cada mudança durante o desenvolvimento tambem seja atualizada nas documentações existentes.

Neste momento como desenvolvedor backend você precisa sempre se preocupar com alguns pontos muito importantes:

**Escolha das tecnologias** aqui tomamos o restante das tecnologias se iremos usar um framework ou usar um biblioteca ou um framework:

Frameworks:

- [Next](https://nextjs.org/)
- [Nest](https://docs.nestjs.com/)
- [Loopback](https://loopback.io/)

Bibliotecas:

- [Express](https://expressjs.com/pt-br/)
- [Fastfy](https://www.fastify.io/)

A principal diferença entre os dois esta em como escrevemos nosso código e nas funções que cada um realiza. Quando optamos por um framework ele geralmente
dita a forma como escrevemos nosso código enquanto em bibliotecas temos a liberdade de escolher diferentes implementações.

Um framework tambem costuma ter tudo que precisamos para executar nossa solução isso causar um overlap de funções do framework com o nosso Cloud Provider.


**Setup do projeto** como outra pessoa consegue executar o projeto na maquina dela, mesmo que você seja o o unico desenvolvedor sempre tenha esse ponto 
em mente afinal existem muitas possibilidades como atuar em varios projetos, mudar de tecnologia, ficar um longo tempo sem executar o projeto ou até mesmo o [fator onibus](https://pt.wikipedia.org/wiki/Fator_%C3%B4nibus). Para garantir que outra pessoa consiga fazer o setup podemos:

- Escrever uma boa documentação.
- Usar ferramentas para facilitar o setup. 
- Simplificar ao máximo o setup do projeto.

**Qualidade de código** para isso temos muitas ferramentas, [filosofias aplicadas para programação](https://en.wikipedia.org/wiki/List_of_software_development_philosophies) e [design patterns](https://pt.wikipedia.org/wiki/Padr%C3%A3o_de_projeto_de_software) que podemos estudar e usar para [melhorar ou otimizar nosso código](https://en.wikipedia.org/wiki/Program_optimization#When_to_optimize) porem essa tarefa é fundamentalmente nossa não existe mágica.

[Linters](https://en.wikipedia.org/wiki/Lint_(software)) esses dependem muito da sua linguagem abaixo alguns de NodeJs:

- [eslint](https://eslint.org/)

Design patterns:

- [SOLID](https://pt.wikipedia.org/wiki/SOLID)
- [YAGNI](https://pt.wikipedia.org/wiki/YAGNI)
- [GRASP](https://pt.wikipedia.org/wiki/GRASP)
- [KISS](https://pt.wikipedia.org/wiki/Princ%C3%ADpio_KISS)
- [Unix](https://pt.wikipedia.org/wiki/Filosofia_Unix)

**Documentação** existem muitas coisas que precisam ser documentadas como APIs, código, setup do projeto entre outras, para cada uma delas existe uma ferramenta mais adequada.

APIs:

- [Swagger](https://swagger.io/docs/)

Código:

- [Comentarios no código](https://en.wikipedia.org/wiki/Comment_(computer_programming)) podendo usar ferramentas como [JsDoc](https://jsdoc.app/), [TsDoc](https://tsdoc.org/)
  
Setup do projeto: 

- [Markdown no README.md](https://pt.wikipedia.org/wiki/Markdown)

### 5️⃣ Testes

Essa é a parte onde validamos oque escrevemos, como disse antes pode ser feita antes durante o desenvolvimento. 

Tambem conseguiriamos testar após porem quando testamos durante ou antes isso ajuda a manter a qualidade do nosso código.

Podemos testar nossa aplicação de muitas formas diferentes, com [testes funcionais](https://pt.wikipedia.org/wiki/Teste_funcional) que pode ser dividida em 3 partes:

- [Testes unitarios]() que testa as menores parte do nosso código como funções e declarações tudo individualmente usando [mocks]().
- [Testes de integração]() que testa como nosso código se conversa dentro da aplicação sem mocks.
- [Testes e2e]() que testa toda nossa aplicação desde o frontend até o backend simulando um usuario.

Ou com [testes não funcionais](https://en.wikipedia.org/wiki/Non-functional_testing) que existem possibilidades:

- [Testes de carga](https://en.wikipedia.org/wiki/Scalability_testing) que valida ou entende quantos usuarios em simultaneo seu backend consegue suportar.
- [Testes de performance](https://en.wikipedia.org/wiki/Software_performance_testing) que valida em quanto tempo seu backend esta respondendo.

Para realizar esses testes existem muitas ferramentas como.

Testes unitarios:

- [Jest]()
- [Jasmine]()
- [Mocha](), [Chai](), [Sinon]() e [Istanbul]()

### 6️⃣ Implantação

Neste momento é onde temos contato com o [cloud provider]() escolhido, por este motivo temos que pensar nele antes do desenvolvimento 
pois aqui nosso código já estara preparado para o ambiente em que será executado.

Para fazer a implantação é muito importante pensar automatizar usando algum [CI]()/[CD]() desde de o primeiro deploy.

Sem setup para usar:

- [Travis]()
- [Github actions]()

Self-hosted:

- [Jenkins]()

Analise de código estatica:

- [SonarScube]()
- [Codacy]()

Cloud Providers: 

- [Azure]()
- [Amazon (AWS)]()
- [Google Cloud (GCP)]()

### 7️⃣ Manutenção

Neste passo acompanhamos como nossa aplicação esta se comportando durante o uso real, aqui pegamos falhas e pontos de melhoria. 

Quando estamos falando sobre acompanhamento um termo muito comum é [observabilidade](https://pt.wikipedia.org/wiki/Observabilidade) que é baseado em 3 pilares:

- [Logs](https://pt.wikipedia.org/wiki/Log_de_dados) são como os saidas que a aplicação da de acordo com a necessidade do desenvolvedor geralmente a cada ação importante executada. Pense que são os `console.log` que deixamos para ajudar a entender o comportamento da aplicação.
  
- [Métrics](https://pt.wikipedia.org/wiki/M%C3%A9trica_de_software) são medidas usadas para medir o desempenho da aplicação seja em [tempo de resposta](https://en.wikipedia.org/wiki/Response_time_(technology)), [consumo de cpu](https://en.wikipedia.org/wiki/CPU_time), [consumo de memoria](https://en.wikipedia.org/wiki/Memory_footprint), quantidade de erros etc...

- [Tracing](https://en.wikipedia.org/wiki/Tracing_(software)) são como logs porem que acompanham todo o ciclo de vida de uma ação iniciada em alguma parte do sistema.

Para isso temos muitas ferramentas cada uma para atender um tipo de necessidade.

- [ELK stack]()

## 🧠 Objetivo de aprendizagem

Os objetivos deste estudo são entender que o existem outras partes alem do código no desenvolvimento de um backend e que elas são tão importantes quanto o desenvolvimento, ter uma breve introdução sobre algumas ferramentas, tecnologias e processo de cada passo do ciclo de vida de um software. 

## ✔️ Entrega mínima

Tome nota dos pontos que ainda não tinha conhecimento, e levante alguns pontos de duvidas.