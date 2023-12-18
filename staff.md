# Expense Management System API Documentation

Welcome to the Expense Management System API documentation. This API provides endpoints to manage departments, designations, staff, expenses, and salary information.

## Table of Contents
1. [Department](#department)
    - [List Departments](#list-departments)
    - [Create Department](#create-department)
    - [Retrieve, Update, Delete Department](#retrieve-update-delete-department)

2. [Designation](#designation)
    - [List Designations](#list-designations)
    - [Create Designation](#create-designation)
    - [Retrieve, Update, Delete Designation](#retrieve-update-delete-designation)

3. [Staff](#staff)
    - [List Staff Members](#list-staff-members)
    - [Create Staff Member](#create-staff-member)
    - [Retrieve, Update, Delete Staff Member](#retrieve-update-delete-staff-member)
    - [Get Staff Expense History](#get-staff-expense-history)
    - [Generate Monthly Report for Staff](#generate-monthly-report-for-staff)
    - [Create Staff Attendance](#create-staff-attendance)
    - [Get Staff Attendance List](#get-staff-attendance-list)

4. [Expense](#expense)
    - [List Expenses](#list-expenses)
    - [Create Expense](#create-expense)
    - [Retrieve, Update, Delete Expense](#retrieve-update-delete-expense)
    - [List Expense Categories](#list-expense-categories)
    - [List Expense Sub-Categories](#list-expense-sub-categories)

5. [Salary](#salary)
    - [Create Salary](#create-salary)
    - [Get Salary Report](#get-salary-report)

6. [Miscellaneous](#miscellaneous)
    - [Get Expense History for a Staff Member](#get-expense-history-for-a-staff-member)

## Department

### List Departments
**Endpoint:** `/departments/`  
**Method:** GET  
**Description:** Retrieve a list of all departments.

### Create Department
**Endpoint:** `/departments/`  
**Method:** POST  
**Description:** Create a new department.  
**JSON Data:**
```json
{
  "name": "New Department"
}
```

### Retrieve, Update, Delete Department
**Endpoint:** `/departments/{department_id}/`  
**Methods:** GET, PUT, DELETE  
**Description:** Retrieve, update, or delete a specific department.

## Designation

### List Designations
**Endpoint:** `/designations/`  
**Method:** GET  
**Description:** Retrieve a list of all designations.

### Create Designation
**Endpoint:** `/designations/`  
**Method:** POST  
**Description:** Create a new designation.  
**JSON Data:**
```json
{
  "name": "New Designation"
}
```

### Retrieve, Update, Delete Designation
**Endpoint:** `/designations/{designation_id}/`  
**Methods:** GET, PUT, DELETE  
**Description:** Retrieve, update, or delete a specific designation.

## Staff

### List Staff Members
**Endpoint:** `/staff/`  
**Method:** GET  
**Description:** Retrieve a list of all staff members.

### Create Staff Member
**Endpoint:** `/staff/`  
**Method:** POST  
**Description:** Create a new staff member.  
**JSON Data:**
```json
{
  "name": "John Doe",
  "father_name": "Doe Sr.",
  "mother_name": "Doe Sr.",
  ...
  // Other staff details
}
```

### Retrieve, Update, Delete Staff Member
**Endpoint:** `/staff/{staff_id}/`  
**Methods:** GET, PUT, DELETE  
**Description:** Retrieve, update, or delete a specific staff member.

### Get Staff Expense History
**Endpoint:** `/expense_history/{staff_id}/`  
**Method:** GET  
**Description:** Get the expense history for a specific staff member.

### Generate Monthly Report for Staff
**Endpoint:** `/monthly-report/{staff_id}/{year}/{month}/`  
**Method:** GET  
**Description:** Generate a monthly report for a specific staff member.

### Create Staff Attendance
**Endpoint:** `/staff/attendance/`  
**Method:** POST  
**Description:** Create attendance records for staff.  
**JSON Data:**
```json
{
  "date": "2023-12-18",
  "attendances": [
    {
      "staff_id": 1,
      "in_time": "09:00:00",
      "out_time": "17:00:00",
      "status": "present"
    },
    // Additional attendance entries
  ]
}
```

### Get Staff Attendance List
**Endpoint:** `/staff/attendance/{date}/`  
**Method:** GET  
**Description:** Get the list of staff with their attendance details for a specific date.

## Expense

### List Expenses
**Endpoint:** `/expenses/`  
**Method:** GET  
**Description:** Retrieve a list of all expenses.

### Create Expense
**Endpoint:** `/expenses/`  
**Method:** POST  
**Description:** Create a new expense entry.  
**JSON Data:**
```json
{
  "staff": 1,
  "account": 1,
  "month": "1",
  "year": 2023,
  "description": "Office Supplies",
  "amount": 100.50,
  "expense_category": 1
}
```

### Retrieve, Update, Delete Expense
**Endpoint:** `/expenses/{expense_id}/`  
**Methods:** GET, PUT, DELETE  
**Description:** Retrieve, update, or delete a specific expense entry.

### List Expense Categories
**Endpoint:** `/expense-categories/`  
**Method:** GET  
**Description:** Retrieve a list of all expense categories.

### List Expense Sub-Categories
**Endpoint:** `/expense-sub-categories/`  
**Method:** GET  
**Description:** Retrieve a list of all expense sub-categories.

## Salary

### Create Salary
**Endpoint:** `/create_salary/`  
**Method:** POST  
**Description:** Create or update salary information for staff.  
**JSON Data:**
```json
{
  "month": 1,
  "year": 2023,
  "salaries": [
    {
      "staff_id": 1,
      "amount": 5000.00
    },
    // Additional salary entries
  ]
}
```

### Get Salary Report
**Endpoint:** `/salary_report/{month}/{year}/`  
**Method:** GET  
**Description:** Get the salary report for all staff members for a specific month and year.

## Miscellaneous

### Get Expense History for a Staff Member
**Endpoint:** `/expense_history/{staff_id}/`  
**Method:** GET  
**Description:** Get the detailed expense history for a specific staff member.

---

Feel free to use the provided API endpoints to manage and retrieve information related to departments, designations, staff, expenses, and salaries. If you have any questions or issues, please refer to the API documentation or contact the system administrator.

*Note: Replace `{department_id}`, `{designation_id}`, `{staff_id}`, `{expense_id}`, `{month}`, `{year}`, and `{date}` with the actual IDs or values when making API requests.*