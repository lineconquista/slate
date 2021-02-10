
# Informações Gerais

## Status das mensagens

Cada mensagem enviada ou recebida poderá ter diferentes status e atualizado conforme seu ciclo de vida,
por exemplo: quando você enviar uma nova mensagem o status dela será status=stored, após o provedor enviar sua mensagem
para o usuário final o status será status=delivered, e assim por diante. 

<br>

Veja na tabela abaixo todos os possíveis status de uma mensagem:

| Status  | Descrição |
| ------------- | ------------- |
| stored | Recebeu o payload e armazenou individualmente no banco |
| sent | Provedor recebeu mensagem enviada. |
| delivered | Provedor entregou mensagem para usuário. |
| read | Usuário leu a mensagem. |
| failed | Falha no envio da mensagem. |
| deleted | A mensagem enviada ou recebida foi excluída. |

## Capacidade e limites de mensagem 

A capacidade e limites de mensagens consiste em:

- __Limites de volume de capacidade:__
A limitação de volume de capacidade é imposta em cada endpoint disponível da API e retornará os códigos de erro de HTTPS adequados (por exemplo, 429, 503, etc.) dependendo do estado do sistema.
    - No momento, duas formas de limitação de volume de capacidade são compatíveis:
        - __Limitação de volume da solicitação:__ é a limitação do recebimento de solicitações no endpoint de uma resposta das mensagens instantâneas. Quando o limite de número de solicitações por segundo [e atingido, ponto de extremidade começará a retornar um código de erro 429.
            - A partir da nova versão, o limite de taxa de solicitação para mensagens, o endpoint de 50 solicitações por segundo, com permissão de pico de até 150 solicitações por segundo.
            - Nas versões anteriores e a todos os outros pontos de extremidades, o limite de taxa de solicitações é de 20 segundos, com permissão de pico de até 60 solicitações por segundo. 

        <br>

        - __Limitação de volume concorrente:__ é a limitação do recebimento de solicitações quando o Coreapp está com uma carga pesada (por exemplo, a fila de trabalhos ficou muito grande). Nesse momento, o ponto de extremidade começará a retornar um erro 503.

    Quando atingir um desses cenários de limitação do volume de capacidade, você deve parar novas solicitações e diminuir o andamento das solicitações de respostas.  Se você começar a ver muitos erros de limite de volume de capacidade, é recomendado criar uma fila para limitar as solicitações.

<br>

- __Classificação de qualidade e limites de mensagem:__
    A classificação de qualidade, os limites de mensagem e o status do número de telefone da conta do WhatsApp Business estão listados na guia Números de telefone no Gerenciador do WhatsApp.

<img class = "tel" src="./images/guia-tel.png"  alt="Telefone" width="100%"/> 

## Classificação de qualidade

A classificação de qualidade mostra como as mensagens foram recebidas pelos clientes nas últimas 24 horas. São exibidos três estados diferentes: verde, amarelo e vermelho. Essas cores representam a qualidade de mensagens em alta/média/baixa, respectivamente.


## Limites de mensagem

Os limites de mensagem determinam para quantos usuários sua empresa pode enviar mensagens diariamente. Isso inclui novas conversas, assim como conversas existentes com os usuários. O limite de mensagem NÃO limita o número de mensagens que sua empresa pode enviar, apenas o número de usuários que irão recebê-las. Também NÃO se aplica a mensagens enviadas em resposta a uma mensagem iniciada pelo usuário dentro de um período de 24 horas.

- __Nível 1:__ permite que a empresa envie mensagens para 1.000 clientes exclusivos em um período contínuo de 24 horas.
- __Nível 2:__ permite que a empresa envie mensagens para 10.000 clientes exclusivos em um período contínuo de 24 horas.
- __Nível 3:__ permite que a empresa envie mensagens para 100.000 clientes exclusivos em um período contínuo de 24 horas.

Haverá o upgrade do número de telefone de uma empresa se:
- a classificação de qualidade da linha não for baixa,
- a quantidade cumulativa de usuários para quem há o envio de notificações soma duas vezes o limite de mensagens atual em um período de 7 dias. Assim que atingir esse limite. O tempo mínimo para que o upgrade ocorra é 48 horas, quando a empresa estiver enviando mensagens até seu limite atual todos os dias.

<br>

Veja os gráficos abaixo com exemplos de como uma empresa pode passar para o próximo nível:

__Exemplo 1:__ uma empresa fará o upgrade do Nível 1 para o Nível 2 quando enviar mensagens para um total de 2.000 usuários em um período de 7 dias.

<img class = "tab" src= "./images/tab1.png"  alt="Telefone" width="80%"/> 

<br>
<br>

__Exemplo 2:__ o gráfico explica o conceito de limite de mensagens nas últimas 24 horas.

<img class = "tab" src="./images/tab2.png" alt="Tabela exemplo 2" width="80%"/> 


## Status

Existem diferentes status para os números de telefone que geralmente estão associados ao status da conexão (por exemplo, Conectado, Offline etc.). De vez em quando, um número de telefone pode mostrar um dos dois status específicos relacionados aos limites de qualidade e de mensagens: 


- __Sinalizado__ - quando a classificação de qualidade atinge um estado baixo, o número de telefone passa para o status Sinalizado. Se a qualidade da mensagem melhorar para um estado alto ou médio e continuar pelos próximos 7 dias, assim o número de telefone retornará ao status Conectado. Caso a classificação de qualidade não melhorar, o número retornará ao status conectado com limite de mensagens inferior imposto ao mesmo.
- __Restrito__ – os números de telefone que atingir o limite de mensagens passam para o status restrito. Durante a fase de restrição, o número não poderá enviar mensagens de notificação até que o período de 24h para o envio seja redefinido.


Você receberá uma notificação no Gerenciador de Negócios se o status de um número de telefone da(s) sua(s) conta(s) do WhatsApp Business mudar(em) para Sinalizado ou Restrito. Caso o limite de mensagens mude, você também receberá uma notificação.


Outros status de número de telefone incluem:


- __Pendente:__ quando uma empresa configura um número de telefone que ainda não foi registrado.
- __Conectado:__ o número de telefone está online e funcionando normalmente.
- __Offline:__ no momento, o número de telefone não está acessível aos servidores do WhatsApp ou não está online.
