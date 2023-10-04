# Ex. No: 6 Creating Cursors using PL/SQL

## AIM: To create a cursor using PL/SQL.

## Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

## Program:

### Create employee table

create table employee1(empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);

### PLSQL Cursor code
```
set serveroutput on;

declare

cursor employee_cursor is

select EMPID,EMPNAME,DEPT,SALARY

from employee1;

emp_id number;

emp_name varchar(50);

emp_dept varchar(50);

emp_salary number;

begin

open employee_cursor;

loop

fetch employee_cursor into emp_id,emp_name,emp_dept,emp_salary;

exit when employee_cursor%NOTFOUND;

dbms_output.put_line('EMPLOYEE ID: ' || emp_id);

dbms_output.put_line('EMPLOYEE NAME: ' || emp_name);

dbms_output.put_line('DEPARTMENT: ' || emp_dept);

dbms_output.put_line('SALARY ' || emp_salary);

dbms_output.put_line('----------------------');

END LOOP;

close employee_cursor;

end;

/
```
## Output:
![image](https://github.com/Anandanaruvi/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/120443233/6a35e7b4-c474-4350-982d-7eb5674dee59)
