
# Webhook

## Recebimento de mensagens 

No cadastro de Webhook é possível customizar a URL das requests.

<aside class = "warning">
   As URLs abaixo são apenas para exemplificar o funcionamento do Webhook, suas URLs deverão ser cadastradas por um administrado juntamente com o aplicativo que irá realizar a integração.
</aside>

> ```Body: Mensagem de resposta``` 

```json

{
  "event": {
    "messageId": "i3i4321d",
    "type": "response"
  },
  "clientData": {
    "number": "+5544999999999",
    "name": "Maria da Silva",
    "timeLastMessage": "2020-06-18T17:07:51.271Z"
  },
  "message": {
    "messageId": "5e178088a88ad9001b6e1914",
    "contextId": "5e1789d9e73be8001ba18830",
    "interactionsId": "0398634d-5a10-4118-b44f-02d26f3a773a",
    "mediaType": "document",
    "message": "Mensagem de teste",
    "mediaData": {
      "link": "http://linkteste.com/doc.pdf",
      "caption": "Descrição da midia",
      "filename": "nome-arquivo.pdf"
    },
    "to": "+5544999027914",
    "from": "+554188956674",
    "appId": "5e138ee5d53f5b001b96fa54",
    "status": "stored",
    "createdAt": "2020-01-09T19:35:36.639Z",
    "updatedAt": "2020-01-09T20:19:44.942Z"
  }
}

```

> ```Body: Status da mensagem``` 

```json

{
  "event": {
    "messageId": "i3i4321d",
    "type": "status",
    "status": "sent | delivered | read"
  },
  "message": {
    "messageId": "5e178088a88ad9001b6e1914",
    "contextId": "5e1789d9e73be8001ba18830",
    "interactionsId": "0398634d-5a10-4118-b44f-02d26f3a773a",
    "mediaType": "document",
    "message": "Mensagem de teste",
    "mediaData": {
      "link": "http://linkteste.com/doc.pdf",
      "caption": "Descrição da midia",
      "filename": "nome-arquivo.pdf"
    },
    "to": "+5544999027914",
    "from": "+554188956674",
    "appId": "5e138ee5d53f5b001b96fa54",
    "status": "stored",
    "createdAt": "2020-01-09T19:35:36.639Z",
    "updatedAt": "2020-01-09T20:19:44.942Z"
  }
}

```


> ```Request``` 

```bash
curl --location --request POST 'https://instantmessage.grupoboticario.digital/endereco-webhook-integracao'
--data-raw body
```


```python


import requests
url = "https://instantmessage.grupoboticario.digital/endereco-webhook-integracao"

payload= body
headers = {}

response = requests.request("POST", url, headers=headers, data=payload)

```

```javascript
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://instantmessage.grupoboticario.digital/endereco-webhook-integracao',
  'headers': {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(body)
};

request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});

```

### HTTP Request

`POST https://instantmessage.grupoboticario.digital/endereco-webhook-integracao`


