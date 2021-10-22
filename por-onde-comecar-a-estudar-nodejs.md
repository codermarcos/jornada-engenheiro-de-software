# 🏁 Por onde começar a estudar NodeJS

Como as linguagens exige muito pratica então nesta issue você verá por onde iniciar alguns conceitos importantes.

------------------------

- [🏁 Por onde começar a estudar NodeJS](#-por-onde-começar-a-estudar-nodejs)
  - [📦 Modules ou packages](#-modules-ou-packages)
    - [Gerenciador de pacotes](#gerenciador-de-pacotes)

## 📦 Modules ou packages

São códigos prontos que geralmente facilita ou agiliza o desenvolvimento. **Os modulos a seguir estão disponiveis apenas para o Servidor** mas se deseja seguir na engenharia Frontend é muito importante que você os conheça muito bem. Para usar um modulo ou pacote você precisa aprender como funciona o [require](https://nodejs.org/en/knowledge/getting-started/what-is-require/). Com ele podemos usar código de diferentes lugares.

Os **modules** são códigos oficiais do Node eles não precisam ser instalados ou baixados eles veem junto com o Node basta usa-los. Por exemplo:

```javascript
const fs = require('fs');
```

São chamados de built-in modules. Você pode encontrar uma lista completa deles [aqui](https://nodejs.org/api/synopsis.html)

Alguns dos mais comuns que usamos no dia a dia são:

| Pacote | Função | Exemplo |
| --- | --- | --- |
| [http](https://nodejs.org/api/http.html) | Usado para trabalhar com o [protocolo HTTP](https://pt.wikipedia.org/wiki/Hypertext_Transfer_Protocol) | [Criar um servidor http](https://nodejs.dev/learn/build-an-http-server) - [Fazer requisições http para outros servidores](https://nodejs.dev/learn/making-http-requests-with-nodejs) |
| [path](https://nodejs.org/api/path.html) | Para trabalhar com [caminhos](https://pt.wikipedia.org/wiki/Caminho_(computa%C3%A7%C3%A3o)) | [Como usar o path](https://nodejs.dev/learn/nodejs-file-paths)
| [fs](https://nodejs.org/api/fs.html) | Usado para trabalhar com arquivos. | [Criar, Deletar, Renomear um arquivo](https://nodejs.dev/learn/the-nodejs-fs-module) |

### Gerenciador de pacotes

O gerenciador de pacotes pode ser usado tanto para o lado o Javascript do navegador quanto para o Javascript do runtime. 
Os modulos vistos até esse momento são os nativos por isso não precisam instalar porem temos um infinidade de pacotes da comunidade eles podem ser baixados para isso precisamos usar o [package.json](https://docs.npmjs.com/cli/v7/configuring-npm/package-json) ele precisa seguir as especificações  da doc para funcionar então para facilitar você pode usar o seguinte comando para cria-lo.

```bash
npm init -y
```

Isso vai criar um arquivo na pasta em que foi executado o comando. Nele controlamos as versões dos pacotes que iremos instalar por exemplo.

```bash 
npm install http-server
```

O [http-server](https://www.npmjs.com/package/http-server) é usado para criar um servidor de arquivos estáticos. Depois de instalado ele deve ter alterado seu **package.json** com isso podemos iniciar o servidor usando o [npx](https://www.npmjs.com/package/npx) um pacote nativo que acompanha todas as versões do npm >= 5.2.0 (acima da cinco).

```bash
npx http-server
```

> Se quiser entender um pouco melhor o npx pode ler estas repeferencias.
> [en](https://www.freecodecamp.org/news/npm-vs-npx-whats-the-difference/) [en](https://stackoverflow.com/questions/50605219/difference-between-npx-and-npm) [en](https://blog.npmjs.org/post/162869356040/introducing-npx-an-npm-package-runner) [pt](https://pt.stackoverflow.com/questions/433378/qual-a-diferen%C3%A7a-entre-npm-e-npx) [pt](https://blog.rocketseat.com.br/conhecendo-o-npx-executor-de-pacote-do-npm/) [pt](https://walde.co/2018/02/15/conhecendo-o-npx-o-package-runner-npm/)

Isso vai iniciar um server local provendo a pasta em que estive rodando. Se quiser testar crie um arquivo **index.html** com o seguinte conteúdo na pasta que iniciou.

```html
<body>
    <h1>Olá mundo, porra nenhuma aqui é velocidade máxima.</h1>
</body>
```

Você também poderia ter instalado o pacote globalmente na sua maquina assim não teria a necessidade de ter um ```package.json``` para isso usaria o comando.

```bash
npm install http-server -g
```

Assim poderia usa-lo em qualquer pasta sem a necessidade de usar o npx ou instalar ele novamente, usando apenas.

```bash 
http-server
```