
# Whatsapp

## Status do número do whatsapp 


> ```Request``` 

```bash
curl --location --request GET 'https://instantmessage.grupoboticario.digital/v1/whatsapp/contacts/:number'
--header 'Authorization': JWT
```

```python
import requests
url = "https://instantmessage.grupoboticario.digital/v1/whatsapp/contacts/:number"

payload = {}
headers = {
  'Authorization': JWT
}

response = requests.request("GET", url, headers=headers, data=payload)

```

```javascript
var request = require('request');
var options = {
  'method': 'GET',
  'url': 'https://instantmessage.grupoboticario.digital/v1/whatsapp/contacts/:number',
  'headers': {
    'Authorization': JWT
  }
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
  "valid": true
}
```


Consulta o status de um determinado número 


### HTTP Request

`GET https://instantmessage.grupoboticario.digital/v1/whatsapp/contacts/:number`


## Lista de janelas abertas


> ```Request``` 

```bash
curl --location --request GET 'https://instantmessage.grupoboticario.digital/v1/whatsapp/chatwindow'
--header 'Authorization': JWT
```

```python
import requests
url = "GET https://instantmessage.grupoboticario.digital/v1/whatsapp/chatwindow"

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
  'url': 'https://instantmessage.grupoboticario.digital/v1/whatsapp/chatwindow',
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
  "contacts": [
    {
      "phone": "+5500999911111",
      "name": "João Silva",
      "closesIn": "2020-09-03T12:49:59.496Z"
    }
  ]
}
```


Consulta de janelas abertas para o número.

### HTTP Request

`GET https://instantmessage.grupoboticario.digital/v1/whatsapp/chatwindow`



## Status da janela de conversa 


> ```Request``` 

```bash
curl --location --request GET 'https://instantmessage.grupoboticario.digital/v1/whatsapp/chatwindow/:number'
--header 'Authorization': JWT
```

```python
import requests
url = "https://instantmessage.grupoboticario.digital/v1/whatsapp/chatwindow/:number"
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
  'url': 'https://instantmessage.grupoboticario.digital/v1/whatsapp/chatwindow/:number',
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
<!-- 
`` 
Content-Type não especificado 
`` -->

```
body
```

```json
{
  "open": true,
  "closesIn": "2020-09-03T12:49:59.496Z"
}
```

Consulta status da janela para o contato.

### HTTP Request

`GET https://instantmessage.grupoboticario.digital/v1/whatsapp/chatwindow/:number`


## Lista de templates  


> ```Request``` 

```bash
curl --location --request GET 'https://instantmessage.grupoboticario.digital/v1/whatsapp/templates'
--header 'Authorization': JWT
```

```python
import requests
url = "https://instantmessage.grupoboticario.digital/v1/whatsapp/templates"

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
  'url': 'https://instantmessage.grupoboticario.digital/v1/whatsapp/templates',
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
  "data": [
    {
      "facebookId": "708927800029953",
      "category": "ACCOUNT_UPDATE",
      "components": [
        {
          "type": "HEADER",
          "format": "TEXT",
          "text": "Hi {{1}}"
        },
        {
          "type": "BODY",
          "text": "Template text {{1}}"
        },
        {
          "type": "FOOTER",
          "text": "Footer text"
        },
        {
          "type": "BUTTONS",
          "buttons": [
            {
              "type": "PHONE_NUMBER",
              "text": "Make a call",
              "phone_number": "+5511976333566"
            },
            {
              "type": "QUICK_REPLY",
              "text": "I agree"
            },
            {
              "type": "URL",
              "text": "Visit our website",
              "url": "`http://website.com/{{1}}"
            }
          ]
        }
      ],
      "language": "pt_BR",
      "name": "template_name",
      "status": "APPROVED"
    }
  ],
  "next": "NWZiZDllOGVjZDhmYjA3ODQyNDg3NjNm",
  "previous": "NWZiZDllOGVjZDhmYjA3ODQyNDg3NjNm"
}
```

Gerenciamento de templates cadastrados no Facebook Business


### URL Parameters

<br>

Parameter | Description | Example
--------- | ----------- | --------
name | filtro de nome do template (opcional) | reply
next | token de cursor para a página seguinte (opcional) | NWZiZDllOGVjZDhmYjA3ODQyNDg3NjNm
previous | token de cursor para a página anterior (opcional) | NWZiZDllOGVjZDhmYjA3ODQyNDg3NjNm


### HTTP Request

<br>

`GET https://instantmessage.grupoboticario.digital/v1/whatsapp/templates`


