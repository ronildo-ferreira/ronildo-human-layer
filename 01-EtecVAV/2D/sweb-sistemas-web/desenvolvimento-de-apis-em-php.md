## Leia atentamente o texto.

# Aula — Introdução ao desenvolvimento de APIs em PHP

## 1. O que é uma API?

API significa **Application Programming Interface** — Interface de Programação de Aplicações.

De maneira simples, uma API permite que **dois sistemas troquem informações seguindo regras previamente definidas**.

Imagine um aplicativo de celular que precisa consultar os produtos de uma loja.

O aplicativo poderia fazer uma solicitação:

```text
GET /api/products
```

O servidor poderia responder:

```json
[
    {
        "id": 1,
        "name": "Keyboard",
        "price": 150.00
    },
    {
        "id": 2,
        "name": "Mouse",
        "price": 80.00
    }
]
```

Nesse exemplo:

```text
Aplicativo
    │
    │ requisição
    ▼
   API
    │
    │ consulta
    ▼
Servidor / Banco de Dados
```

A API funciona como uma **interface de comunicação** entre os sistemas.

---

# 2. Uma página Web e uma API não são a mesma coisa

Quando acessamos uma página PHP tradicional:

```text
http://localhost/store/products.php
```

o servidor normalmente responde com **HTML**:

```html
<h1>Products</h1>

<p>Keyboard - R$ 150,00</p>
<p>Mouse - R$ 80,00</p>
```

O navegador interpreta esse HTML e apresenta a página ao usuário.

Uma API pode receber:

```text
GET /api/products
```

e responder:

```json
[
    {
        "id": 1,
        "name": "Keyboard",
        "price": 150
    },
    {
        "id": 2,
        "name": "Mouse",
        "price": 80
    }
]
```

A diferença principal aqui é o objetivo:

| Página Web                           | API                                     |
| ------------------------------------ | --------------------------------------- |
| Responde normalmente com HTML        | Pode responder com JSON                 |
| Pensada para apresentação ao usuário | Pensada para comunicação entre sistemas |
| Navegador apresenta a interface      | Outro software interpreta os dados      |
| Pode usar Bootstrap                  | Não precisa de Bootstrap                |

Portanto, **Bootstrap não é necessário para construir a API**.

---

# 3. O que é JSON?

JSON significa **JavaScript Object Notation**.

É um formato muito utilizado para troca de dados entre sistemas.

Exemplo:

```json
{
    "id": 1,
    "name": "Keyboard",
    "price": 150.00,
    "available": true
}
```

Temos pares:

```text
chave → valor
```

Por exemplo:

```text
"name"  → "Keyboard"
"price" → 150.00
```

JSON pode representar objetos, listas, números, textos, valores booleanos etc.

---

# 4. PHP transformando dados em JSON

O PHP possui a função:

```php
json_encode()
```

Vamos começar com algo simples.

```php
<?php

$product = [
    "id" => 1,
    "name" => "Keyboard",
    "price" => 150.00
];

echo json_encode($product);
```

O resultado será semelhante a:

```json
{"id":1,"name":"Keyboard","price":150}
```

Nosso primeiro passo para construir uma API já está funcionando.

---

# 5. Informando que estamos enviando JSON

É importante informar ao cliente qual tipo de conteúdo está sendo retornado.

Podemos utilizar:

```php
header("Content-Type: application/json");
```

Código:

```php
<?php

header("Content-Type: application/json");

$product = [
    "id" => 1,
    "name" => "Keyboard",
    "price" => 150.00
];

echo json_encode($product);
```

O servidor está dizendo:

> A resposta que estou enviando contém JSON.

---

# 6. Retornando vários produtos

Podemos criar um vetor:

```php
<?php

header("Content-Type: application/json");

$products = [
    [
        "id" => 1,
        "name" => "Keyboard",
        "price" => 150.00
    ],
    [
        "id" => 2,
        "name" => "Mouse",
        "price" => 80.00
    ],
    [
        "id" => 3,
        "name" => "Monitor",
        "price" => 900.00
    ]
];

echo json_encode($products);
```

Nossa API responderá com uma coleção:

```json
[
    {
        "id": 1,
        "name": "Keyboard",
        "price": 150
    },
    {
        "id": 2,
        "name": "Mouse",
        "price": 80
    },
    {
        "id": 3,
        "name": "Monitor",
        "price": 900
    }
]
```

---

# 7. Requisição e resposta

Dois termos serão utilizados constantemente:

### Request

É a **requisição** enviada pelo cliente.

```text
Cliente
   │
   │ REQUEST
   ▼
Servidor
```

### Response

É a **resposta** enviada pelo servidor.

```text
Cliente
   ▲
   │ RESPONSE
   │
Servidor
```

Juntando:

```text
CLIENTE
   │
   │ Request
   ▼
  API
   │
   │ processamento
   ▼
SERVIDOR

SERVIDOR
   │
   │ Response
   ▼
CLIENTE
```

---

# 8. Métodos HTTP

Uma API REST utiliza métodos HTTP para indicar diferentes operações.

Os quatro mais importantes neste momento são:

| Método   | Operação comum |
| -------- | -------------- |
| `GET`    | Consultar      |
| `POST`   | Criar          |
| `PUT`    | Atualizar      |
| `DELETE` | Excluir        |

Podemos relacioná-los ao CRUD:

| CRUD   | HTTP   |
| ------ | ------ |
| Create | POST   |
| Read   | GET    |
| Update | PUT    |
| Delete | DELETE |

Isso será fundamental durante o desenvolvimento das nossas APIs.

---

# 9. GET — consultando dados

Imagine:

```text
GET /api/products
```

Significa:

> Quero consultar os produtos.

Poderíamos ter:

```php
<?php

header("Content-Type: application/json");

$products = [
    ["id" => 1, "name" => "Keyboard"],
    ["id" => 2, "name" => "Mouse"]
];

echo json_encode($products);
```

Resposta:

```json
[
    {
        "id": 1,
        "name": "Keyboard"
    },
    {
        "id": 2,
        "name": "Mouse"
    }
]
```

---

# 10. Consultando um produto específico

Também podemos solicitar somente um recurso:

```text
GET /api/products/2
```

O `2` representa o identificador do produto.

Conceitualmente:

```text
/api/products/2
              ↑
              ID
```

A API deverá localizar o produto 2 e responder:

```json
{
    "id": 2,
    "name": "Mouse",
    "price": 80
}
```

Mais adiante, o **roteamento** será responsável por interpretar URLs como essa.

---

# 11. POST — enviando dados

Agora queremos cadastrar:

```text
POST /api/products
```

O cliente poderá enviar:

```json
{
    "name": "Webcam",
    "price": 250
}
```

A API:

1. recebe os dados;
2. valida;
3. cadastra;
4. retorna uma resposta.

Por exemplo:

```json
{
    "id": 4,
    "name": "Webcam",
    "price": 250
}
```

---

# 12. PHP recebendo JSON

Aqui existe uma diferença importante em relação aos formulários HTML tradicionais.

Já conheçem:

```php
$_POST["name"]
```

Porém, quando recebemos JSON diretamente no corpo da requisição, podemos fazer:

```php
$json = file_get_contents("php://input");

$data = json_decode($json, true);
```

Agora:

```php
$data["name"]
```

poderá acessar o nome recebido.

Exemplo:

```php
<?php

header("Content-Type: application/json");

$json = file_get_contents("php://input");

$data = json_decode($json, true);

$response = [
    "message" => "Product received",
    "product" => $data
];

echo json_encode($response);
```

Se enviarmos:

```json
{
    "name": "Webcam",
    "price": 250
}
```

receberemos uma resposta semelhante a:

```json
{
    "message": "Product received",
    "product": {
        "name": "Webcam",
        "price": 250
    }
}
```

Ainda não estamos gravando no banco. Estamos apenas aprendendo a **receber e responder dados**.

---

# 13. PUT — atualizando

Imagine que o produto `4` já existe:

```text
PUT /api/products/4
```

Enviamos:

```json
{
    "name": "Webcam HD",
    "price": 280
}
```

A interpretação seria:

> Atualize o produto de ID 4 utilizando esses dados.

A API poderá responder:

```json
{
    "message": "Product updated"
}
```

---

# 14. DELETE — excluindo

Para excluir:

```text
DELETE /api/products/4
```

Podemos interpretar:

> Exclua o produto de ID 4.

Resposta possível:

```json
{
    "message": "Product deleted"
}
```

Observe que não precisamos enviar uma página HTML confirmando a exclusão.

A API responde com dados que o **cliente** poderá interpretar.

---

# 15. Códigos HTTP

Além do JSON, o servidor informa se a operação funcionou através de um **HTTP Status Code**.

Alguns códigos importantes:

| Código | Significado                                 |
| -----: | ------------------------------------------- |
|  `200` | OK                                          |
|  `201` | Criado                                      |
|  `204` | Sucesso sem conteúdo na resposta            |
|  `400` | Requisição inválida                         |
|  `401` | Não autenticado                             |
|  `403` | Acesso proibido                             |
|  `404` | Recurso não encontrado                      |
|  `422` | Dados não puderam ser processados/validados |
|  `500` | Erro interno do servidor                    |

Por exemplo:

```php
http_response_code(201);
```

podemos informar que algo foi criado.

```php
<?php

header("Content-Type: application/json");

http_response_code(201);

echo json_encode([
    "message" => "Product created"
]);
```

---

# 16. Um exemplo de erro

Imagine uma consulta:

```text
GET /api/products/99
```

Mas o produto `99` não existe.

Não seria adequado simplesmente responder:

```json
{
    "product": null
}
```

Podemos informar:

```php
http_response_code(404);
```

e responder:

```json
{
    "error": "Product not found"
}
```

Exemplo:

```php
<?php

header("Content-Type: application/json");

http_response_code(404);

echo json_encode([
    "error" => "Product not found"
]);
```

Assim temos duas informações:

```text
HTTP Status
404

+

JSON
{
   "error": "Product not found"
}
```

---

# 17. Onde os dados podem chegar?

Esse é outro conteúdo importante para avançarmos depois.

Uma requisição pode transportar informações em lugares diferentes.

### Route

```text
/api/products/15
```

O `15` está na rota.

---

### Query String

```text
/api/products?category=computer
```

Temos:

```text
category=computer
```

Podemos usar isso para filtros, pesquisa, paginação etc.

---

### Body

```json
{
    "name": "Keyboard",
    "price": 150
}
```

Muito utilizado em `POST` e `PUT`.

---

### Header

```text
Content-Type: application/json
```

ou, futuramente:

```text
Authorization: Bearer ...
```

Headers carregam informações sobre a requisição ou resposta.

---

# 18. Testando nossa API

Não precisamos criar outra aplicação para testar imediatamente.

Podemos utilizar um **cliente REST**.

Algumas possibilidades são [Postman](https://www.postman.com/?utm_source=chatgpt.com) e [Insomnia](https://insomnia.rest/?utm_source=chatgpt.com).

Com essas ferramentas podemos escolher:

```text
GET
POST
PUT
DELETE
```

informar:

```text
http://localhost/api/products
```

e enviar JSON:

```json
{
    "name": "Mouse",
    "price": 80
}
```

Isso permite observar:

```text
REQUEST
↓
API PHP
↓
RESPONSE
↓
Status + JSON
```

---

# 19. E o banco de dados?

Até agora utilizamos arrays:

```php
$products = [
    ["id" => 1, "name" => "Keyboard"],
    ["id" => 2, "name" => "Mouse"]
];
```

Isso é proposital.

Primeiro precisamos entender **como uma API funciona**.

Depois podemos substituir:

```text
Array PHP
```

por:

```text
MariaDB
```

Nossa arquitetura evoluirá para:

```text
Cliente REST
      │
      │ HTTP Request
      ▼
    API PHP
      │
      ▼
     PDO
      │
      ▼
   MariaDB
      │
      ▼
     PDO
      │
      ▼
    API PHP
      │
      │ HTTP Response
      ▼
     JSON
```

Assim conseguimos reaproveitar o conhecimento que já possuem sobre **PHP + PDO + MariaDB/XAMPP**.

---

# 20. API com PHP puro × CodeIgniter

Em PHP puro, nós mesmos precisaremos organizar:

```text
rotas
controllers
validação
responses
banco
tratamento de erros
```

No CodeIgniter 4, podemos ter algo mais estruturado:

```text
Request
   ↓
Route
   ↓
Controller
   ↓
Model
   ↓
Database
   ↓
Controller
   ↓
Response JSON
```

Por exemplo, futuramente uma rota poderá ser:

```php
$routes->get('api/products', 'ProductController::index');
```

E o Controller:

```php
public function index()
{
    $products = [
        ["id" => 1, "name" => "Keyboard"],
        ["id" => 2, "name" => "Mouse"]
    ];

    return $this->response->setJSON($products);
}
```

O conceito continua sendo o mesmo. O framework apenas oferece ferramentas para **organizar e facilitar o desenvolvimento**.

---

# 21. Um pequeno exercício prático

Podemos terminar a aula criando uma API extremamente simples, ainda sem banco.

Crie:

```text
htdocs/
└── first-api/
    └── products.php
```

Código:

```php
<?php

header("Content-Type: application/json");

$products = [
    [
        "id" => 1,
        "name" => "Keyboard",
        "price" => 150.00
    ],
    [
        "id" => 2,
        "name" => "Mouse",
        "price" => 80.00
    ],
    [
        "id" => 3,
        "name" => "Monitor",
        "price" => 900.00
    ]
];

http_response_code(200);

echo json_encode($products);
```

Acesse:

```text
http://localhost/first-api/products.php
```

O navegador deverá receber o JSON.

O importante neste primeiro exercício não é fazer um CRUD completo, mas perceber:

```text
Cliente
   │
   │ GET
   ▼
products.php
   │
   │ processamento
   ▼
JSON + HTTP 200
   │
   ▼
Cliente
```

---

# 22. O que precisamos saber ao final da aula?

Como primeira aula foque nos conceitos:

| Conceito        | Ideia principal                           |
| --------------- | ----------------------------------------- |
| API             | Interface de comunicação entre aplicações |
| Request         | Requisição enviada ao servidor            |
| Response        | Resposta do servidor                      |
| JSON            | Formato utilizado para representar dados  |
| URI             | Identificação/endereço de um recurso      |
| GET             | Consultar                                 |
| POST            | Criar                                     |
| PUT             | Atualizar                                 |
| DELETE          | Excluir                                   |
| HTTP Status     | Informa o resultado da requisição         |
| `json_encode()` | Converte dados PHP para JSON              |
| `json_decode()` | Converte JSON para dados PHP              |

