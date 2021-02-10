
# Mensagens

## Mensagens de interações


> ```Body: Mensagem de texto``` 

```json
{
  "provider": "whatsapp",
  "type": "interaction",
  "contact": {
    "phone": "+5544999999999"
  },
  "message": "Olá João, ótimo saber que gostou do produto",
  "contextId": "wdad-123123"
}
```

> ```Body: Mensagem de mídia``` 

```json

{
  "provider": "whatsapp",
  "type": "interaction",
  "mediaType": "audio",
  "mediaData": {
    "link": "https://site.com/media.png",
    "id": "d9a63dffc1e0fd7e4e507de78bb0db5c",
    "caption": "Perfume Malbec",
    "filename": "relatorio_mensal.pdf"
  },
  "contact": {
    "phone": "+5544999999999"
  },
  "contextId": "wdad-123123"
}

```

> ```Body: Mensagem de localização``` 

```json
{
  "provider": "whatsapp",
  "type": "interaction",
  "mediaType": "location",
  "location": {
    "address": "1 Hacker Way, Menlo Park, CA 94025",
    "latitude": -122.425332,
    "longitude": -37.758056,
    "name": "Facebook HQ"
  },
  "contact": {
    "phone": "+5544999999999"
  },
  "contextId": "wdad-123123"
}
```



> ```Request``` 

```bash
curl --location --request POST 'https://instantmessage.grupoboticario.digital/v1/messages'
--header 'Authorization': JWT
--data-raw body
```

```python
import requests
url = "https://instantmessage.grupoboticario.digital/v1/messages"

payload = body
headers = {
  'Authorization': JWT
}

response = requests.request("POST", url, headers=headers, data=payload)

```

```javascript
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://instantmessage.grupoboticario.digital/v1/messages',
  'headers': {
    'Authorization': JWT
  },
  body: JSON.stringify(body)

};

request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});

```

> ```Response: 200``` 

```

body
```

```json
{
  "messages": [
    {
      "messageId": "5e178088a88ad9001b6e1914",
      "contextId": "5e1789d9e73be8001ba18830",
      "interactionsId": "0398634d-5a10-4118-b44f-02d26f3a773a",
      "mediaType": "text",
      "message": "Mensagem de teste",
      "mediaData": {
        "link": "null",
        "id": "null",
        "caption": "null",
        "filename": "null"
      },
      "location": {
        "address": "1 Hacker Way, Menlo Park, CA 94025",
        "latitude": -122.425332,
        "longitude": -37.758056,
        "name": "Facebook HQ"
      },
      "to": "+5544999027914",
      "from": "+554188956674",
      "appId": "5e138ee5d53f5b001b96fa54",
      "status": "stored",
      "createdAt": "2020-01-09T19:35:36.639Z",
      "updatedAt": "2020-01-09T20:19:44.942Z"
    }
  ]
}
```


> ```Response: 400``` 

```

body
```

```json
{
  "message": "Parâmetros incorretos"
}
```


Rota para envio de mensagens de interações


### HTTP Request

`POST https://instantmessage.grupoboticario.digital/v1/messages`



## Mensagens de templates


> ```Body: Modelo de texto``` 

```json
{
  "provider": "whatsapp",
  "type": "new",
  "templateName": "nome_template",
  "contacts": [
    {
      "phone": "+5544999999999"
    }
  ]
}
```

> ```Body: Modelo de texto com variáveis``` 

```json

{
  "provider": "whatsapp",
  "type": "new",
  "templateName": "nome_template",
  "contacts": [
    {
      "1": "João",
      "2": "123456789",
      "phone": "+5544999999999"
    }
  ]
}
```

> ```Body: Modelo de mídia com header texto``` 

```json
{
  "provider": "whatsapp",
  "type": "new",
  "templateName": "nome_template",
  "contacts": [
    {
      "1": "123456789",
      "2": "22/03/2020",
      "header": {
        "1": "João"
      },
      "phone": "+5544999999999"
    }
  ]
}
```

> ```Body: Modelo de mídia com header imagem/video/documento```

```json

{
  "provider": "whatsapp",
  "type": "new",
  "templateName": "nome_template",
  "contacts": [
    {
      "1": "123456789",
      "2": "22/03/2020",
      "header": {
        "link": "https://site.com/media.png",
        "id": "d9a63dffc1e0fd7e4e507de78bb0db5c"
      },
      "phone": "+5544999999999"
    }
  ]
}
```

> ```Body: Modelo de botões dinâmicos``` 

```json
{
  "provider": "whatsapp",
  "type": "new",
  "templateName": "nome_template",
  "contacts": [
    {
      "1": "123456789",
      "2": "22/03/2020",
      "buttons": {
        "index": 0,
        "type": "url",
        "content": "hash"
      },
      "phone": "+5544999999999"
    }
  ]
}
```

> ```Request``` 

```bash
curl --location --request POST 'https://instantmessage.grupoboticario.digital/v1/messages'
--header 'Authorization': JWT
--data-raw body
```

```python
import requests
url = "https://instantmessage.grupoboticario.digital/v1/messages"

payload = body
headers = {
  'Authorization': JWT
}

response = requests.request("POST", url, headers=headers, data=payload)

```

```javascript
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://instantmessage.grupoboticario.digital/v1/messages',
  'headers': {
    'Authorization': JWT
  },
  body: JSON.stringify(body)

};

request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});

```

> ```Response: 200``` 

```

body
```

```json
{
  "messages": [
    {
      "messageId": "5e178088a88ad9001b6e1914",
      "contextId": "5e1789d9e73be8001ba18830",
      "interactionsId": "0398634d-5a10-4118-b44f-02d26f3a773a",
      "mediaType": "text",
      "message": "Mensagem de teste",
      "to": "+5544999027914",
      "from": "+554188956674",
      "appId": "5e138ee5d53f5b001b96fa54",
      "status": "stored",
      "createdAt": "2020-01-09T19:35:36.639Z",
      "updatedAt": "2020-01-09T20:19:44.942Z"
    }
  ]
}
```


> ```Response: 400``` 

```

body
```

```json
{
  "message": "Parâmetros incorretos"
}
```


Rota para envio de mensagens de templates


### HTTP Request

`POST https://instantmessage.grupoboticario.digital/v1/messages`



## Consulta de interações


> ```Request``` 

```bash
curl --location --request GET 'https://instantmessage.grupoboticario.digital/v1/messages/interactions'
--header 'Authorization': JWT
```

```python
import requests
url = "GET https://instantmessage.grupoboticario.digital/v1/messages/interactions"

payload={}
headers = {
  'Authorization': JWT
}

response = requests.request("GET", url, headers=headers, data=payload)

```

```javascript
var request = require('request');
var options = {
  'method': 'GET',
  'url': 'https://instantmessage.grupoboticario.digital/v1/messages/interactions',
  'headers': {
    'Authorization': JWT
  },
};

request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});

```


> ```Response: 200``` 

```
body
```

```json

{
  "interactionList": [
    {
      "interactionId": "5e80e5fe487dbb9f8d035456",
      "interactionsId": "123456-1231456-21456-213456",
      "clientData": {
        "name": "User teste",
        "timeLastMessage": "2020-06-09T19:44:03.508Z"
      },
      "lastMessage": {
        "messageId": "123456789123456",
        "mediaData": {
          "link": "https://site.com/media.png",
          "id": "d9a63dffc1e0fd7e4e507de78bb0db5c",
          "caption": "Descrição arquivo",
          "filename": "Nome do documento"
        },
        "mediaType": "text",
        "message": "Mensagem de teste",
        "failCode": 420,
        "failMessage": "Mensagem de falha",
        "contextId": "123456789123456",
        "interactionsId": "123456-1231456-21456-213456",
        "status": "read",
        "to": "+5544999999999",
        "from": "+555544999999999",
        "appId": "123456789123456",
        "createdAt": "2020-01-09T20:15:21.419Z",
        "updatedAt": "2020-01-09T20:15:21.419Z"
      },
      "to": "+5544999027914",
      "from": "+554188956674",
      "contextId": "5e1789d9e73be8001ba18830",
      "appId": "5e138ee5d53f5b001b96fa54",
      "createdAt": "2020-01-09T19:35:36.639Z",
      "updatedAt": "2020-01-09T20:19:44.942Z"
    }
  ],
  "pagination": {
    "totalPages": 1,
    "currentPage": 1,
    "itensPage": 2,
    "totalItens": 2
  }
}
```


> ```Response: 401``` 

```
body
```

```json
{
  "message": "Não autorizado"
}
```


> ```Response: 422``` 

```
body
```

```json
{
  "message": "Parâmetros incorretos"
}
```


Rota para buscar todas as interações do aplicativo vinculado ao token enviado.
As interações possuem o objeto lastMessage que contem a última mensagem enviada na conversa

### URL Parameters

<br>

Parameter | Description | Example
--------- | ----------- | --------
page | Número da página (opcional) | 1
limit | Limite de itens por página (opcional) | 10
appid | ID do aplicativo | 5dfd7753d663b30027d21747
allInteraction | Valor para identificar se deve consultar todas as conversas ou não. | true: Para trazer todas as conversas <br> false: Para trazer somente as respondidas <br> notanswered: Para trazer as não respondidas



### HTTP Request

`GET https://instantmessage.grupoboticario.digital/v1/messages/interactions`



## Consulta 


> ```Request``` 

```bash
curl --location --request GET 'https://instantmessage.grupoboticario.digital/v1/messages/{?phone}{&page}{&limit}{&status}{&contextId}{&dateInitial}{&dateEnd}{&search}'
--header 'Authorization': JWT
```

```python
import requests
url = "https://instantmessage.grupoboticario.digital/v1/messages/{?phone}{&page}{&limit}{&status}{&contextId}{&dateInitial}{&dateEnd}{&search}"
payload={}
headers = {
  'Authorization': JWT
}

response = requests.request("GET", url, headers=headers, data=payload)

```

```javascript
var request = require('request');
var options = {
  'method': 'GET',
  'url': 'https://instantmessage.grupoboticario.digital/v1/messages/{?phone}{&page}{&limit}{&status}{&contextId}{&dateInitial}{&dateEnd}{&search}',
  'headers': {
    'Authorization': JWT
  },
};

request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});

```

> ```Response: 200``` 

```
body
```

```json
{
  "isMinorThan24Hours": true,
  "messagesList": [
    {
      "messageId": "i3i4321d",
      "to": "+554499999999",
      "from": "+554499999998",
      "appId": "5dfd7753d663b30027d21747",
      "interactionsId": "8436fda0-b55f-4743-a4ac-211526bf53a6",
      "contextId": "5e176cbea12be50027aa0ce2",
      "message": "Bom dia",
      "mediaType": "text",
      "mediaData": {
        "link": "https://site.com/media.png",
        "id": "d9a63dffc1e0fd7e4e507de78bb0db5c",
        "caption": "Descrição arquivo",
        "filename": "Nome do documento"
      },
      "status": "read",
      "createdAt": "2019-10-14T20:21:12.648Z",
      "updatedAt": "2019-10-14T20:21:12.648Z"
    }
  ],
  "pagination": {
    "totalPages": 1,
    "currentPage": 1,
    "itensPage": 2,
    "totalItens": 2
  }
}
```



> ```Response: 401``` 

```
body
```

```json
{
  "message": "Não autorizado"
}
```



> ```Response: 400``` 

```
body
```

```json
{
  "message": "Parâmetros incorretos"
}
```

Rota para listar todas as mensagens de uma conversa.

<aside class = "warning">
   Caso não tenha parâmetro, o valor da padrão da paginação é page: 1 e limit: 30
</aside>

### URL Parameters

<br>

Parameter | Description | Example
--------- | ----------- | --------
phone | Número de telefone | +5544999999999
page | Número da página (opcional) | 1
limit | Limite de itens por página (opcional) | 30
status | (opcional) | read
contextId | (opcional) | atendente-123
dateInitial | (opcional) | YYYMMDDHHmm
dateEnd | (opcional) | YYYMMDDHHmm
search | (opcional) | texto


### HTTP Request

`GET https://instantmessage.grupoboticario.digital/v1/messages/{?phone}{&page}{&limit}{&status}{&contextId}{&dateInitial}{&dateEnd}{&search}`


## Exclusão  


> ```Request``` 

```bash
curl --location --request DELETE 'https://instantmessage.grupoboticario.digital/v1/messages/{{phone}}'
--header 'Authorization': JWT
```

```python
import requests
url = "https://instantmessage.grupoboticario.digital/v1/messages/{{phone}}"

payload={}
headers = {
  'Authorization': JWT
}

response = requests.request("DELETE", url, headers=headers, data=payload)

```

```javascript
var request = require('request');
var options = {
  'method': 'DELETE',
  'url': 'https://instantmessage.grupoboticario.digital/v1/messages/{{phone}}',
  'headers': {
    'Authorization': JWT
  },
};

request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});

```


> ```Response: 200``` 


Rota para exclusão de todas as mensagens de um número

### URL Parameters

<br>

Parameter | Description | Example
--------- | ----------- | --------
phone | Número de telefone | 5544999999999


### HTTP Request

<br>

`DELETE https://instantmessage.grupoboticario.digital/v1/messages/{{phone}}`


