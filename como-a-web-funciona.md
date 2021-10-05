 # 🌍 Como a web funciona

Vamos ver uma parte superficial do funcionamento da web desde o momento que um cliente abre o browser e decide acessar alguma informação.

------------------------

- [🌍 Como a web funciona](#-como-a-web-funciona)
  - [🌐 Oque é a internet](#-oque-é-a-internet)
    - [Os principais elementos da navegação](#os-principais-elementos-da-navegação)
      - [🌐 Internet](#-internet)
      - [🚗 TCP/IP](#-tcpip)
      - [🗺️ DNS](#️-dns)
      - [👤 Cliente)](#-cliente)
      - [🖧 Servidor)](#-servidor)
  - [🧠Objetivo de aprendizagem](#objetivo-de-aprendizagem)
  - [✔️ Entrega mínima](#️-entrega-mínima)

## 🌐 Oque é a [internet](https://pt.wikipedia.org/wiki/Internet)

É o principal elemento que permite que a [web](https://pt.wikipedia.org/wiki/World_Wide_Web), e muitas outras coisas existam.
Pense que a internet é como as ruas e estradas, que ligam um lugar ao outro. Para ficar mais claro imagine o seguinte cenário: 

<p align="center">
   <img src="https://www.tuseguro.com/pe/pe/images/images/Blog/Contenido_Epico/prepara-tu-auto-viaje-5-tips-disfrutar/auto_mapa.jpg" alt="mapa" />
</p>

*Quando você precisa fazer compras pega seu carro vai até o mercado e logo em seguida volta pra casa*.

### Os principais elementos da navegação

Agora vamos ver os principais elementos desta navegação, **não se preocupe se não entender todos elementos agora**. Conforme estiver atuando vai entende-los melhor com o passar do tempo.


#### 🌐 Internet

A internet neste caso permitiu seu deslocamento para acessar o mercado e conseguir oque você precisava, e voltar para sua casa.

#### 🚗 [TCP/IP](https://pt.wikipedia.org/wiki/TCP/IP)

É a forma como o cliente e o mercado se comunicam, neste caso seria o carro, bicicleta ou qualquer que seja o meio de transporte. 

> 📌 O [IP](https://pt.wikipedia.org/wiki/Endere%C3%A7o_IP) como podemos ver em seu nome ele é um dos elementos mais importantes do TCP/IP ele representa o endereço, assim como o mercado e a nossa casa tem endereço, nosso computador ou dispositivo com acesso a internet também tem um endereço. Sua principal versão é a [Ipv4](https://pt.wikipedia.org/wiki/IPv4), porem nesta versão ele contem algumas limitações que com o crescimento da internet seu formato não suportaria o numero de dispositivos conectados, por este motivo esta aos poucos sendo substituído por sua nova versão o [Ipv6](https://pt.wikipedia.org/wiki/IPv6).
>
> **Exemplo de ipv4**: 172.217.14.227
> **Exemplo de ipv6**: 2a00:1450:4001:821::200e

> 📝O [HTTP](https://pt.wikipedia.org/wiki/Hypertext_Transfer_Protocol) ou [HTTPS](https://pt.wikipedia.org/wiki/Hyper_Text_Transfer_Protocol_Secure) são os protocolos mais usados por aplicações para comunicar o cliente ao servidor. Ele seria como a linguagem usada para o cliente se comunicar com mercado.

#### 🗺️ [DNS](https://pt.wikipedia.org/wiki/Sistema_de_Nomes_de_Dom%C3%ADnio)

Assim como quando vamos a um lugar que não conhecemos o endereço usamos o GPS, o DNS (Domain Name Service) é responsável por identificar o caminho e informar o verdadeiro endereço para nós. Ele transforma aquele endereço bonitinho que acessamos [www.google.com.br](https://www.google.com.br/) chamado de [domínio](https://pt.wikipedia.org/wiki/Nome_de_dom%C3%ADnio) em um enderenço IP [//172.217.14.227](//172.217.14.227).

#### 👤 [Cliente](https://pt.wikipedia.org/wiki/Cliente_(computa%C3%A7%C3%A3o))

Neste caso um dos atores é você o Cliente que frequenta o mercado. Na Web seria o **usuário**, também chamado de **cliente** que acessa um determinado site, conteúdo ou faz uma pesquisa. O acesso do cliente pode ser feito por muitas formas diferentes por enquanto imagine que esse acesso foi feito através de um [navegador](https://pt.wikipedia.org/wiki/Navegador_web) como chrome  ou firefox.

#### 🖧 [Servidor](https://pt.wikipedia.org/wiki/Servidor_(computa%C3%A7%C3%A3o))

Outro ator muito importante é o Servidor que no caso seria o mercado. Na Web o Servidor é responsável por armazenar o conteúdo, que pode ser desde um site até dados fornecidos pelo usuário através de [mensagens](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Messages), ele também é responsável por processar os [pedidos (mais conhecido como "request")](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Messages#requisi%C3%A7%C3%B5es_http) dos clientes e retornar uma [resposta (mais conhecido como "response")](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Messages#respostas_http)  oque foi requisitado. 

Então agora que entendemos quem são os atores no final temos o seguinte fluxo:

<p align="center">
   <img src="https://drive.google.com/u/0/uc?id=1IG-LHsCF56Brm2NrcM4sQJl_TrsqBsQl&export=download" alt="como funciona a web" />
</p>

1. O usuário usa pode usar seu celular, computador ou qualquer outro dispositivo com acesso a um navegador e internet.
2. O navegador solicita ao servidor de DNS o endereço IP. 
3. O servidor de DNS busca pelo endereço IP seguindo uma ordem de busca por exemplo: `www.google.com` -> `.com` -> `google.com` -> `www.google.com`
4. Encontrado o IP o servidor de DNS retorna para o cliente que solicitou.
5. O navegador com o endereço IP solicita o conteúdo ao servidor usando HTTP/S
6. O servidor recebe a solicitação e responde enviando ao cliente que solicitou os arquivo solicitado.

## 🧠Objetivo de aprendizagem

O Objetivo deste estudo é aprender um pouco sobre o funcionamento da web e se familiarizar com alguns nomes como *client*, *server*, *DNS*, *Web* e *Internet*.

## ✔️ Entrega mínima

Comente aqui algo que aprendeu estudando que não conhecia, se já tiver domínio sobre todos os temas apresentados busque se aprofundar em algum deles como DNS e lembre-se de comentar aqui oque foi encontrado.