# 🔤 Escolhendo uma linguagem de programação

Para escolher uma linguagem recomendo uma das [Linguagens mais eficientes para Computação em Nuvem](#LmepCeN). Abaixo vamos ver alguns pontos que recomendamos levar em consideração ao escolher uma linguagem!

------------------------

- [🔤 Escolhendo uma linguagem de programação](#-escolhendo-uma-linguagem-de-programação)
  - [🧮 Características de uma linguagem](#-características-de-uma-linguagem)
    - [Comunidade e atividade](#comunidade-e-atividade)
    - [Interpretada ou compilada](#interpretada-ou-compilada)
  - [☁️ Linguagens mais eficientes para Computação em Nuvem](#️-linguagens-mais-eficientes-para-computação-em-nuvem)
  - [🧠Objetivo de aprendizagem](#objetivo-de-aprendizagem)
  - [✔️ Entrega mínima](#️-entrega-mínima)

## 🧮 Características de uma linguagem

Quando comparamos uma linguagem com a outra temos diferentes características que ajudam a classificar ela e decidir em que cenários ela seria mais eficiente. Abaixo levantamos alguns pontos para ajudar a entender oque podemos comparar.

### Comunidade e atividade

**Comunidade** é o grupo de pessoas que usam, contribuem ou mantem certa tecnologia. 

Pontos importantes a serem levados em consideração na comunidade:

- **Numero de pacotes** Pacotes são códigos prontos que temos para realizar determinada tarefa.
	- [Rust](https://crates.io/) No Rust são chamados de *crates* e tem mais de **61.2 mil** publicados.
	- [GoLang](https://pkg.go.dev/) No Go são chamados de *modules* não tem esse numero em um lugar especifico, é provável que fique entre *Rust* e *Python*.
	- [NodeJS](https://www.npmjs.com/) No NodeJS de *packages* e tem mais de **1.6 milhões** publicados.
	- [Python](https://pypi.org/) No Python são chamados de *packages* e tem mais de **305.7 mil** publicados.

- **Numero de repositórios ou arquivos** Os repositórios são onde armazenamos versões do nosso código de forma publica ou privada.
	- [Rust](https://github.com/search?q=extension%3Ars) tem aproximadamente mais de **5 Milhões** de arquivos públicos no Github.
	- [GoLang](https://github.com/search?q=extension%3Ago) tem aproximadamente mais de **72 Milhões** de arquivos públicos no Github.
	- [NodeJS](https://github.com/search?q=extension%3Ajs+extension%3Ats) tem aproximadamente mais de **3.14 Bilhões** de arquivos públicos no Github.
	- [Python](https://github.com/search?q=extension%3Apy+extension%3Apyc+extension%3Apyo+extension%3Apyd) tem aproximadamente mais de **680 Milhões** de arquivos públicos no Github.
	
- **Numero de starts (Estrelas)** Isso não diz muita coisa afinal pode ter pessoas que não deram suas estrelas porem usam a linguagem mas ajuda a ter uma certa noção.

**Atividade** é oque acontece com a linguagem no decorrer do tempo.

- **Data dos últimos commits** A tecnologia evolui muito rápido para garantir que a linguagem esta acompanhado essa evolução ela deve ter pessoas trabalhando nela constantemente.

- **Ultimas mudanças** Podemos ver qual a frequência de atualização da linguagem e acompanhar para onde a linguagem esta caminhando para isso é legal acompanhar as ultimas features.


### Interpretada ou compilada

As [linguagens interpretadas](https://pt.wikipedia.org/wiki/Linguagem_interpretada) como (**NodeJS** e **Python**) o responsável pela execução **não é o sistema operacional ou processador** mesmo que passe por um processo de compilação no final são interpretadores são os executores do código-fonte. 

As [linguagens compiladas](https://pt.wikipedia.org/wiki/Linguagem_compilada) como (**Rust** e **Go**) acontece uma tradução do código fonte para código de máquina para que possa ser executado diretamente pelo sistema operacional ou processador.

As duas podem ter muitas [diferenças](https://pt.stackoverflow.com/questions/77070/qual-a-diferen%C3%A7a-entre-linguagem-compilada-para-linguagem-interpretada) algumas delas são:

- **Confiabilidade**: linguagens compiladas geralmente são mais confiáveis graças às suas diversas etapas de validação e otimização durante a compilação.
- **Flexibilidade**: linguagens interpretadas geralmente são independente da plataforma já que são interpretadores executam o código.
- **Consumo de memória**: linguagens interpretadas geralmente consomem mais memória quando comparado com compiladas.
- **Tempo de execução**: linguagens interpretadas tendem a ser mais lentas quando comparado com compiladas.

Se quiser pode seguir alguns links
[pt](https://pt.stackoverflow.com/questions/102787/qual-%C3%A9-a-vantagem-de-usar-linguagens-que-compila-pra-outras-linguagens) [pt](https://blog.geekhunter.com.br/metodos-de-traducao-compiladores-ou-interpretadores/) [pt](https://www.luby.com.br/programacao/diferenca-entre-compilacao-e-interpretacao/) [en](https://stackoverflow.com/questions/3265357/compiled-vs-interpreted-languages) [en](https://www.freecodecamp.org/news/compiled-versus-interpreted-languages/)

## ☁️ Linguagens mais eficientes para Computação em Nuvem

O que torna uma linguagem eficiente para computação em nuvem? Abaixo temos alguns pontos:

- **Comece rapidamente**: Algumas aplicações o volume de uso sobe muito rápido com isso também precisam escalar rápido se puderem inicializar replicas dela mesma em alguns micro segundos acaba sendo muito mais eficiente.

- **Tamanho pequeno**: Linguagens que precisam de menos espaço em termos de consumo de disco (memória) podem ser iniciadas com muito mais rapidez. Isso pode reduzir significativamente o tempo de inicialização.

- **Baixo consumo de memória e cpu**: Quanto menor o consumo mais réplicas caberão em um lugar só, tornando-o mais barato de operar e mais fácil de escalar.

Sabendo disso linguagens compiladas quase sempre serão mais rápidas e leve do que uma linguagem interpretada temos as: 

:rocket: As que recomendamos sendo as **MAIS** eficientes em ordem da melhor para a pior:

1. [Rust](https://www.rust-lang.org/) Uma linguagem compilada extremamente rápida com eficiente gerencia de memória muito usada como alternativa a *C/C++*.

2. [Go](https://golang.org/) Uma linguagem compilada focada em produtividade e programação concorrente muito usada na comunidade *Devops* e *Backend*.

3. [Javascript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) / [NodeJS](https://nodejs.org/en/) - Uma linguagem interpretada que conta com a maior volume de atividades justamente por poder ser usada tanto *client-side* quanto *server-side* ou seja na comunidade *Frontend* e *Backend*.

4. [Python](https://www.python.org/) Uma linguagem interpretada muito usada para trabalhar com larga escala de dados por ter muitas bibliotecas e estruturas para a análise de dados prontas desenvolvidas pela comunidade.

:turtle: E as principais que **NÃO** recomendamos sendo as **MENOS** eficientes:

- **Java**: Pelo fato de precisar da JVM as VMs têm algumas desvantagens como serem lentas para iniciar, usarem muita memória além de sobrepor algumas  responsabilidades em ambientes que contam com orquestradores.

## 🧠Objetivo de aprendizagem

O Objetivo deste estudo é entender como escolhemos uma linguagem para determinados tipos de problemas. Onde usar não usar, prós e contras de cada uma delas levando em consideração nosso principal cenário a [nuvem](https://pt.wikipedia.org/wiki/Computa%C3%A7%C3%A3o_em_nuvem), também o cenário de aprendizagem na busca de conteúdo.

## ✔️ Entrega mínima

Escolha sua primeira linguagem de programação, comente nesta issue o racional para sua escolha.