# Projeto: Sistema para Lanchonete com Arquivo Local

## Situação-problema

Uma pequena lanchonete precisa de um sistema simples para registrar seus produtos, controlar o estoque e registrar pedidos dos clientes.

O sistema será executado no terminal e deverá salvar os dados em um **arquivo local**, sem uso de banco de dados.

## Objetivo

Desenvolver um programa em **Python** que simule o funcionamento básico de uma lanchonete, permitindo que os dados continuem salvos mesmo depois que o programa for fechado.

## Arquivo de dados

O sistema deverá utilizar um arquivo local chamado:

```text
lanchonete_dados.json
```

Esse arquivo deverá armazenar:

```text
Produtos cadastrados
Pedidos realizados
```

## Funcionalidades obrigatórias

O sistema deve apresentar o seguinte menu:

```text
1 - Cadastrar produto
2 - Listar produtos
3 - Fazer pedido
4 - Ver pedidos realizados
5 - Sair
```

## Dados dos produtos

Cada produto deve possuir:

```text
Código
Nome
Preço
Quantidade em estoque
```

## Dados dos pedidos

Cada pedido deve registrar:

```text
Nome do cliente
Código do produto
Nome do produto
Quantidade comprada
Valor total
```

## Regras do sistema

O programa deve:

```text
Carregar os dados do arquivo ao iniciar
Criar o arquivo caso ele ainda não exista
Salvar os dados sempre que um produto for cadastrado
Salvar os dados sempre que um pedido for realizado
Não permitir produtos com códigos repetidos
Não permitir venda de produto inexistente
Não permitir venda com estoque insuficiente
Atualizar o estoque após cada pedido
Permitir consultar produtos e pedidos já salvos
Usar funções para organizar o código
```

## Conceitos de Python utilizados

```text
Variáveis
Listas
Dicionários
Funções
Estruturas condicionais
Laços de repetição
Arquivos
JSON
Importação de módulos
Validação de dados
```

## Melhorias opcionais

```text
Alterar preço de produto
Remover produto
Pesquisar produto por nome
Relatório de vendas
Produto mais vendido
Total vendido no dia
Exportar relatório para CSV
Criar backup do arquivo JSON
```
## Vesão inicial


| [`Sistema Lanchonete - v1.0`](sistema-lanchonete-programa.md) |
| -------------------------------------------------------- |



