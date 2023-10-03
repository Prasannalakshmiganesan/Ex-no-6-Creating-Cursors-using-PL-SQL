# Ex. No: 5 Creating Cursors using PL/SQL

### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table
![272232998-d6ba61a1-4f82-4276-9101-c38622bda21e](https://github.com/Prasannalakshmiganesan/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/118610231/51b09e0c-b30b-4f60-bd71-b11e33624186)

### PLSQL Cursor code
declare 
	cursor employee_cursor is
		select empid,ename,dept,salary
		from employee;
	
	emp_id number;
	emp_name varchar2(10);
	emp_dept varchar2(10);
	emp_salary number;
begin
	open employee_cursor;
	loop 
		fetch employee_cursor into emp_id, emp_name, emp_dept, emp_salary;
	exit when employee_cursor%notfound;

	dbms_output.put_line('Employee id: ' || emp_id);
	dbms_output.put_line('Employee Name: ' || emp_name);
	dbms_output.put_line('Department: ' || emp_dept);
	dbms_output.put_line('Salary: ' || emp_salary);
	dbms_output.put_line('------------------------');
	end loop;

close employee_cursor;
end;
/

### Output:
![image](https://github.com/Prasannalakshmiganesan/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/118610231/2593080b-b59f-44c1-b0eb-0dbe2206a185)

### Result:
A Cursor is successfully created.
