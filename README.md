#Create database
CREATE DATABASE SalesDB;
USE SalesDB;
ALTER DATABASE OldSalesDB MODIFY NAME = NewSalesDB;
BACKUP DATABASE SalesDB TO DISK = 'C:\Backup\SalesDB.bak';
RESTORE DATABASE SalesDB FROM DISK = 'C:\Backup\SalesDB.bak' WITH REPLACE;

DROP DATABASE demo;
CREATE TABLE Products ( ProductID INT PRIMARY KEY, ProductName NVARCHAR(100) UNIQUE, Price DECIMAL(10, 2) NOT NULL, Category NVARCHAR(50) CHECK (Category IN ('Electronics', 'Clothing', 'Food', 'Furniture')) );
