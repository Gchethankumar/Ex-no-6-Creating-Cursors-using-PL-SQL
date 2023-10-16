# Ex-no-6-Creating-Cursors-using-PL/SQL

## AIM:
To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
```
Developed By : Chethan Kumar G
Register number: 212222240022
```
### Create employee table
```sql
CREATE TABLE employee(empid NUMBER, empname VARCHAR(10), dept VARCHAR(10), salary NUMBER);
INSERT INTO employee VALUES(1,'Dileep','HR',600000);
INSERT INTO employee VALUES(2,'Anji','MD',950000);
INSERT INTO employee VALUES(3,'Jaggu','Finance',800000);
```
### SQL Cursor code
```sql
     set serveroutput on
     declare
  2  cursor employee_cursor is
  3  select empid, empname, dept, salary
  4  from employee;
  5  empid number;
  6  empname varchar(90);
  7  dept varchar(90);
  8  salary number;
  9  begin
 10  open employee_cursor;
 11  loop
 12  fetch employee_cursor into empid,empname,dept,salary;
 13  exit when employee_cursor%notfound;
 14  dbms_output.put_line('Employee ID: '||empid);
 15  dbms_output.put_line('Employee Name: '||empname);
 16  dbms_output.put_line('Department: '||dept);
 17  dbms_output.put_line('Salary: '||salary);
 18  dbms_output.put_line('-x-x-x-x-x-x-x-x-x-x-x-x-x-');
 19  end loop;
 20  close employee_cursor;
 21  end;
 22  /
```
## Output:
![Screenshot 2023-10-16 181740](https://github.com/Gchethankumar/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/118348224/448163a4-45ac-4952-89b0-983578e9edb6)

## Result:
Thus, a cursor using PL/SQL is created successfully.
