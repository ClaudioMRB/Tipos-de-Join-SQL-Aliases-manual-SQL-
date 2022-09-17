# Tipos-de-Join-SQL-Aliases
(inner) Join, Left (outer) Join, Right (outer) Join, Full (outer) Join &amp; SQL Aliases (AS) 

[SQL INNER JOIN Keyword (w3schools.com) ](https://www.w3schools.com/sql/sql_join_inner.asp)      [SQL LEFT JOIN Keyword (w3schools.com)](https://www.w3schools.com/sql/sql_join_left.asp)

[SQL RIGHT JOIN Keyword (w3schools.com)](https://www.w3schools.com/sql/sql_join_right.asp)       [Codinomes SQL (w3schools.com)](https://www.w3schools.com/sql/sql_alias.asp)

## ---------------SQL INNER JOIN Palavra-chave--------------------------

A palavra-chave seleciona registros que têm valores correspondentes em ambas as tabelas.`INNER JOIN`

### Sintaxe de join interno

SELECT *column_name(s)*
FROM *table1*
INNER JOIN *table2
*ON *table1.column_name* = *table2.column_name*;

![JUNTA INTERNA DO SQL](https://www.w3schools.com/sql/img_innerjoin.gif)

------

## Banco de dados de demonstração

Neste tutorial usaremos o conhecido banco de dados de amostras northwind.

Abaixo está uma seleção da tabela "Ordens":

| OrderID | CustomerID | EmployeeID | OrderDate  | ShipperID |
| :------ | :--------- | :--------- | :--------- | :-------- |
| 10308   | 2          | 7          | 1996-09-18 | 3         |
| 10309   | 37         | 3          | 1996-09-19 | 1         |
| 10310   | 77         | 8          | 1996-09-20 | 2         |

E uma seleção da tabela "Clientes":

| CustomerID | CustomerName                       | ContactName    | Address                       | City        | PostalCode | Country |
| :--------- | :--------------------------------- | :------------- | :---------------------------- | :---------- | :--------- | :------ |
| 1          | Alfreds Futterkiste                | Maria Anders   | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo   | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno | Mataderos 2312                | México D.F. | 05023      | Mexico  |

------

## SQL INNER JOIN Exemplo

A seguinte instrução SQL seleciona todos os pedidos com informações do cliente:

### Exemplo

SELECT Orders.OrderID, Customers.CustomerName
FROM Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID;

**Nota:** A palavra-chave seleciona todas as linhas de ambas as tabelas, desde que haja uma correspondência entre as colunas. Se houver registros na tabela "Pedidos" que não tenham correspondências em "Clientes", esses pedidos não serão mostrados!`INNER JOIN`

------

## JUNTE-SE A TRÊS Mesas

A seguinte instrução SQL seleciona todos os pedidos com informações de clientes e entregadores:

### Exemplo

SELECT Orders.OrderID, Customers.CustomerName, Shippers.ShipperName
FROM ((Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID)
INNER JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID);



## ------------------------SQL LEFT JOIN Keyword----------------------------

A palavra-chave retorna todos os registros da tabela esquerda (tabela1) e os registros correspondentes da tabela direita (tabela2). O resultado é 0 registros do lado direito, se não houver correspondência.`LEFT JOIN`

### Se juntar à esquerda sintaxe

SELECT *column_name(s)*
FROM *table1*
LEFT JOIN *table2
*ON *table1.column_name* = *table2.column_name*;

**Nota:** Em alguns bancos de dados, o LEFT JOIN é chamado de LEFT OUTER JOIN.

![SQL ESQUERDA JUNTE-SE](https://www.w3schools.com/sql/img_leftjoin.gif)

------

## Banco de dados de demonstração

Neste tutorial usaremos o conhecido banco de dados de amostras northwind.

Abaixo está uma seleção da tabela "Clientes":

| CustomerID | CustomerName                       | ContactName    | Address                       | City        | PostalCode | Country |
| :--------- | :--------------------------------- | :------------- | :---------------------------- | :---------- | :--------- | :------ |
| 1          | Alfreds Futterkiste                | Maria Anders   | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo   | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno | Mataderos 2312                | México D.F. | 05023      | Mexico  |

E uma seleção da tabela "Ordens":

| OrderID | CustomerID | EmployeeID | OrderDate  | ShipperID |
| :------ | :--------- | :--------- | :--------- | :-------- |
| 10308   | 2          | 7          | 1996-09-18 | 3         |
| 10309   | 37         | 3          | 1996-09-19 | 1         |
| 10310   | 77         | 8          | 1996-09-20 | 2         |

------

## SQL ESQUERDA JOIN Exemplo

A seguinte instrução SQL selecionará todos os clientes e quaisquer pedidos que eles possam ter:

### Exemplo

SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID
ORDER BY Customers.CustomerName;

[Experimente você mesmo »](https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_join_left)

**Nota:** A palavra-chave retorna todos os registros da tabela esquerda (Clientes), mesmo que não haja correspondências na tabela direita (Pedidos).`LEFT JOIN`



## -----------------------SQL RIGHT JOIN Keyword---------------------------

A palavra-chave retorna todos os registros da tabela direita (tabela2) e os registros correspondentes da tabela esquerda (tabela1). O resultado é 0 registros do lado esquerdo, se não houver correspondência.`RIGHT JOIN`

### UNINDO-SE À DIREITA Sintaxe

SELECT *column_name(s)*
FROM *table1*
RIGHT JOIN *table2
*ON *table1.column_name* = *table2.column_name*;

**Nota:** Em alguns bancos de dados é chamado .`RIGHT JOIN``RIGHT OUTER JOIN`

![SQL RIGHT JOIN](https://www.w3schools.com/sql/img_rightjoin.gif)

------

## Banco de dados de demonstração

Neste tutorial usaremos o conhecido banco de dados de amostras northwind.

Abaixo está uma seleção da tabela "Ordens":

| OrderID | CustomerID | EmployeeID | OrderDate  | ShipperID |
| :------ | :--------- | :--------- | :--------- | :-------- |
| 10308   | 2          | 7          | 1996-09-18 | 3         |
| 10309   | 37         | 3          | 1996-09-19 | 1         |
| 10310   | 77         | 8          | 1996-09-20 | 2         |

E uma seleção da tabela "Funcionários":

| EmployeeID | LastName  | FirstName | BirthDate | Photo      |
| :--------- | :-------- | :-------- | :-------- | :--------- |
| 1          | Davolio   | Nancy     | 12/8/1968 | EmpID1.pic |
| 2          | Fuller    | Andrew    | 2/19/1952 | EmpID2.pic |
| 3          | Leverling | Janet     | 8/30/1963 | EmpID3.pic |

------

## SQL RIGHT JOIN Example

A seguinte declaração SQL devolverá todos os funcionários e quaisquer ordens que eles possam ter feito:

### Exemplo

SELECT Orders.OrderID, Employees.LastName, Employees.FirstName
FROM Orders
RIGHT JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
ORDER BY Orders.OrderID;

[Experimente você mesmo »](https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_join_right&ss=-1)

**Nota:** A palavra-chave retorna todos os registros da tabela direita (Funcionários), mesmo que não haja correspondências na tabela esquerda (Ordens).`RIGHT JOIN`
