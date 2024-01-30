# Projeto de Comércio Eletrônico - Banco de Dados SQL

Este projeto consiste em um esquema de banco de dados SQL para um sistema de comércio eletrônico. O esquema inclui várias tabelas que representam entidades
típicas em um sistema de comércio eletrônico, como clientes, produtos, pedidos, fornecedores e vendedores.

## Tabelas

1.  clients: Armazena informações sobre os clientes, incluindo nome, CPF, CNPJ, data de nascimento, endereço e tipo de conta.
2.  register: Armazena informações sobre o registro dos clientes.
3.  product: Armazena informações sobre os produtos, incluindo nome, classificação (se é para crianças ou não), categoria, avaliação e tamanho.
4.  payment: Armazena informações sobre os métodos de pagamento dos clientes.
5.  orders: Armazena informações sobre os pedidos, incluindo status do pedido, descrição, valor de envio e se o pagamento foi feito à vista.
6.  productStorage: Armazena informações sobre o estoque de produtos.
7.  supplier: Armazena informações sobre os fornecedores, incluindo nome social, CNPJ e contato.
8.  productSupplier: Armazena a relação entre produtos e fornecedores.
9.  seller: Armazena informações sobre os vendedores, incluindo nome social, nome abreviado, CNPJ, CPF, localização e contato.
10.  productSeller: Armazena a relação entre produtos e vendedores.
11.  productOrder: Armazena a relação entre produtos e pedidos.
12.  storageLocation: Armazena a relação entre produtos e locais de armazenamento.
13.  delivery: Armazena informações sobre as entregas, incluindo endereço de entrega, status de entrega e código de rastreamento.

## Como Usar

Para usar este esquema de banco de dados, você precisa ter um servidor MySQL instalado. Você pode então executar o script SQL para criar as tabelas e inserir dados de exemplo.

## Consultas SQL Usadas

1.  Recuperações simples com SELECT Statement: A instrução SELECT é usada para selecionar dados de uma ou mais tabelas. Por exemplo, SELECT * FROM clients;
2.  seleciona todos os dados da tabela clients.
3.  Filtros com WHERE Statement: A cláusula WHERE é usada para filtrar registros que satisfazem uma condição específica. Por exemplo,
4.  SELECT * FROM clients WHERE accountType = 'Pessoa Física'; seleciona todos os dados da tabela clients onde o accountType é 'Pessoa Física'.
5.  Crie expressões para gerar atributos derivados: Você pode usar funções e operadores SQL para criar atributos a partir de atributos existentes.
6.  Por exemplo, `SELECT idClients, CONCAT(Fname, ' ', Lname) AS FullName FROM clients;` cria um novo atributo `FullName` que é a concatenação dos atributos `Fname` e `Lname`.
7.  Defina ordenações dos dados com ORDER BY: A cláusula ORDER BY é usada para classificar os dados em ordem ascendente ou descendente com base em uma ou mais colunas.
8.  Por exemplo, `SELECT * FROM clients ORDER BY Lname;` seleciona todos os dados da tabela clients ordenados pelo sobrenome Lname.
9.  Condições de filtros aos grupos – HAVING Statement: A cláusula HAVING é usada para filtrar os resultados de uma consulta que usa a cláusula GROUP BY.
10.  Por exemplo, `SELECT accountType, COUNT(*) FROM clients GROUP BY accountType HAVING COUNT(*) > 1;` seleciona o tipo de conta accountType e a contagem de
11.  registros para cada tipo de conta da tabela clients, mas apenas para os tipos de conta que têm mais de um registro.
12.  Crie junções entre tabelas para fornecer uma perspectiva mais complexa dos dados: A cláusula JOIN é usada para combinar linhas de duas ou mais tabelas com base
13.  em uma coluna relacionada entre elas. Por exemplo, `SELECT clients.Fname, clients.Lname, orders.orderDescription FROM clients JOIN orders ON clients.idClients = orders.idOrderclients;`
14.  recupera o nome e sobrenome do cliente e a descrição do pedido para todos os pedidos, juntando as tabelas `clients` e `orders` no `idClients` e `idOrderclients`, respectivamente.

## Consultas SQL Adicionais

Aqui estão algumas consultas SQL adicionais que foram usadas:

1.  Drop Database: `DROP DATABASE ecommerce;` Este comando exclui o banco de dados chamado 'ecommerce'.
2.  Create Database: `CREATE DATABASE ecommerce;` Este comando cria um novo banco de dados chamado 'ecommerce'.
3.  Use Database: `USE ecommerce;` Este comando seleciona o banco de dados 'ecommerce' para uso.
4.  Update Data: `UPDATE clients SET Lname = 'Wilson' WHERE idClients = 4;` Este comando atualiza a coluna `Lname` para 'Wilson' na tabela `clients` onde `idClients` é 4.
5.  Insert Data: `INSERT INTO clients(Fname, Minit, Lname, CPF, CNPJ, birthDate, Addres, accountType) VALUES ...; Este comando insere um novo registro na tabela clients. Você precisará substituir `...`
6.  pelos valores que deseja inserir.
7.  Show Databases: `SHOW DATABASES;` Este comando lista todos os bancos de dados no servidor MySQL.
7 – Show Tables: Este comando irá listar todas as tabelas no banco de dados ecommerce.
