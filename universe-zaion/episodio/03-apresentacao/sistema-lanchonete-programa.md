# Projeto: Sistema para Lanchonete com Arquivo Local


## Versão usando **arquivo local JSON**, sem banco de dados.

## O que é JSON?

**JSON** (*JavaScript Object Notation*) é um formato de arquivo utilizado para **armazenar e trocar informações** de maneira organizada e legível, tanto por pessoas quanto por programas.

Embora tenha sido criado com base na linguagem JavaScript, o JSON é amplamente utilizado em diversas linguagens de programação, como **Python, Java, C#, PHP, entre outras**.

Uma das principais vantagens do JSON é permitir que os dados sejam gravados em um arquivo e recuperados posteriormente, sem a necessidade de utilizar um banco de dados.

No Python, o módulo `json` é utilizado para converter estruturas como listas e dicionários em arquivos JSON e vice-versa.

---

## Estrutura do JSON

Um arquivo JSON é composto por **pares chave–valor**, organizados entre chaves `{}`.

Exemplo:

```json
{
    "nome": "João",
    "idade": 17,
    "curso": "Desenvolvimento de Sistemas"
}
```

Neste exemplo:

* `"nome"` é a chave, e `"João"` é o valor;
* `"idade"` é a chave, e `17` é o valor;
* `"curso"` é a chave, e `"Desenvolvimento de Sistemas"` é o valor.

---

## Exemplo com vários produtos

```json
{
    "produtos": [
        {
            "codigo": "001",
            "nome": "X-Burguer",
            "preco": 18.50,
            "estoque": 12
        },
        {
            "codigo": "002",
            "nome": "Refrigerante",
            "preco": 6.00,
            "estoque": 25
        }
    ]
}
```

Observe que:

* `{}` representa um **objeto** (conjunto de informações);
* `[]` representa uma **lista** de objetos;
* cada produto possui seus próprios atributos (código, nome, preço e estoque).

---

## Exemplo em Python

Gravando dados em um arquivo JSON:

```python
import json

produto = {
    "codigo": "001",
    "nome": "X-Burguer",
    "preco": 18.50,
    "estoque": 12
}

with open("produto.json", "w", encoding="utf-8") as arquivo:
    json.dump(produto, arquivo, indent=4, ensure_ascii=False)
```

Lendo os dados do arquivo:

```python
import json

with open("produto.json", "r", encoding="utf-8") as arquivo:
    produto = json.load(arquivo)

print(produto["nome"])
print(produto["preco"])
```

Saída:

```text
X-Burguer
18.5
```

---

## Resumo

* JSON é um formato para **armazenar e trocar dados**.
* Os dados são organizados em **chaves e valores**.
* É um formato leve, simples e muito utilizado em aplicações web e sistemas.
* No Python, utiliza-se o módulo `json` para gravar (`json.dump`) e ler (`json.load`) arquivos JSON.
* Para projetos de pequeno porte, o JSON é uma excelente alternativa ao banco de dados, permitindo persistir informações de forma simples e organizada.

---

## Abaixo o programa completo da lanchonete em Python

### Note que os nomes das funções e variáveils estão em inglês
### Este modelo foi adotado para seguir o padrão de desenvolmento internacional

---

## lanchonete.py

```python
import json
import os

DATA_FILE = "lanchonete_dados.json"

products = []
orders = []


def load_data():
    global products, orders

    if not os.path.exists(DATA_FILE):
        products = []
        orders = []
        return

    with open(DATA_FILE, "r", encoding="utf-8") as file:
        data = json.load(file)
        products = data.get("products", [])
        orders = data.get("orders", [])


def save_data():
    data = {
        "products": products,
        "orders": orders
    }

    with open(DATA_FILE, "w", encoding="utf-8") as file:
        json.dump(data, file, indent=4, ensure_ascii=False)


def register_product():
    code = input("Código do produto: ")

    if find_product_by_code(code) is not None:
        print("Já existe um produto com este código.")
        return

    name = input("Nome do produto: ")
    price = float(input("Preço do produto: "))
    stock = int(input("Quantidade em estoque: "))

    product = {
        "code": code,
        "name": name,
        "price": price,
        "stock": stock
    }

    products.append(product)
    save_data()

    print("Produto cadastrado com sucesso!")


def list_products():
    if len(products) == 0:
        print("Nenhum produto cadastrado.")
        return

    print("\n--- Produtos cadastrados ---")
    for product in products:
        print(f"Código: {product['code']}")
        print(f"Nome: {product['name']}")
        print(f"Preço: R$ {product['price']:.2f}")
        print(f"Estoque: {product['stock']}")
        print("-" * 30)


def find_product_by_code(code):
    for product in products:
        if product["code"] == code:
            return product
    return None


def make_order():
    if len(products) == 0:
        print("Nenhum produto cadastrado.")
        return

    customer_name = input("Nome do cliente: ")

    list_products()

    code = input("Digite o código do produto: ")
    product = find_product_by_code(code)

    if product is None:
        print("Produto não encontrado.")
        return

    quantity = int(input("Quantidade desejada: "))

    if quantity <= 0:
        print("Quantidade inválida.")
        return

    if quantity > product["stock"]:
        print("Estoque insuficiente.")
        return

    total = quantity * product["price"]
    product["stock"] -= quantity

    order = {
        "customer_name": customer_name,
        "product_code": product["code"],
        "product_name": product["name"],
        "quantity": quantity,
        "total": total
    }

    orders.append(order)
    save_data()

    print("Pedido realizado com sucesso!")
    print(f"Total: R$ {total:.2f}")


def list_orders():
    if len(orders) == 0:
        print("Nenhum pedido realizado.")
        return

    print("\n--- Pedidos realizados ---")
    for order in orders:
        print(f"Cliente: {order['customer_name']}")
        print(f"Produto: {order['product_name']}")
        print(f"Quantidade: {order['quantity']}")
        print(f"Total: R$ {order['total']:.2f}")
        print("-" * 30)


def show_menu():
    print("\n=== Sistema para Lanchonete ===")
    print("1 - Cadastrar produto")
    print("2 - Listar produtos")
    print("3 - Fazer pedido")
    print("4 - Ver pedidos realizados")
    print("5 - Sair")


def main():
    load_data()

    while True:
        show_menu()
        option = input("Escolha uma opção: ")

        if option == "1":
            register_product()
        elif option == "2":
            list_products()
        elif option == "3":
            make_order()
        elif option == "4":
            list_orders()
        elif option == "5":
            save_data()
            print("Sistema encerrado.")
            break
        else:
            print("Opção inválida.")


main()
```

O programa criará automaticamente o arquivo:

```text
lanchonete_dados.json
```

Exemplo do conteúdo salvo:

```json
{
    "products": [
        {
            "code": "1",
            "name": "X-Salada",
            "price": 18.5,
            "stock": 10
        }
    ],
    "orders": [
        {
            "customer_name": "Ana",
            "product_code": "1",
            "product_name": "X-Salada",
            "quantity": 2,
            "total": 37.0
        }
    ]
}
```
