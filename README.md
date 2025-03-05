-- Departments tablosunun olusturulmasi ve veri eklenmesi
CREATE TABLE Departments (
DepartmentID INT PRIMARY KEY,
DepartmentName VARCHAR(58) NOT Null
);

INSERT INTO Departments (DepartmentID, DepartmentNaMe) VALUES
(1, 'IT'),
(2, 'HR'),
(3, 'Finance');

--Employees Cablosunun olusturutnasi ve ver ektennest
CREATE TABLE Employees(
EmployeeID int PRIMARY Key,
FirstNaMe VARCHAR(50) NOT NULL,
LastName varchar(50) not null,
Age INT,
DepartmentID INT,
Salary DECIMAL(10,2),
JoinDate DATE,
FOREIGN KEY (DepartmentID) REFERENCES Departments(DepartmentID));

INSERT INTO Employees (EmployeeID, FirstName, LastName, Age, DepartmentID, Salary, JoinDate) VALUES
(1, 'John', 'Doe', 30, 1, 55000, '2020-01-15'),
(2, 'Jane', 'Smith', 45, 2, 65000, '2018-07-20'),
(3, 'Sam', 'Brown', 28, 1, 52000, '2021-04-25'),
(4, 'Lisa', 'White', 35, 3, 70000, '2019-03-18'),
(5, 'Mark', 'Black', 50, 1, 75000, '2015-11-05'),
(6, 'Lucy', 'Green', 40, 2, 60000, '2017-10-10');

--a şıkkı
select FirstName,LastName, Salary from employees;
--b şıkkı
select distinct * from departments;
--c şıkkı
select * from departments
where departmentname = 'IT';
--d şıkkı
select salary from employees
order by salary asc;
--e şıkkı
select concat(FirstName, ' ' ,LastName) AS FirstLastName
from employees
order by FirstLastName asc;
