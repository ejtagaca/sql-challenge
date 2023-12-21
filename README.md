# sql-challenge

ERD

![image](https://github.com/ejtagaca/sql-challenge/assets/16442065/0f092bcb-0b89-4e43-b48a-15180d43fb3c)



--1. List the employee number, last name, first name, sex, and salary of each employee.


SELECT e.last_name, e.first_name, e.sex, s.salary


FROM employees as e


INNER JOIN salaries AS s ON e.emp_no = s.emp_no;


![image](https://github.com/ejtagaca/sql-challenge/assets/16442065/df035e09-c731-4085-8a7b-ac268be70905)


--2. List the first name, last name, and hire date for the employees who were hired in 1986.


SELECT e.last_name, e.first_name, e.hire_date


FROM employees AS e


WHERE e.hire_date >= '1986-01-01' AND e.hire_date <= '1986-12-31';


![image](https://github.com/ejtagaca/sql-challenge/assets/16442065/5ff53179-3ba9-4218-a7de-40b226334223)


--3. List the manager of each department along with their department number, 


--   department name, employee number, last name, and first name.


SELECT dm.dept_no, d.dept_name, dm.emp_no, e.last_name, e.first_name


FROM dept_manager AS dm


INNER JOIN departments AS d ON dm.dept_no = d.dept_no


INNER JOIN employees AS e ON dm.emp_no = e.emp_no;


![image](https://github.com/ejtagaca/sql-challenge/assets/16442065/340d3b3b-16da-4e55-bd00-5e6d55380d21)

--4. List the department number for each employee along with that 


--   employee’s employee number, last name, first name, and department name.


SELECT de.dept_no, e.emp_no, e.last_name, e.first_name, d.dept_name


FROM employees as e


INNER JOIN dept_emp as de ON e.emp_no = de.emp_no


INNER JOIN departments as d ON de.dept_no = d.dept_no


![image](https://github.com/ejtagaca/sql-challenge/assets/16442065/d9c50f28-ce44-4250-9545-f7235f4f914c)


--5. List first name, last name, and sex of each employee whose 


--   first name is Hercules and whose last name begins with the letter B.


SELECT e.first_name, e.last_name, e.sex


FROM employees as e


WHERE 1=1


AND e.first_name = 'Hercules'


AND e.last_name LIKE 'B%'


![image](https://github.com/ejtagaca/sql-challenge/assets/16442065/41fe7de1-4efb-47ca-8d5d-63bd443f47df)


--6. List each employee in the Sales department, including their employee number, 


--   last name, and first name.


SELECT e.emp_no, e.last_name, e.first_name


FROM employees as e


INNER JOIN dept_emp as de ON de.emp_no = e.emp_no


INNER JOIN departments AS d ON de.dept_no = d.dept_no


WHERE d.dept_name IN 


(


	'Sales'

 
);


![image](https://github.com/ejtagaca/sql-challenge/assets/16442065/1b667ca8-b3d7-407c-8b64-f639d8719a21)


--7. List each employee in the Sales and Development departments, 


--   including their employee number, last name, first name, and department name.


SELECT e.emp_no, e.last_name, e.first_name, d.dept_name


FROM employees as e


INNER JOIN dept_emp as de ON de.emp_no = e.emp_no


INNER JOIN departments AS d ON de.dept_no = d.dept_no


WHERE d.dept_name IN 


(


	'Sales', 'Development'

 
);


![image](https://github.com/ejtagaca/sql-challenge/assets/16442065/7b3899c4-642b-401e-8854-e0db30a99a52)


--8. List the frequency counts, in descending order, of all the employee last names


--   (that is, how many employees share each last name).


SELECT last_name, COUNT(*)


FROM employees


GROUP BY last_name


ORDER BY 2 DESC 


![image](https://github.com/ejtagaca/sql-challenge/assets/16442065/01f3bc56-413a-429c-b6e9-41d7d22fc0df)



