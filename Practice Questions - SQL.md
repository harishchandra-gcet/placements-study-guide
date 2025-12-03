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

| Table Name | Key Column | Other Columns |
| :--- | :--- | :--- |
| **STUDENTS** | `Student_ID` (PK) | `First_Name`, `Email`, ... |

---

## SQL Question 5: Customer Order Status

Write an SQL query to display:
The **names** (use the alias **First Name**) and the **status of the items** ordered by customers with names starting with **'C'**.

Your output should have 2 columns as given below:

| First Name | Status |
| :---: | :---: |

### Database Schema:

| Table Name | Key Column | Other Columns |
| :--- | :--- | :--- |
| **CUSTOMERS** | `Customer_ID` (PK) | `First_Name`, `Last_Name`, ... |
| **ORDERS** or **ITEMS** | `Order_ID` (PK) | `Customer_ID` (FK), `Status` (e.g., 'Shipped', 'Processing'), ... |

---

## SQL Question 6: Lecture Timings

Write an SQL query to display:
All the **lecture timings on Friday** encoded as 'fr' (use alias **Timings**).

**Hint**: Lecture timings are a combination of start and end time in the below format:
`starttime-endtime`

Your output should have 1 column as given below:

| Timings |
| :---: |

### Database Schema:

| Table Name | Key Column | Other Columns |
| :--- | :--- | :--- |
| **SCHEDULE** | `Lecture_ID` (PK) | `Day_of_Week` (e.g. 'Friday'), `Start_Time`, `End_Time`, ... |
