# Staff Management API Documentation

## Overview

The Staff Management API provides endpoints for managing staff information, including details on staff members, expenses, salary, and attendance.

## Table of Contents

- [Department](#department)
  - [List Departments](#list-departments)
  - [Create Department](#create-department)
  - [Retrieve, Update, Delete Department](#retrieve-update-delete-department)

- [Designation](#designation)
  - [List Designations](#list-designations)
  - [Create Designation](#create-designation)
  - [Retrieve, Update, Delete Designation](#retrieve-update-delete-designation)

- [Staff](#staff)
  - [Create a New Staff Member](#create-a-new-staff-member)
  - [Get List of Staff Members](#get-list-of-staff-members)
  - [Get Staff Member Details](#get-staff-member-details)

- [Expense](#expense)
  - [List Expenses](#list-expenses)
  - [Create Expense](#create-expense)
  - [Retrieve, Update, Delete Expense](#retrieve-update-delete-expense)

- [Salary](#salary)
  - [Generate Salary Report](#generate-salary-report)
  - [Create Salary](#create-salary)

- [Attendance](#attendance)
  - [Create Staff Attendance](#create-staff-attendance)
  - [Get Staff Attendance](#get-staff-attendance)
  - [Get Staff Monthly Report](#get-staff-monthly-report)

---

## Department

### List Departments

**Endpoint:** `/departments/`  
**Method:** GET  
**Description:** Retrieve a list of all departments.

### Create Department

**Endpoint:** `/departments/`  
**Method:** POST  
**Description:** Create a new department.  
**JSON Data Example:**
```json
{
  "name": "Human Resources"
}
```

### Retrieve, Update, Delete Department

**Endpoint:** `/departments/{department_id}/`  
**Methods:** GET, PUT, DELETE  
**Description:** Retrieve, update, or delete a specific department.

---

## Designation

### List Designations

**Endpoint:** `/designations/`  
**Method:** GET  
**Description:** Retrieve a list of all designations.

### Create Designation

**Endpoint:** `/designations/`  
**Method:** POST  
**Description:** Create a new designation.  
**JSON Data Example:**
```json
{
  "name": "Software Engineer"
}
```

### Retrieve, Update, Delete Designation

**Endpoint:** `/designations/{designation_id}/`  
**Methods:** GET, PUT, DELETE  
**Description:** Retrieve, update, or delete a specific designation.

---

## Staff

### Create a New Staff Member

**Endpoint:** `/staff/`  
**Method:** POST  
**Description:** Create a new staff member.  
**JSON Data Example:**
```json
    {
        "name": "John Doe",
        "father_name": "Doe Sr.",
        "mother_name": "Jane Doe",
        "address": "123 Main St, Cityville",
        "permanent_address": "456 Park Ave, Townsville",
        "date_of_birth": "1990-01-01",
        "nationality": "Bangladeshi",
        "religion": "Islam",
        "marital_status": "Married",
        "voter_id": "1234567890",
        "birth_certificate": "BC123456",
        "blood_group": "A+",
        "gender": "Male",
        "mobile": "1234567890",
        "educational_qualification": "Bachelor's in Computer Science",
        "experience": "5 years",
        "staff_id": "S123",
        "photo": null,
        "staff_type": "Regular",
        "office_zone": "North",
        "joining_date": "2022-01-15",
        "job_exemption_date": null,
        "email": "john.doe@example.com",
        "mobile_occupation": "9876543210",
        "notes": "This is a note about John Doe.",
        "notes1": "Another note about John Doe.",
        "office_time_start": null,
        "office_time_end": null,
        "department": 1,
        "designation": null
    }
```

<sub>***To accurately calculate attendance status and total working hours, please ensure that both "office_time_start" and "office_end_time" are clearly specified in the document. These parameters are crucial for our system to determine accurate working durations. Thank you for your attention to this matter.***</sub>

### Get List of Staff Members

**Endpoint:** `/staff/`  
**Method:** GET  
**Description:** Retrieve a list of all staff members.

### Get Staff Member Details

**Endpoint:** `/staff/{staff_id}/`  
**Methods:** GET, PUT, DELETE  
**Description:** Retrieve, update, or delete a specific staff member.

---

## Expense

### List Expenses

**Endpoint:** `/expenses/`  
**Method:** GET  
**Description:** Retrieve a list of all expenses.

### Create Expense

**Endpoint:** `/expenses/`  
**Method:** POST  
**Description:** Create a new expense.  
**JSON Data Example:**
```json
        {
            "id": 7,
            "month": "10",
            "year": 2023,
            "description": "new update",
            "amount": "10000.00",
            "staff": 2,
            "account": 1, //this is id from Account sections
            "expense_category": null
        }
```

### Retrieve, Update, Delete Expense

**Endpoint:** `/expenses/{expense_id}/`  
**Methods:** GET, PUT, DELETE  
**Description:** Retrieve, update, or delete a specific expense.

---

## Salary

### Generate Salary Report

**Endpoint:** `/salary_report/{month}/{year}/`  
**Method:** GET  
**Description:** Generate a salary report for a specific month and year.<br>
**Example Url:** `/api/hrm/salary_report/1/2023/`<br>
<sub> ***If you need any additional details about the staff, you have to use the staff ID to retrieve that data. Refer to the staff section for instructions on how to do that.*** </sub>

### Create Salary

**Endpoint:** `/create_salary/`  
**Method:** POST  
**Description:** Create or update salary entries for staff members.  
**JSON Data Example:**
```json
{
  "month": 12,
  "year": 2023,
  "salaries": [
    {
      "staff_id": 1,
      "amount": 5000.0
    },
    // Additional salary entries
  ]
}
```

---

## Attendance

### Create Staff Attendance

**Endpoint:** `/staff/attendance/`  
**Method:** POST  
**Description:** Create attendance records for staff.  
**JSON Data Example:**
```json
{
  "date": "2023-01-01",
  "attendances": [
    {
      "staff_id": 1,
      "in_time": "09:00:00",
      "out_time": "17:00:00",
      "status": "present"
    },
    {
      "staff_id": 2,
      "in_time": "10:30:00",
      "out_time": "18:30:00",
      "status": "present"
    }
  ]
}

```

### Get Staff Attendance Report

**Endpoint:** `/staff/attendance/{date}/`  
**Method:** GET  
**Description:** Retrieve the attendance records for a specific date.<br>
**Example Url:** `/api/hrm/staff/attendance/2023-12-17/` <br>
<sub>***You will receive data exactly as shown in the posted information. If you need any additional details about the staff, you have to use the staff ID to retrieve that data. Refer to the staff section for instructions on how to do that.***</sub>



### Get Staff Monthly Report

**Endpoint:** `/staff/attendance/monthly_report/{staff_id}/{month}/{year}/`  
**Method:** GET  
**Description:** Generate the monthly attendance report for a specific staff member.<br>
**Example Url:** `/api/hrm/attendance/monthly-report/1/2021/2/`<br>
<sub>***if you need any total/or sum data of any value you can do it in forntend from the json data you will get from it.***</sub>

---

