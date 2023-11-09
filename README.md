# adventureWorks2012_sql






SELECT TOP 10 * FROM Sales.SalesOrderHeader;

USE AdventureWorks2012;

SELECT 
    SUM(SubTotal) AS TotalSales
FROM 
    Sales.SalesOrderHeader
WHERE 
    OrderDate >= '2011-05-01' AND OrderDate < '2011-06-01';

	USE AdventureWorks2012;

SELECT 
    SalesOrderID,
    OrderDate,
    SubTotal
FROM 
    Sales.SalesOrderHeader
WHERE 
    MONTH(OrderDate) = 5 AND YEAR(OrderDate) = 2011;

	USE AdventureWorks2012;

SELECT 
    MONTH(OrderDate) AS Month,
    YEAR(OrderDate) AS Year,
    SUM(SubTotal) AS TotalSales
FROM 
    Sales.SalesOrderHeader
WHERE 
    YEAR(OrderDate) = 2011
GROUP BY 
    MONTH(OrderDate), YEAR(OrderDate)
ORDER BY 
    TotalSales;


	USE AdventureWorks2012;

SELECT 
    MONTH(OrderDate) AS Month,
    YEAR(OrderDate) AS Year,
    SUM(SubTotal) AS TotalSales
FROM 
    Sales.SalesOrderHeader
WHERE 
    YEAR(OrderDate) = 2011
GROUP BY 
    MONTH(OrderDate), YEAR(OrderDate)
ORDER BY 
    TotalSales; -- Order directly by TotalSales


	USE AdventureWorks2012; 

SELECT
    p.BusinessEntityID,
    p.FirstName,
    p.LastName,
    e.EmailAddress,
    ph.PhoneNumber,
    pt.Name AS PhoneNumberType
FROM
    Person.Person AS p
LEFT JOIN
    Person.EmailAddress AS e ON p.BusinessEntityID = e.BusinessEntityID
LEFT JOIN
    Person.PersonPhone AS ph ON p.BusinessEntityID = ph.BusinessEntityID
LEFT JOIN
    Person.PhoneNumberType AS pt ON ph.PhoneNumberTypeID = pt.PhoneNumberTypeID;



