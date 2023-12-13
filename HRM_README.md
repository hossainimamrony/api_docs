
# HRM API Documentation

## Overview

Welcome to the API documentation for [HRM]. This API provides a set of endpoints to manage departments, designations, staff members, expenses, and more. It also offers features like generating salary reports and viewing expense histories.

## Base URL

The base URL for all API endpoints is:

```
https://api.yourdomain.com/api/hrm/
```


## Departments

### List and Create Departments

- **Endpoint:** `/departments/`
- **Method:** `GET` (List all departments) / `POST` (Create a new department)
- **Parameters:**
  - None (for GET)
  - JSON data (for POST)

#### Sample GET Response

```json
[
  {
    "id": 1,
    "name": "Engineering"
  },
  {
    "id": 2,
    "name": "Marketing"
  }
  // ... (other departments)
]
```

#### Sample POST Request

```http
POST /departments/

{
  "name": "Finance"
}
```

### Retrieve, Update, and Delete Department

- **Endpoint:** `/departments/{department_id}/`
- **Method:** `GET` (Retrieve department details) / `PUT` (Update department details) / `DELETE` (Delete a department)
- **Parameters:**
 

  - `{department_id}`: Department ID (integer)

#### Sample GET Response

```json
{
  "id": 1,
  "name": "Engineering"
}
```

#### Sample PUT Request

```http
PUT /departments/1/

{
  "name": "Software Engineering"
}
```

#### Sample DELETE Request

```http
DELETE /departments/1/
```

## Designations

### List and Create Designations

- **Endpoint:** `/designations/`
- **Method:** `GET` (List all designations) / `POST` (Create a new designation)
- **Parameters:**
  - None (for GET)
  - JSON data (for POST)

#### Sample GET Response

```json
[
  {
    "id": 1,
    "name": "Software Engineer"
  },
  {
    "id": 2,
    "name": "Marketing Specialist"
  }
  // ... (other designations)
]
```

#### Sample POST Request

```http
POST /designations/

{
  "name": "Senior Software Engineer"
}
```

### Retrieve, Update, and Delete Designation

- **Endpoint:** `/designations/{designation_id}/`
- **Method:** `GET` (Retrieve designation details) / `PUT` (Update designation details) / `DELETE` (Delete a designation)
- **Parameters:**
  - `{designation_id}`: Designation ID (integer)

#### Sample GET Response

```json
{
  "id": 1,
  "name": "Software Engineer"
}
```

#### Sample PUT Request

```http
PUT /designations/1/

{
  "name": "Lead Software Engineer"
}
```

#### Sample DELETE Request

```http
DELETE /designations/1/
```

## Staff Members

### List and Create Staff Members

- **Endpoint:** `/staff/`
- **Method:** `GET` (List all staff members) / `POST` (Create a new staff member)
- **Parameters:**
  - None (for GET)
  - JSON data (for POST)

#### Sample GET Response

```json
[
  {
    "id": 1,
    "name": "John Doe",
    // ... (other staff details)
  },
  {
    "id": 2,
    "name": "Jane Doe",
    // ... (other staff details)
  }
  // ... (other staff members)
]
```

#### Sample POST Request

```http
POST /staff/

{
  "name": "Alice",
  // ... (other staff details)
}
```

### Retrieve, Update, and Delete Staff Member

- **Endpoint:** `/staff/{staff_id}/`
- **Method:** `GET` (Retrieve staff member details) / `PUT` (Update staff member details) / `DELETE` (Delete a staff member)
- **Parameters:**
  - `{staff_id}`: Staff Member ID (integer)

#### Sample GET Response

```json
{
  "id": 1,
  "name": "John Doe",
  // ... (other staff details)
}
```

#### Sample PUT Request

```http
PUT /staff/1/

{
  "name": "John Smith",
  // ... (other updated staff details)
}
```

#### Sample DELETE Request

```http
DELETE /staff/1/
```

## Expenses

### List and Create Expenses

- **Endpoint:** `/expenses/`
- **Method:** `GET` (List all expenses) / `POST` (Create a new expense)
- **Parameters:**
  - None (for GET)
  - JSON data (for POST)

#### Sample GET Response

```json
[
  {
    "id": 1,
    "description": "Office Supplies",
    // ... (other expense details)
  },
  {
    "id": 2,
    "description": "Travel Expenses",
    // ... (other expense details)
  }
  // ... (other expenses)
]
```

#### Sample POST Request

```http
POST /expenses/

{
  "description": "Meeting Expenses",
  // ... (other expense details)
}
```

### Retrieve, Update, and Delete Expense

- **Endpoint:** `/expenses/{expense_id}/`
- **Method:** `GET` (Retrieve expense details) / `PUT` (Update expense details) / `DELETE` (Delete an expense)
- **Parameters:**
  - `{expense_id}`: Expense ID (integer)

#### Sample GET Response

```json
{
  "id": 1,
  "description": "Office Supplies",
  // ... (other expense details)
}
```

#### Sample PUT Request

```http
PUT /expenses/1/

{
  "description": "New Office Supplies",
  // ... (other updated expense details)
}
```

#### Sample DELETE Request

```http
DELETE /expenses/1/
```

## Expense Categories

### List and Create Expense Categories

- **Endpoint:** `/expense-categories/`
- **Method:** `GET` (List all expense categories) / `POST` (Create a new expense category)
- **Parameters:**
  - None (for GET)
  - JSON data (for POST)

#### Sample GET Response

```json
[
  {
    "id": 1,
    "name": "Office Supplies"
  },
  {
    "id": 2,
    "name": "Travel"
  }
  // ... (other expense categories)
]
```

#### Sample POST Request

```http
POST /expense-categories/

{
  "name": "Meals"
}
```

### Retrieve, Update, and Delete Expense Category

- **Endpoint:** `/expense-categories/{category_id}/`
- **Method:** `GET` (Retrieve expense category details) / `PUT` (Update expense category details) / `DELETE` (Delete an expense category)
- **Parameters:**
  - `{category_id}`: Expense Category ID (integer)

#### Sample GET Response

```json
{
  "id": 1,
  "name": "Office Supplies"
}
```

#### Sample PUT Request

```http
PUT /expense-categories/1/

{
  "name": "Office Equipment"
}
```

#### Sample DELETE Request

```http
DELETE /expense-categories/1/
```

## Expense Sub-Categories

### List and Create Expense Sub-Categories

- **Endpoint:** `/expense-sub-categories/`
- **Method:** `GET` (List all expense sub-categories) / `POST` (Create a new expense sub-category)
- **Parameters:**
  - None (for GET)
  - JSON data (for POST)

#### Sample GET Response

```json
[
  {
    "id": 1,
    "name": "Pens",
    "expenseCategory": 1
  },
  {
    "id": 2,
    "name": "Airfare",
    "expenseCategory": 2
  }
  // ... (other expense sub-categories)
]
```

#### Sample POST Request

```http
POST /expense-sub-categories/

{
  "name": "Paper",
  "expenseCategory": 1
}
```

### Retrieve, Update, and Delete Expense Sub-Category

- **Endpoint:** `/expense-sub-categories/{sub_category_id}/`
- **Method:** `GET` (Retrieve expense sub-category details) / `PUT` (Update expense sub-category details) / `DELETE`

` /expense-sub-categories/{sub_category_id}/`


- **Parameters:**
  - `{sub_category_id}`: Expense Sub-Category ID (integer)

#### Sample GET Response

```json
{
  "id": 1,
  "name": "Pens",
  "expenseCategory": 1
}
```

#### Sample PUT Request

```http
PUT /expense-sub-categories/1/

{
  "name": "Ballpoint Pens",
  "expenseCategory": 1
}
```

#### Sample DELETE Request

```http
DELETE /expense-sub-categories/1/
```

## Expense History

### Get Expense History for a Staff Member

- **Endpoint:** `/expense_history/{staff_id}/`
- **Method:** `GET`
- **Parameters:**
  - `{staff_id}`: Staff Member ID (integer)
  - `start_date` (optional): Start date in YYYY-MM-DD format
  - `end_date` (optional): End date in YYYY-MM-DD format

#### Sample GET Response

```json
[
  {
    "staff_name": "John Doe",
    "overall_total_payment": 1200.50,
    "monthly_details": [
      {
        "month": "01",
        "year": 2023,
        "monthly_payment": 500.00,
        "expenses": [
          {"description": "Office Supplies", "amount": 200.00},
          {"description": "Travel Expenses", "amount": 150.50}
          // ... (other expenses)
        ]
      },
      // ... (other months)
    ]
  }
]
```

## Salary

### Create Salary Entry

- **Endpoint:** `/create_salary/`
- **Method:** `POST`
- **Parameters:**
  - JSON data

#### Sample POST Request

```http
POST /create_salary/

{
  "month": 1,
  "year": 2023,
  "salaries": [
    {"staff_id": 1, "amount": 1500.00},
    {"staff_id": 2, "amount": 1200.00}
    // ... (other staff salaries)
  ]
}
```

#### Sample POST Response

```json
{
  "id": 1,
  "staff": 1,
  "month": 1,
  "year": 2023,
  "amount": 1500.00
}
```

### Get Salary Details for a Month and Year

- **Endpoint:** `/get_salary/{month}/{year}/`
- **Method:** `GET`
- **Parameters:**
  - `{month}`: Month (integer)
  - `{year}`: Year (integer)

#### Sample GET Response

```json
[
  {
    "id": 1,
    "staff": 1,
    "month": 1,
    "year": 2023,
    "amount": 1500.00
  },
  {
    "id": 2,
    "staff": 2,
    "month": 1,
    "year": 2023,
    "amount": 1200.00
  }
  // ... (other salary entries)
]
```

## Salary Report

### Generate Salary Report for a Month and Year

- **Endpoint:** `/salary_report/{month}/{year}/`
- **Method:** `GET`
- **Parameters:**
  - `{month}`: Month (integer)
  - `{year}`: Year (integer)

#### Sample GET Response

```json
{
  "reports": [
    {
      "staff_name": "John Doe",
      "salary_amount": 1500.00,
      "total_expense": 500.00,
      "will_get": 1000.00,
      "status": "Partial Paid"
    },
    // ... (other staff reports)
  ],
  "overall_sum": {
    "overall_salary_sum": 2700.00,
    "overall_payment_sum": 800.00,
    "overall_will_get_sum": 1900.00
  }
}
```

## Conclusion

This concludes the API documentation for [Your API Name]. If you have any further questions or need assistance, please refer to the [API Documentation](https://api.yourdomain.com/) or contact our support team at [support@techelementbd.com].

Thank you for using [HRM APP]!
