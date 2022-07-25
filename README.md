
# sistema-pizzaria-backend

Backend de um sistema de pizzaria

Feito com Node.js e Typescript

### Rotas User:
#### /user  - POST - Criação de usuário
- Body da requisição:
name: string
email: string
password: string

#### /session - POST - Autenticação e login de usuário com geração
- Body da requisição:
email: string
password: string

#### /me - GET - Detalhes do usuário
- Não espera nenhum parâmetro, o id é resgatado da request, assim que o usuário é autenticado.

### Rotas Category
#### /category - POST - Criação de uma categoria
- Body da requisição:
name: string

####  /category - GET - Listagem de categorias
- Não espera nenhum parâmetro.

### Rotas Product
#### /product - POST - Cadastrar um produto
- Body da requisição:
name: string
price: string
description: string
banner: arquivo de imagem
category_id: string

#### /category/product - GET - Listagem de produtos por categoria
- Query params esperados:
category_id

### Rotas Order
#### /order - POST - Cria um pedido
- Body da requisição:
table: number
name: string

#### /order - DELETE - Remove um pedido
- Query params esperados:
order_id

#### /order/add - POST - Adiciona um produto no pedido
- Body da requisição:
order_id: string
product_id: string
amount: number

#### /order/remove - DELETE - Remove um produto do pedido
- Query params esperados:
item_id

#### /order/send - PUT - Envia o pedido
- Body da requisição:
order_id: string

#### /orders - GET - Listagem de pedidos
- Não espera nenhum parâmetro.
- 
#### /order/details - GET - Detalhes de um pedido
- Query params esperados:
order_id

#### /order/finish - PUT - Finaliza um pedido
- Body da requisição:
order_id: string
