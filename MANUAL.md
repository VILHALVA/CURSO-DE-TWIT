# MANUAL
## 1. INSTALAÇÃO:
Para começar, você precisa ter Node.js instalado no seu sistema. Se ainda não tiver, baixe e instale a versão mais recente do Node.js através do [site oficial](https://nodejs.org/).

1. Abra o terminal ou prompt de comando.

2. Instale o Twit globalmente usando npm (Node Package Manager):
   ```
   npm install -g twit
   ```

## 2. CONFIGURAÇÃO DO PROJETO:
Vamos criar um novo diretório para o projeto e configurar as credenciais necessárias do Twitter.

1. Crie um novo diretório para o projeto e acesse-o:
   ```
   mkdir twit-bot
   cd twit-bot
   ```

2. Inicialize um novo projeto Node.js (se ainda não o fez):
   ```
   npm init -y
   ```

## 3. CONFIGURAÇÃO DAS CREDENCIAIS DO TWITTER:
Para usar a API do Twitter, você precisa de credenciais de desenvolvedor. Siga estes passos para obter suas credenciais:

1. Acesse o [Twitter Developer Portal](https://developer.twitter.com/en/portal/projects-and-apps).

2. Crie um novo projeto ou aplicativo e obtenha as seguintes chaves:
   - API Key (chave de API)
   - API Secret Key (segredo da chave de API)
   - Access Token (token de acesso)
   - Access Token Secret (segredo do token de acesso)

3. Guarde essas informações em um local seguro.

## 4. CONFIGURAÇÃO DO TWIT NO PROJETO:
1. Instale o Twit localmente no projeto:
   ```
   npm install twit --save
   ```

2. Crie um arquivo `config.js` dentro do diretório do seu projeto e adicione as credenciais obtidas do Twitter:
   ```javascript
   module.exports = {
     consumer_key: 'SUA_CONSUMER_KEY',
     consumer_secret: 'SUA_CONSUMER_SECRET',
     access_token: 'SEU_ACCESS_TOKEN',
     access_token_secret: 'SEU_ACCESS_TOKEN_SECRET',
   };
   ```

   Substitua `'SUA_CONSUMER_KEY'`, `'SUA_CONSUMER_SECRET'`, `'SEU_ACCESS_TOKEN'` e `'SEU_ACCESS_TOKEN_SECRET'` pelos valores correspondentes das suas credenciais.

## 5. CRIANDO O PRIMEIRO PROJETO COM TWIT:
Vamos criar um simples bot que envia um tweet.

1. Crie um arquivo `bot.js` dentro do diretório do seu projeto:

   ```javascript
   const Twit = require('twit');
   const config = require('./config');

   const T = new Twit(config);

   // Enviar um tweet
   T.post('statuses/update', { status: 'Olá, Twitter!' }, (err, data, response) => {
     if (err) {
       console.log('Erro ao tweetar:', err);
     } 
     else {
       console.log('Tweet enviado com sucesso!');
     }
   });
   ```

2. Execute o arquivo `bot.js` no terminal para enviar um tweet:
   ```
   node bot.js
   ```

   Verifique a sua conta do Twitter para ver o tweet enviado pelo bot.

## CONCLUSÃO:
Parabéns! Você configurou com sucesso o Twit, criou suas credenciais do Twitter, configurou-as no projeto Node.js e enviou seu primeiro tweet usando o Twit. A partir daqui, você pode explorar mais funcionalidades do Twit para criar bots mais sofisticados e interativos no Twitter.