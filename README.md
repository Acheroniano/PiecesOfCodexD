# PiecesOfCodexD
Pieces of Code Launched at the limbo

# For the Course: 
https://www.linkedin.com/learning/sql-practice-basic-queries/talking-to-your-database-in-sql

###### SQL Statements developed (LinkedIn Course)

```
-- SQL request(s)​​​​​​‌‌​‌​​​​​​​‌‌​‌​‌‌‌​​‌​‌​ below
SELECT FirstName, LastName, Email
FROM Customers order by LastName Asc, FirstName Asc;

-- SQL request(s)​​​​​​‌‌​‌​​​​​​​‌‌​‌​‌​‌​‌‌‌​‌ below
SELECT Reservations.Date, Reservations.PartySize, Customers.FirstName, Customers.LastName, Customers.Email
FROM Reservations
INNER JOIN Customers
ON Reservations.CustomerID = Customers.CustomerID
ORDER BY Reservations.Date DESC
LIMIT 2;

-- SQL request(s)​​​​​​‌‌​‌​​​​​​​‌‌​‌​‌​‌​‌‌‌​‌ below
SELECT TOP 2 Reservations.Date, Reservations.PartySize, Customers.FirstName, Customers.LastName, Customers.Email
FROM Reservations
INNER JOIN Customers
ON Reservations.CustomerID = Customers.CustomerID
ORDER BY Reservations.Date DESC;

-- SQL request(s)​​​​​​‌‌​‌​​​​​​​‌‌​‌‌​​​​‌‌‌​‌ below
SELECT DishID, Name, Price 
FROM Dishes Where Price between 7.99 and 9.01 order by name ASC;

-- SQL request(s)​​​​​​‌‌​‌​​​​​​​‌‌​‌‌​​​​‌‌‌​‌ below
SELECT DishID, Name, Price 
FROM Dishes Where Price between 8 and 9 order by name ASC;

-- SQL request(s)​​​​​​‌‌​‌​​​​​​​‌‌​‌‌​‌​​‌‌​​‌ below
SELECT TOP 3 Customers.CustomerID, Customers.FirstName, Customers.LastName, COUNT(Orders.CustomerID) AS CustomerOrderCount
FROM Customers
INNER JOIN Orders
ON Customers.CustomerID = Orders.CustomerID
GROUP BY Customers.CustomerID, Customers.FirstName, Customers.LastName
ORDER BY CustomerOrderCount DESC;

-- SQL request(s)​​​​​​‌‌​‌​​​​​​​‌‌​‌‌​‌​​‌‌​​‌ below
SELECT TOP 3 Customers.CustomerID, Customers.FirstName, Customers.LastName, COUNT(OrderID) AS CustomerOrderCount
FROM Customers
INNER JOIN Orders
ON Customers.CustomerID = Orders.CustomerID
GROUP By Customers.CustomerID
ORDER By CustomerOrderCount DESC;

-- SQL request(s)​​​​​​‌‌​‌​​​​​​​‌‌​‌‌‌​‌‌​‌‌‌​ below
SELECT FirstName, LastName, City FROM Customers where LEFT(City,1) = 'R' order by city;

-- SQL Request(s)| below
SELECT CustomerID, FirstName, LastName, City FROM Customers where City Like 'R%' ORDER BY City;

-- SQL request(s)​​​​​​‌‌​‌​​​​​​​‌‌​‌‌‌‌‌‌‌​‌​‌ below
SELECT TOP 1 Orders.OrderID, Customers.FirstName, Customers.LastName, SUM(Dishes.Price) AS OrderTotal
FROM Customers
INNER JOIN Orders ON Customers.CustomerID = Orders.CustomerID
INNER JOIN OrdersDishes ON Orders.OrderID = OrdersDishes.OrderID
INNER JOIN Dishes ON OrdersDishes.DishID = Dishes.DishID
GROUP BY Orders.OrderID, Customers.FirstName, Customers.LastName
ORDER BY OrderTotal DESC;

-- SQL request(s)​​​​​​‌‌​‌​​​​​​​‌‌​‌‌‌‌‌‌‌​‌​‌ below
SELECT TOP 1 Orders.OrderID, Customers.FirstName, Customers.LastName, SUM(Dishes.Price) AS OrderTotal
FROM ORDERS
INNER JOIN OrdersDishes ON Orders.OrderID = OrdersDishes.OrderID
INNER JOIN Dishes ON OrdersDishes.DishID = Dishes.DishID
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID
GROUP BY OrdersDishes.Order.ID
ORDER BY OrderTotal DESC;

-- SQL request(s)​​​​​​‌‌​‌​​​​​​​‌‌​‌‌‌‌‌‌‌​‌​‌ below
SELECT AVG(OrderTotal) 
FROM 
    ( SELECT Orders.OrderID, SUM(Dishes.Price) as OrderTotal
      FROM Orders
      INNER JOIN OrdersDishes ON Orders.OrderID = OrdersDishes.OrderID
      INNER JOIN Dishes On OrdersDishes.DishID = Dishes.DishID
      GROUP BY OrdersDishes.OrderID );

-- SQL request(s)​​​​​​‌‌​‌​​​​​​​‌‌​‌‌‌‌‌‌‌​‌​‌ below
SELECT ROUND(AVG(OrderTotal),2) 
FROM 
    ( SELECT Orders.OrderID, SUM(Dishes.Price) as OrderTotal
      FROM Orders
      INNER JOIN OrdersDishes ON Orders.OrderID = OrdersDishes.OrderID
      INNER JOIN Dishes On OrdersDishes.DishID = Dishes.DishID
      GROUP BY OrdersDishes.OrderID );


## Comando do Linux Xubuntu para
## Criar Uma Pasta, com arquivos aleatórios
## de conteúdo aleatório de tambho aleatório
## até atingir 500gib



```
#!/bin/bash

total_size=0
max_size=$((500 * 1024 * 1024 * 1024))  # 500 GB em bytes
output_dir="arquivos_random"
mkdir -p "$output_dir"

while [ $total_size -lt $max_size ]; do
    file_name="$output_dir/$(uuidgen).txt"
    file_size=$(( RANDOM * RANDOM ))  # Tamanho aleatório
    file_size=$(( file_size % (10 * 1024 * 1024) ))  # Limitando a 10MB por arquivo

    base64 /dev/urandom | head -c $file_size > "$file_name"
    actual_size=$(stat -c%s "$file_name")
    total_size=$(( total_size + actual_size ))

    echo "Criado $file_name com $actual_size bytes. Total acumulado: $total_size bytes."
done

echo "Processo concluído! Total de 500GB alcançado."


data mundo
https://www.notion.so/Cronograma-Mentoria-Data-Mundo-60-Dias-211d8156dd768062aceac52076cb412e

