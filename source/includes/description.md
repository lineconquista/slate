# API Instant Message

A plataforma consiste em:

- Uma API de disparo de mensagens instantâneas;

- Um portal administrativo de unidades, números, aplicações e usuários;

- Uma interface de chat para interação;

- Um sistema de URA Chat Boti;


## Como eu posso utilizar a API?

- A plataforma Instant Message foi desenvolvida a partir do projeto do WhatsApp Corporativo, tendo como área solicitante: Comunicação da UN O Boticário, onde entregamos uma solução integrada a API do WhatsApp.<br>
Para as demais áreas e unidades interessadas em utilizar a plataforma, a cada nova necessidade será necessária a abertura de um novo projeto onde algumas premissas devem ser levadas em conta:<br><br>

    - Levantamento dos requisitos contendo a média de volumetria de disparos (Ativos/Reativos) e quantidade de números necessários;
    
    - Desenvolvimentos nas aplicações que serão integradas a plataforma Instant Message e se necessário melhorias na própria plataforma;

    - Configurações das contas/números no facebook e também cadastros na plataforma IM, tendo como área responsável – Comunicação O Boticário;

    - Avaliação junto as área de arquitetura/infra para levantamento do custos com a AWS;

    - Análise quanto ao suporte da operação junto ao time interno de aplicações e parceiros.


## Lista de provedores homologados para disparo

| Provedores |
| ------------- |
| Whatsapp |

### Headers Padrão

| Parâmetro  | Significado | Valores |
| ------------- | ------------- | --- |
| Accept | Indica para a API o formato que é esperado no retorno. | application/json |
| Content-Type | Tipo de arquivo do recurso.  | application/json |
| Authorization | Token JWT utilizado para autenticação. | Um token JWT |

Para obter um token de autorização você precisa gerar um token de aplicativo no portal administrativo da API Instant Message.




