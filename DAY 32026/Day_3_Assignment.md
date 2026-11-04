DBMS LAB ASSIGNMENT – 3

Q1. Create table EMPLOYEE with the following details.

Answer:

CREATE TABLE EMPLOYEE (
    EMPLOYEE_ID NUMBER(6),
    LAST_NAME VARCHAR2(25),
    JOB_ID VARCHAR2(10),
    SALARY NUMBER(8,2),
    COMM_PCT NUMBER(4,2),
    MGR_ID NUMBER(6),
    DEPARTMENT_ID NUMBER(4)
);

Q2. Insert the following data into EMPLOYEE table.

Answer:

INSERT INTO EMPLOYEE VALUES (198, 'Connell', 'SH_CLERK', 2600, 2.5, 124, 50);

INSERT INTO EMPLOYEE VALUES (199, 'Grant', 'SH_CLERK', 2600, 2.2, 124, 50);

INSERT INTO EMPLOYEE VALUES (200, 'Whalen', 'AD_ASST', 4400, 1.3, 101, 10);

INSERT INTO EMPLOYEE VALUES (201, 'Hartstein', 'IT_PROG', 6000, NULL, 100, 20);

INSERT INTO EMPLOYEE VALUES (202, 'Fay', 'AC_MGR', 6500, NULL, 210, 20);

INSERT INTO EMPLOYEE VALUES (203, 'Mavris', 'AD_VP', 7500, NULL, 101, 40);

INSERT INTO EMPLOYEE VALUES (204, 'Baer', 'AD_PRES', 3500, 1.5, 101, 90);

INSERT INTO EMPLOYEE VALUES (205, 'Higgins', 'AC_MGR', 2300, NULL, 101, 60);

INSERT INTO EMPLOYEE VALUES (206, 'Gitz', 'IT_PROG', 5000, NULL, 103, 60);

INSERT INTO EMPLOYEE VALUES (100, 'King', 'AD_ASST', 8956, 0.3, 108, 100);

INSERT INTO EMPLOYEE VALUES (101, 'Kochar', 'SH_CLERK', 3400, 1.3, 118, 30);

COMMIT;

Q3. Display last_name, job_id, employee_id for each employee with employee_id appearing first.

Answer:

SELECT EMPLOYEE_ID, LAST_NAME, JOB_ID
FROM EMPLOYEE
ORDER BY EMPLOYEE_ID;

Q4. Display the details of all employees of department 60.

Answer:

SELECT *
FROM EMPLOYEE
WHERE DEPARTMENT_ID = 60;

Q5. Display the employee details of the employee whose last_name is King.

Answer:

SELECT *
FROM EMPLOYEE
WHERE LAST_NAME = 'King';

Q6. Display unique job_id from EMPLOYEE table. Give alias name to the column as JOB_TITLE.

Answer:

SELECT DISTINCT JOB_ID AS JOB_TITLE
FROM EMPLOYEE;

Q7. Display last_name, salary and salary increase of Rs.300. Give the new column name as 'Increased Salary'.

Answer:

SELECT LAST_NAME, SALARY,
       SALARY + 300 AS "Increased Salary"
FROM EMPLOYEE;

Q8. Display last_name, salary and annual compensation of all employees, plus a one-time bonus of Rs.100. Give an alias name to the column displaying annual compensation.

Answer:

SELECT LAST_NAME, SALARY,
       (SALARY * 12) + 100 AS "Annual Compensation"
FROM EMPLOYEE;

Q9. Display the details of those employees who get commission.

Answer:

SELECT *
FROM EMPLOYEE
WHERE COMM_PCT IS NOT NULL;

Q10. Display the details of those employees who do not get commission.

Answer:

SELECT *
FROM EMPLOYEE
WHERE COMM_PCT IS NULL;

Q11. Display the Employee_id, Department_id and Salary of all employees whose salary is greater than 5000.

Answer:

SELECT EMPLOYEE_ID, DEPARTMENT_ID, SALARY
FROM EMPLOYEE
WHERE SALARY > 5000;

Q12. Display the Last_Name and Salary of all employees whose salary is between 4000 and 7000.

Answer:

SELECT LAST_NAME, SALARY
FROM EMPLOYEE
WHERE SALARY BETWEEN 4000 AND 7000;

Q13. Display the details of all employees whose salary is either 6000 or 6500 or 7000.

Answer:

SELECT *
FROM EMPLOYEE
WHERE SALARY IN (6000, 6500, 7000);

Q14. Display the details of all those employees who work either in department 10 or 20 or 30 or 50.

Answer:

SELECT *
FROM EMPLOYEE
WHERE DEPARTMENT_ID IN (10, 20, 30, 50);

Q15. Display the details of all employees whose salary is not equal to 5000.

Answer:

SELECT *
FROM EMPLOYEE
WHERE SALARY <> 5000;

Q16. Display the details of all the CLERKS working in the organization.

Answer:

SELECT *
FROM EMPLOYEE
WHERE JOB_ID LIKE '%CLERK%';

Q17. Update the job_id's of the employees who earn more than 5000 to Grade_A. Display the table EMPLOYEE after updating.

Answer:

UPDATE EMPLOYEE
SET JOB_ID = 'Grade_A'
WHERE SALARY > 5000;

COMMIT;

SELECT *
FROM EMPLOYEE;

Q18. Display the details of all those employees who are either CLERK or PROGRAMMER or ASSISTANT.

Answer:

SELECT *
FROM EMPLOYEE
WHERE JOB_ID LIKE '%CLERK%'
   OR JOB_ID LIKE '%PROG%'
   OR JOB_ID LIKE '%ASST%';

Q19. Display those employees from the EMPLOYEE table whose designation is CLERK and salary is less than 3000.

Answer:

SELECT *
FROM EMPLOYEE
WHERE JOB_ID LIKE '%CLERK%'
AND SALARY < 3000;

Q20. Display those employees' Last_Name, Mgr_id from the EMPLOYEE table whose salary is above 3000 and work under Manager 101.

Answer:

SELECT LAST_NAME, MGR_ID
FROM EMPLOYEE
WHERE SALARY > 3000
AND MGR_ID = 101;
