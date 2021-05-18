# sql-statements
sql-statements
SELECT column1, column2, ...
FROM table_name;
SELECT * FROM table_name;

SELECT DISTINCT column1, column2, ...
FROM table_name;
SELECT COUNT(DISTINCT Country) FROM Customers;
SELECT Count(*) AS DistinctCountries
FROM (SELECT DISTINCT Country FROM Customers);
