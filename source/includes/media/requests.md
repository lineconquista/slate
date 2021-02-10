
# Media

## Upload 


> ```Request``` 

```bash
curl --location --request POST 'https://instantmessage.grupoboticario.digital/v1/medias'
--header 'Authorization': JWT
--header 'Content-Type:' <content-type da mídia>
--body binary
```

```python
import requests
url = "https://instantmessage.grupoboticario.digital/v1/medias"

payload = binary
headers = {
  'Authorization': JWT,
  'Content-Type': <content-type da mídia>
}

response = requests.request("POST", url, headers=headers, data=payload)

```

```javascript
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://instantmessage.grupoboticario.digital/v1/medias',
  'headers': {
    'Authorization': JWT,
    'Content-Type': <content-type da mídia>
  },
  body: file contents here

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
  "id": "d9a63dffc1e0fd7e4e507de78bb0db5c"
}
```


> ```Response: 400``` 

```
body
```

```json
{
   "error": "É necessário enviar a mídia no corpo da requisição"
}
```

É necessário enviar o binário da midia no corpo da requisição e como retorno irá obter o id da midia.
Uma limitação deste endpoint é que o binário deve ter no máximo 10mb. 


### HTTP Request

`POST https://instantmessage.grupoboticario.digital/v1/medias`

<aside class=warning>
Caso seja necessário o upload de arquivos maiores, utilize o modelo assíncrono.
</aside>

### Fluxo de utilização

<br>

<img class = "tab" src= "./images/upload_find_media.png"  width="80%"/> 

<img class = "tab" src= "./images/upload_send_media_message.png"  width="80%"/> 



## Upload Assíncrono


> ```Request``` 

```bash
curl --location --request GET 'https://instantmessage.grupoboticario.digital/v1/medias/async'
--header 'Authorization': JWT
--header 'Content-Type': <content-type da mídia>
```

```python
import requests
url = "https://instantmessage.grupoboticario.digital/v1/medias/async"

payload={}
headers = {
  'Authorization': JWT,
  'Content-Type': <content-type da mídia>
}

response = requests.request("GET", url, headers=headers, data=payload)

```

```javascript
var request = require('request');
var options = {
  'method': 'GET',
  'url': 'https://instantmessage.grupoboticario.digital/v1/medias/async',
  'headers': {
    'Authorization': JWT,
    'Content-Type': <content-type da mídia>
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
  "id": "d9a63dffc1e0fd7e4e507de78bb0db5c",
  "url": "<upload url>"
}
```


> ```Response: 400``` 


```
body
```

```json
{
  "error": "É necessário informar o header Content-Type"
}
```


O upload assíncrono de mídias não possui limite de tamanho, porém o processo é realizado em duas etapas:

- Deve ser realizada uma requisição informando o “Content-Type” da mídia que deseja fazer upload. Este endpoint retornará o ID da mídia e uma URL para a qual a mídia deverá ser enviada.
- Deve ser enviada requisição PUT para esta URL com a mídia como corpo.

<br>

<aside class = "success">
  Após o upload, você poderá enviar a mensagem com o ID da mídia recebido na primeira requisição.
</aside>

### HTTP Request

`GET https://instantmessage.grupoboticario.digital/v1/medias/async`



## Consulta 


> ```Request``` 

```bash
curl --location --request GET 'https://instantmessage.grupoboticario.digital/v1/medias/{{id}}'
--header 'Authorization': JWT
```

```python
import requests
url = "https://instantmessage.grupoboticario.digital/v1/medias/{{id}}"

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
  'url': 'https://instantmessage.grupoboticario.digital/v1/medias/{{id}}',
  'headers': {
    'Authorization': JWT
  },
};

request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});

```

> ```Response: 302``` 

```
header: "Location: URL media"

```


> ```Response: 400``` 

```
body
```

```json
{
  "error": "Arquivo não encontrado!"
}
```


### URL Parameters

<br>

Parameter | Description | Example
--------- | ----------- | --------
id | id da mídia retornada no método de upload |  d9a63dffc1e0fd7e4e507de78bb0db5c


### HTTP Request

<br>

`GET https://instantmessage.grupoboticario.digital/v1/medias/{{id}}`


