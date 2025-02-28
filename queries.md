# Database Queries

## Find all customers with postal code 1010

```sql
SELECT *
FROM Customers
WHERE PostalCode = 1010
```

## Find the phone number for the supplier with the id 11

```sql
SELECT *
FROM Suppliers
WHERE SupplierID = 11
```

## List first 10 orders ever places, descending by the order date

```sql
Select *
FROM Orders
ORDER BY OrderDate DESC
LIMIT 10
```

## Find all customers that live in London, Madrid, or Brazil

```sql
SELECT * 
FROM Customers
WHERE Country 
	IN ('London',
    	'Madrid',
      'Brazil')
```

## Add a customer record for "The Shire", the contact name is "Bilbo Baggins" the address is -"1 Hobbit-Hole" in "Bag End", postal code "111" and the country is "Middle Earth"

```SQL
INSERT INTO Customers (CustomerName, 
											 ContactName, 
											 Address, 
											 City, 
											 PostalCode, 
											 Country)
VALUES ("The Shire", 
				"Bilbo Baggins", 
				"1 Hobbit-Hole", 
				"Bag End", 
				111, 
				"Middle Earth")
```

## Update Bilbo Baggins record so that the postal code changes to "11122"

- To run in your itteration of the test DB change `WHERE CustomerID = 92 AND ContactName = "Bilbo Baggins"` to be `WHERE ContactName = "Bilbo Baggins"`. This change
	is need if your `Bilbo Baggins` DOES NOT have a CustomerID of 92.

```sql
UPDATE Customers
SET PostalCode = 11122
WHERE CustomerID = 92
AND ContactName = "Bilbo Baggins"
```

## (Stretch) Find a query to discover how many different cities are stored in the Customers table. Repeats should not be double counted

```sql
Select COUNT(DISTINCT Country)
FROM Customers
```

## (Stretch) Find all suppliers who have names longer than 20 characters. You can use `length(SupplierName)` to get the length of the name

```sql
SELECT *
FROM Suppliers
WHERE LENGTH(SupplierName)  > 20
```
