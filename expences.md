
# Expense Management API

Welcome to the Expense Management API documentation! This guide provides detailed information on how to interact with the API for managing expenses. The API is built using Django and Django REST framework.

## Table of Contents

1. [Introduction](#introduction)
2. [Base URL](#base-url)
3. [Expense Categories](#expense-categories)
    - [List and Create Expense Categories](#list-and-create-expense-categories)
    - [Retrieve, Update, and Delete Expense Categories](#retrieve-update-and-delete-expense-categories)
4. [Expense Subcategories](#expense-subcategories)
    - [List and Create Expense Subcategories](#list-and-create-expense-subcategories)
    - [Retrieve, Update, and Delete Expense Subcategories](#retrieve-update-and-delete-expense-subcategories)
5. [Expenses](#expenses)
    - [List and Create Expenses](#list-and-create-expenses)
    - [Retrieve, Update, and Delete Expenses](#retrieve-update-and-delete-expenses)
6. [Payments](#payments)
    - [Retrieve, Update, and Delete Payments](#retrieve-update-and-delete-payments)
7. [Expense Filtering API](#expense-filtering-api)
    - [Filtering Expenses](#filtering-expenses)
8. [Conclusion](#conclusion)

## Introduction <a name="introduction"></a>

The Expense Management API allows you to manage expenses, including categories, subcategories, individual expenses, and payments associated with expenses. This documentation provides a comprehensive guide to help you integrate with the API seamlessly.

## Base URL <a name="base-url"></a>

All API requests should be made to the following base URL:

```
https://your-expense-api.com/api/v1/
```

## Expense Categories <a name="expense-categories"></a>

Expense categories are used to classify and organize expenses into different groups. This section covers CRUD operations on expense categories.

### List and Create Expense Categories <a name="list-and-create-expense-categories"></a>

#### Endpoint

```
GET /expense-categories/
POST /expense-categories/
```

#### Description

- **GET:** Retrieve a list of all expense categories.
- **POST:** Create a new expense category.

#### Parameters

- None for GET.
- For POST, provide `category_name` and `category_code`.

#### Example

```json
{
  "category_name": "Travel",
  "category_code": "TRV"
}
```

### Retrieve, Update, and Delete Expense Categories <a name="retrieve-update-and-delete-expense-categories"></a>

#### Endpoint

```
GET /expense-categories/{category_id}/
PUT /expense-categories/{category_id}/
DELETE /expense-categories/{category_id}/
```

#### Description

- **GET:** Retrieve details of a specific expense category.
- **PUT:** Update the details of a specific expense category.
- **DELETE:** Delete a specific expense category.

#### Parameters

- `{category_id}`: The unique identifier of the expense category.

#### Example

- **PUT:**

```json
{
  "category_name": "New Travel Name"
}
```

## Expense Subcategories <a name="expense-subcategories"></a>

Expense subcategories further classify expenses within a category. This section covers CRUD operations on expense subcategories.

### List and Create Expense Subcategories <a name="list-and-create-expense-subcategories"></a>

#### Endpoint

```
GET /expense-subcategories/
POST /expense-subcategories/
```

#### Description

- **GET:** Retrieve a list of all expense subcategories.
- **POST:** Create a new expense subcategory.

#### Parameters

- None for GET.
- For POST, provide `subcategory_name`.

#### Example

```json
{
  "subcategory_name": "Flight"
}
```

### Retrieve, Update, and Delete Expense Subcategories <a name="retrieve-update-and-delete-expense-subcategories"></a>

#### Endpoint

```
GET /expense-subcategories/{subcategory_id}/
PUT /expense-subcategories/{subcategory_id}/
DELETE /expense-subcategories/{subcategory_id}/
```

#### Description

- **GET:** Retrieve details of a specific expense subcategory.
- **PUT:** Update the details of a specific expense subcategory.
- **DELETE:** Delete a specific expense subcategory.

#### Parameters

- `{subcategory_id}`: The unique identifier of the expense subcategory.

#### Example

- **PUT:**

```json
{
  "subcategory_name": "New Flight Name"
}
```

## Expenses <a name="expenses"></a>

Expenses represent individual financial transactions. This section covers CRUD operations on expenses.

### List and Create Expenses <a name="list-and-create-expenses"></a>

#### Endpoint

```
GET /add-expenses/
POST /add-expenses/
```

#### Description

- **GET:** Retrieve a list of all expenses with optional filtering parameters.
- **POST:** Create a new expense.

#### Parameters

- Various parameters are available for filtering, such as `business_location`, `expense_for`, `contact`, `expense_category`, `sub_category`, `date_range`, and `payment_status`.

#### Example

- **POST:**

```json
{
  "reference_no": "REF-123",
  "date": "2023-01-01T12:00:00Z",
  "expense_for": 1,
  "total_amount": 100.00,
  "payments": [
    {
      "amount": 50.00,
      "date": "2023-01-01T12:00:00Z",
      "method": "card"
    },
    {
      "amount": 50.00,
      "date": "2023-01-02T12:00:00Z",
      "method": "cash"
    }
  ]
}
```

### Retrieve, Update, and Delete Expenses <a name="retrieve-update-and-delete-expenses"></a>

#### Endpoint

```
GET /add-expenses/{expense_id}/
PUT /add-expenses/{expense_id}/
DELETE /add-expenses/{expense_id}/
```

#### Description



- **GET:** Retrieve details of a specific expense.
- **PUT:** Update the details of a specific expense.
- **DELETE:** Delete a specific expense.

#### Parameters

- `{expense_id}`: The unique identifier of the expense.

#### Example

- **PUT:**

```json
{
  "reference_no": "REF-124"
}
```

## Payments <a name="payments"></a>

Payments represent financial transactions associated with expenses. This section covers CRUD operations on payments.

### Retrieve, Update, and Delete Payments <a name="retrieve-update-and-delete-payments"></a>

#### Endpoint

```
GET /payments/{payment_id}/
PUT /payments/{payment_id}/
DELETE /payments/{payment_id}/
```

#### Description

- **GET:** Retrieve details of a specific payment.
- **PUT:** Update the details of a specific payment.
- **DELETE:** Delete a specific payment.

#### Parameters

- `{payment_id}`: The unique identifier of the payment.

#### Example

- **PUT:**

```json
{
  "amount": 60.00
}
```

## Expense Filtering API <a name="expense-filtering-api"></a>

The Expense Filtering API provides additional endpoints for filtering expenses based on various criteria.

### Filtering Expenses <a name="filtering-expenses"></a>

#### Endpoint

```
GET /add-expenses/filter/
```

#### Description

Retrieve a filtered list of expenses based on parameters such as `business_location`, `expense_for`, `contact`, `expense_category`, `sub_category`, `date_range`, and `payment_status`.

#### Parameters

- Various parameters are available for filtering, similar to the `/add-expenses/` endpoint.

#### Example

```
GET /add-expenses/filter/?business_location=Office&date_range=this_month&payment_status=due
```

## Conclusion <a name="conclusion"></a>

Congratulations! You've reached the end of the Expense Management API documentation. This guide should help you seamlessly integrate and interact with the API for efficient expense management. If you have any questions or need further assistance, please refer to the [contact information](#contact-information) provided.

Happy coding!