# Exp-8-Implement-the-keyword-Case-Cross-Join-full-outer-join

## Aim:
To do operations on sql based on CASE,CROSS JOIN,FULL OUTER JOIN.
## Code:
```
Case:
```
```--create
CREATE TABLE EMPLOYEE (
  empId INTEGER PRIMARY KEY,
  firstname TEXT NOT NULL,
  lastname TEXT NOT NULL,
  salary INTEGER NOT NULL
);
--insert
INSERT INTO EMPLOYEE VALUES (0001, 'Harry', 'potter',1000);
INSERT INTO EMPLOYEE VALUES (0002, 'Dave', 'John',3500);
INSERT INTO EMPLOYEE VALUES (0003, 'Ava', 'Grayson',7000);
INSERT INTO EMPLOYEE VALUES (0004, 'Eda', 'Srikar',1200);
INSERT INTO EMPLOYEE VALUES (0005, 'Robert', 'Brown',2500);
INSERT INTO EMPLOYEE VALUES (0006, 'Will', 'John',9000);

SELECT empId,firstname,lastname,salary,
CASE
WHEN salary<3000 THEN "Low"
WHEN salary>3000 AND salary<5000 THEN "Average"
ELSE "High"
END AS result
FROM EMPLOYEE;
```
```
Cross Join:
```
```
CREATE TABLE sales_organization 
(
	sales_org_id INT PRIMARY KEY,
	sales_org VARCHAR (255)
);
CREATE TABLE sales_channel 
(
	channel_id INT PRIMARY KEY,
	channel_name VARCHAR (255)
);
INSERT INTO sales_organization (sales_org_id, sales_org)
VALUES
(1, 'Domestic'),
(2, 'Export');
INSERT INTO sales_channel (channel_id, channel_name)
VALUES
(1, 'Wholesale'),
(2, 'Retail'),
(3, 'eCommerce'),
(4, 'TV Shopping');
SELECT
sales_org,
channel_name
FROM
sales_organization
CROSS JOIN sales_channel;
```
```
Full Outer Join:
```
```
CREATE TABLE fruits (
fruit_id INTEGER PRIMARY KEY,
fruit_name VARCHAR (255) NOT NULL,
basket_id INTEGER
);
CREATE TABLE baskets (
basket_id INTEGER PRIMARY KEY,
basket_name VARCHAR (255) NOT NULL
);
INSERT INTO baskets (basket_id, basket_name)
VALUES
(1, 'A'),
(2, 'B'),
(3, 'C');
INSERT INTO fruits (fruit_id,fruit_name,basket_id)
VALUES
(1, 'Apple', 1),
(2, 'Orange', 1),
(3, 'Banana', 2),
(4, 'Strawberry', NULL);
SELECT
basket_name,
fruit_name
FROM
fruits
FULL OUTER JOIN baskets ON baskets.basket_id = fruits.basket_id;
```
## Output:
### Case:
![image](https://github.com/Archana2003-Jkumar/SQL-ASSIGNMENT-/assets/93427594/791ea1b9-8730-4a3b-8afe-7618ff03631c)
### Cross join:
![image](https://github.com/Archana2003-Jkumar/SQL-ASSIGNMENT-/assets/93427594/a9c355d6-23b4-4738-96b1-b5d72f88bff2)
### Full outer join:
![image](https://github.com/Archana2003-Jkumar/SQL-ASSIGNMENT-/assets/93427594/648b7d80-b55e-472d-9db9-8977b8d2c6f6)
## Result:
Hence the program has been successfully completed.
