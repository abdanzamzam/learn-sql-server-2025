
# SQL Server Tutorial: Medium

## 1. Advanced SQL Syntax
- Using Aliases:
  - Column alias (`AS` keyword).
  - Table alias for shorter queries.
- Nested Queries:
  - Subqueries in `SELECT`, `FROM`, and `WHERE`.
  - Correlated subqueries.
- Case Statements:
  - Conditional logic with `CASE`:
    ```sql
    SELECT Name, 
           CASE 
               WHEN Age >= 18 THEN 'Adult'
               ELSE 'Minor'
           END AS Category
    FROM Persons;
    ```

---

## 2. Working with Relationships
- **One-to-One Relationship:**
  - Creating and querying one-to-one relationships.
- **One-to-Many Relationship:**
  - Foreign keys for one-to-many relationships.
  - Writing queries to retrieve related data.
- **Many-to-Many Relationship:**
  - Using junction tables.
  - Querying many-to-many relationships.

---

## 3. Advanced Joins
- **Self Joins:**
  - Joining a table with itself.
  - Example: Employee hierarchy queries.
- **Full Outer Join:**
  - Combining `LEFT JOIN` and `RIGHT JOIN`.
  - Querying unmatched data from both tables.
- **Cross Join:**
  - Cartesian product of two tables.
  - Use cases and limitations.

---

## 4. Advanced Filtering
- **Using `GROUP BY` and Aggregates:**
  - Grouping data with `GROUP BY`.
  - Filtering grouped data using `HAVING`.
- **Using Wildcards:**
  - Advanced pattern matching with `LIKE`, `%`, and `_`.
- **Advanced Filtering with Conditions:**
  - Combining `AND`, `OR`, and parentheses for complex filters.

---

## 5. Transactions and Error Handling
- **Transactions:**
  - What is a transaction?
  - Using `BEGIN TRANSACTION`, `COMMIT`, and `ROLLBACK`.
  - Example of a transaction:
    ```sql
    BEGIN TRANSACTION;
    UPDATE Accounts SET Balance = Balance - 500 WHERE AccountID = 1;
    UPDATE Accounts SET Balance = Balance + 500 WHERE AccountID = 2;
    COMMIT;
    ```
- **Error Handling:**
  - Using `TRY...CATCH` blocks.
  - Example:
    ```sql
    BEGIN TRY
        UPDATE Accounts SET Balance = Balance - 500 WHERE AccountID = 1;
    END TRY
    BEGIN CATCH
        PRINT 'Error occurred: ' + ERROR_MESSAGE();
    END CATCH;
    ```

---

## 6. Stored Procedures
- What are Stored Procedures?
- Creating a Stored Procedure:
  ```sql
  CREATE PROCEDURE GetCustomerOrders
  @CustomerID INT
  AS
  BEGIN
      SELECT * FROM Orders WHERE CustomerID = @CustomerID;
  END;
  ```
- Executing a Stored Procedure:
  ```sql
  EXEC GetCustomerOrders @CustomerID = 1;
  ```
- Using Input and Output Parameters.

---

## 7. Functions
- **System Functions:**
  - Date and time functions: `GETDATE()`, `DATEADD()`, `DATEDIFF()`.
  - String functions: `SUBSTRING()`, `CHARINDEX()`, `REPLACE()`.
- **User-Defined Functions:**
  - Scalar functions:
    ```sql
    CREATE FUNCTION GetFullName (@FirstName NVARCHAR(50), @LastName NVARCHAR(50))
    RETURNS NVARCHAR(100)
    AS
    BEGIN
        RETURN @FirstName + ' ' + @LastName;
    END;
    ```
  - Table-valued functions.

---

## 8. Views
- Advanced View Concepts:
  - Updating data through views.
  - Indexed views.
- Security with Views:
  - Restricting access to specific columns using views.

---

## 9. Index Optimization
- Clustered vs. Non-Clustered Indexes:
  - Understanding the differences and use cases.
- Covering Index:
  - Improving query performance with covering indexes.
- Maintaining Indexes:
  - Rebuilding and reorganizing indexes.

---

## 10. Practical Use Cases
- **Building Advanced Queries:**
  - Joining multiple tables.
  - Aggregating data across tables.
- **Real-World Case Studies:**
  - Inventory management: Tracking stock levels.
  - Sales reporting: Aggregating sales by region and time.
- **Challenges:**
  - Write a query to find the top 3 highest-selling products in each category.
  - Create a stored procedure to calculate employee bonuses based on performance.

---

This tutorial is tailored for users with a basic understanding of SQL Server who are looking to deepen their skills. Let me know if you need detailed examples or an export in a specific format! 😊
