# Practice Questions - SQL

## SQL Question 1: Flights 

Write an SQL query to display:
The **Flight ID** and the **Name of the pilot(s)** for all flights departing from 'Dubai', where the pilots have the designation **'Captain'**. The pilot's name should be displayed by renaming the column as 'Pilot Name'.
Your output should have two columns as given below:

| Flight ID | Pilot Name |
| :---: | :---: |

### Database Schema:

| Table Name | Key Column | Other Columns |
| :--- | :--- | :--- |
| **FLIGHTS** | `Flight_ID` (PK) | `Departure_City` (or `Departure_Airport_Code`), ... |
| **PILOTS** | `Pilot_ID` (PK) | `Pilot_Name`, `Designation`, ... |
| **FLIGHT_PILOTS** | (Composite PK) | `Flight_ID` (FK), `Pilot_ID` (FK) |

---

## SQL Question 2: Books

Write an SQL query to display:
The **Title**, **Price**, and **ISBN** of books that were published **after January 1, 1940**, and that fall under the **"C102" category**.
Your output should have three columns as given below:

| Title | Price | ISBN |
| :---: | :---: | :---: |

### Database Schema:

| Table Name | Key Column | Other Columns |
| :--- | :--- | :--- |
| **BOOKS** | `ISBN` (PK) | `Title`, `Price`, `Publication_Date`, `Category_ID` |

---

## SQL Question 3: Employees

Write an SQL query to display:
The **Employee ID**, **Name**, **Basic salary**, and **Net pay** for employees whose **basic salary is greater than 5,000**.
Your output should have 4 columns as given below:

| EMPID | EMPNAME | BASIC | NETPAY |
| :---: | :---: | :---: | :---: |

###  Database Schema:

| Table Name | Key Column | Other Columns |
| :--- | :--- | :--- |
| **EMPLOYEES** | `EMPID` (PK) | `EMPNAME`, `BASIC` (salary), `NETPAY` |

---

## SQL Question 4: Students

Write an SQL query to display:
The **Student ID**, **first name**, **email** of students whose email domain is **'aol.com'** and whose first name **starts with 'P'**. Use alias "Student ID", "First Name", "Email".
Your output should have 3 columns as given below:

| Student ID | First Name | Email |
| :---: | :---: | :---: |

### Database Schema:

This query requires a single table containing student personal and contact details.

| Table Name | Key Column | Other Columns |
| :--- | :--- | :--- |
| **STUDENTS** | `Student_ID` (PK) | `First_Name`, `Email`, ... |

---