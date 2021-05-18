# sql-statements
sql-statements
* SELECT column1, column2, ...
* FROM table_name;
* SELECT * FROM table_name;

* SELECT DISTINCT column1, column2, ...
* FROM table_name;
* SELECT COUNT(DISTINCT Country) FROM Customers;
* SELECT Count(*) AS DistinctCountries
* FROM (SELECT DISTINCT Country FROM Customers);
* SELECT column1, column2, ...
* FROM table_name
* WHERE condition;
* SELECT * FROM Customers WHERE City LIKE 's%';
* SELECT * FROM Customers WHERE City IN ('Paris','London');

* SELECT column1, column2, ...
* FROM table_name
* WHERE condition1 AND condition2 AND condition3 ...;
* SELECT column1, column2, ...
* FROM table_name
* WHERE condition1 OR condition2 OR condition3 ...;
* SELECT column1, column2, ...
* FROM table_name
* WHERE NOT condition;
* SELECT * FROM Customers
* WHERE Country='Germany' AND (City='Berlin' OR City='München');

* SELECT * FROM Customers
* ORDER BY Country ASC, CustomerName DESC;

* The INSERT INTO statement is used to insert new records in a table.
* INSERT INTO table_name (column1, column2, column3, ...)
* VALUES (value1, value2, value3, ...);
* INSERT INTO table_name
* VALUES (value1, value2, value3, ...);
* INSERT INTO Customers (CustomerName, City, Country)
* VALUES ('Cardinal', 'Stavanger', 'Norway');
* How to Test for NULL Values?
* SELECT column_names
* FROM table_name
* WHERE column_name IS NULL;
* SELECT column_names
* FROM table_name
* WHERE column_name IS NOT NULL;
* UPDATE table_name
* SET column1 = value1, column2 = value2, ...
* WHERE condition;
* UPDATE Customers
* SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
* WHERE CustomerID = 1;
* UPDATE Customers
* SET ContactName='Juan'
* WHERE Country='Mexico'; // update multiple record

* DELETE FROM table_name WHERE condition;
* DELETE FROM table_name // delete all records

* SELECT column_name(s)
* FROM table_name
* WHERE condition
* LIMIT number;

* SELECT MIN(column_name)
* FROM table_name
* WHERE condition;
* SELECT MAX(column_name)
* FROM table_name
* WHERE condition;
* SELECT MIN(Price) AS SmallestPrice
* Second max salary
* SELECT name, MAX(salary) AS salary
  * FROM employee
 * WHERE salary < (SELECT MAX(salary) FROM employee);

* FROM Products;
* SELECT MAX(Price) AS LargestPrice
* FROM Products;
* COUNT() function returns the number of rows that matches a specified criterion.
* SELECT COUNT(ProductID)
* FROM Products;// finds the number of products:

* SELECT * FROM Customers
* WHERE Country IN ('Germany', 'France', 'UK');
* SELECT * FROM Customers
* WHERE Country NOT IN ('Germany', 'France', 'UK');
* SELECT * FROM Customers
* WHERE Country IN (SELECT Country FROM Suppliers);

* SELECT column_name(s)
* FROM table_name
* WHERE column_name BETWEEN value1 AND value2;
* SELECT * FROM Products
* WHERE Price NOT BETWEEN 10 AND 20;
* SELECT * FROM Products
* WHERE Price BETWEEN 10 AND 20
* AND CategoryID NOT IN (1,2,3);
* Concat
* SELECT CustomerName, Address + ', ' + PostalCode + ' ' + City + ', ' + Country AS Address
* FROM Customers;
* SELECT CustomerName, CONCAT(Address,', ',PostalCode,', ',City,', ',Country) AS Address
* FROM Customers;
* Alias for Tables Example
* SELECT o.OrderID, o.OrderDate, c.CustomerName
* FROM Customers AS c, Orders AS o
* WHERE c.CustomerName='Around the Horn' AND c.CustomerID=o.CustomerID;

* SELECT Orders.OrderID, Customers.CustomerName
* FROM Orders
* INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
* The INNER JOIN keyword selects all rows from both tables as long as there is a match between the columns. If there are records in the "Orders" table that do not * have matches in "Customers", these orders will not be shown!
* SELECT Orders.OrderID, Customers.CustomerName, Shippers.ShipperName
* FROM ((Orders
* INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID)
* INNER JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID);







* CREATE INDEX index_name
* ON table_name (column_name);
* CREATE UNIQUE INDEX index_name
* on table_name (column_name);
* CREATE INDEX index_name
* on table_name (column1, column2);

* ALTER TABLE table_name ADD column_name datatype;
* ALTER TABLE table_name DROP COLUMN column_name;
* ALTER TABLE table_name MODIFY COLUMN column_name datatype;
* ALTER TABLE table_name MODIFY column_name datatype NOT NULL;
* ALTER TABLE table_name 
* ADD CONSTRAINT MyUniqueConstraint UNIQUE(column1, column2...);
* ALTER TABLE table_name 
* DROP CONSTRAINT MyUniqueConstraint;

* TRUNCATE TABLE  table_name;

* CREATE PROCEDURE procedure_name
* AS
* sql_statement
* GO;
* EXEC procedure_name;
