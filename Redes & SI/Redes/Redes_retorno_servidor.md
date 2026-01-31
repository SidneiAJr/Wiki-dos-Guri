# 🚨 Lista de Erros de Status HTTP - Explicação Técnica

---

## ✅ **200 OK**
- **Descrição**: O código 200 indica que a requisição foi processada com sucesso pelo servidor.
- **Quando é usado**: O servidor respondeu corretamente à solicitação.
- **Exemplo**: Requisição GET para uma página que existe e foi carregada com sucesso.

---

## 🚫 **400 Bad Request**
- **Descrição**: A requisição enviada pelo cliente contém erros de sintaxe, o que impede o servidor de entendê-la.
- **Quando é usado**: O cliente envia dados corrompidos ou malformados para o servidor.
- **Exemplo**: Uma URL malformada ou um parâmetro obrigatório ausente.

---

## ❌ **401 Unauthorized**
- **Descrição**: O código 401 indica que a requisição não foi aplicada porque as credenciais de autenticação não foram fornecidas ou são inválidas.
- **Quando é usado**: O servidor requer autenticação para acessar o recurso solicitado.
- **Exemplo**: Tentativa de acessar uma área protegida sem fornecer um token de autenticação válido.

---

## 🔒 **403 Forbidden**
- **Descrição**: O servidor entendeu a requisição, mas se recusa a autorizá-la. O acesso ao recurso é negado.
- **Quando é usado**: A autenticação pode ser fornecida, mas o usuário não tem permissão para acessar o recurso.
- **Exemplo**: Tentar acessar um arquivo com permissões restritas.

---

## ❓ **404 Not Found**
- **Descrição**: O servidor não encontrou o recurso solicitado. Pode ser um caminho de URL inválido ou um arquivo ausente.
- **Quando é usado**: O servidor não tem conhecimento de um recurso solicitado.
- **Exemplo**: Acessar uma página ou arquivo que não existe no servidor.

---

## ⏳ **405 Method Not Allowed**
- **Descrição**: O método HTTP utilizado para fazer a requisição não é permitido para o recurso solicitado.
- **Quando é usado**: Um método (por exemplo, POST, GET, PUT) foi utilizado de forma inadequada para um recurso específico.
- **Exemplo**: Tentar usar um método POST em um recurso que só permite GET.

---

## ⛔ **406 Not Acceptable**
- **Descrição**: O recurso solicitado está em um formato que o cliente não pode aceitar, de acordo com o cabeçalho "Accept" da requisição.
- **Quando é usado**: O servidor não pode gerar uma resposta compatível com o tipo de conteúdo solicitado pelo cliente.
- **Exemplo**: Tentar acessar um recurso em formato XML quando o cliente só aceita JSON.

---

## 🔑 **407 Proxy Authentication Required**
- **Descrição**: O servidor exige autenticação do cliente por meio de um proxy.
- **Quando é usado**: O cliente precisa fornecer credenciais para acessar o recurso por meio de um servidor proxy.
- **Exemplo**: Acessar um recurso na web através de um proxy que exige autenticação.

---

## 💣 **500 Internal Server Error**
- **Descrição**: Este erro indica que ocorreu uma falha genérica no servidor ao tentar processar a requisição.
- **Quando é usado**: O servidor encontrou um erro inesperado ao processar a requisição.
- **Exemplo**: Um erro de programação ou falha em um serviço do servidor.

---

## 🚧 **502 Bad Gateway**
- **Descrição**: O servidor agiu como um gateway ou proxy e recebeu uma resposta inválida de um servidor upstream.
- **Quando é usado**: Quando há uma falha na comunicação entre servidores.
- **Exemplo**: Problema ao tentar buscar dados de um servidor externo e o servidor de origem não retornar a resposta adequada.

---

## 🔄 **503 Service Unavailable**
- **Descrição**: O servidor não está disponível no momento devido a sobrecarga ou manutenção.
- **Quando é usado**: O servidor está temporariamente fora do ar, seja para manutenção ou por sobrecarga.
- **Exemplo**: Tentando acessar um serviço durante sua janela de manutenção.

---

## 🏗️ **504 Gateway Timeout**
- **Descrição**: O servidor agiu como um gateway ou proxy e não obteve uma resposta a tempo de um servidor upstream.
- **Quando é usado**: Quando o servidor não consegue se comunicar com outro servidor no tempo esperado.
- **Exemplo**: Tempo de espera excedido ao tentar acessar dados de um servidor remoto.

---

## 🚫 **505 HTTP Version Not Supported**
- **Descrição**: O servidor não suporta a versão do protocolo HTTP usada na requisição.
- **Quando é usado**: O cliente usa uma versão do protocolo HTTP que não é suportada pelo servidor.
- **Exemplo**: Usar uma versão de HTTP desatualizada ou incompatível.

---

## ⛔ **511 Network Authentication Required**
- **Descrição**: O cliente precisa se autenticar para acessar a rede.
- **Quando é usado**: Requer que o cliente faça login para acessar uma rede.
- **Exemplo**: Conectar-se a uma rede pública que exige autenticação para navegação.

---

# 📋 **Lista Completa de Códigos de Status HTTP**
- **1xx** - Informational responses
  - 100 Continue
  - 101 Switching Protocols
  - 102 Processing
- **2xx** - Success
  - 200 OK
  - 201 Created
  - 202 Accepted
  - 203 Non-Authoritative Information
  - 204 No Content
  - 205 Reset Content
  - 206 Partial Content
  - 207 Multi-Status
  - 208 Already Reported
  - 226 IM Used
- **3xx** - Redirection
  - 300 Multiple Choices
  - 301 Moved Permanently
  - 302 Found
  - 303 See Other
  - 304 Not Modified
  - 305 Use Proxy
  - 306 Switch Proxy
  - 307 Temporary Redirect
  - 308 Permanent Redirect
- **4xx** - Client Error
  - 400 Bad Request
  - 401 Unauthorized
  - 402 Payment Required
  - 403 Forbidden
  - 404 Not Found
  - 405 Method Not Allowed
  - 406 Not Acceptable
  - 407 Proxy Authentication Required
  - 408 Request Timeout
  - 409 Conflict
  - 410 Gone
  - 411 Length Required
  - 412 Precondition Failed
  - 413 Payload Too Large
  - 414 URI Too Long
  - 415 Unsupported Media Type
  - 416 Range Not Satisfiable
  - 417 Expectation Failed
  - 418 I'm a teapot (April Fools' joke)
  - 421 Misdirected Request
  - 422 Unprocessable Entity
  - 423 Locked
  - 424 Failed Dependency
  - 425 Too Early
  - 426 Upgrade Required
  - 427 Unassigned
  - 428 Precondition Required
  - 429 Too Many Requests
  - 431 Request Header Fields Too Large
  - 451 Unavailable For Legal Reasons
- **5xx** - Server Error
  - 500 Internal Server Error
  - 501 Not Implemented
  - 502 Bad Gateway
  - 503 Service Unavailable
  - 504 Gateway Timeout
  - 505 HTTP Version Not Supported
  - 506 Variant Also Negotiates
  - 507 Insufficient Storage
  - 508 Loop Detected
  - 510 Not Extended
  - 511 Network Authentication Required

---

Essa é a explicação técnica, e a lista completa com os principais **códigos de status HTTP**. Se precisar de mais algum código ou mais detalhes sobre algum deles, só avisar!
