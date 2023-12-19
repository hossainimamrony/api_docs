# Expense API Documentation

## Introduction

Welcome to the Expense API documentation. This API is built using Django Rest Framework (DRF) and provides endpoints to manage expenses, payment details, expense categories, and subcategories.

# Expense API Documentation


## Expense Categories

### List and Create Expense Categories

**Endpoint:** `/expense-categories/`

- **Method:** `GET`
  
  Retrieves a list of all expense categories.

- **Method:** `POST`

  Creates a new expense category.

  **Request Body:**
  ```json
  {
    "category_name": "Category Name",
    "category_code": "Category Code",
    "subcategory": null
  }
  ```

  - `category_name` (string): The name of the expense category.
  - `category_code` (string): The code associated with the expense category.
  - `subcategory` (integer, optional): The ID of the associated subcategory. (Set to `null` if no subcategory)

### Retrieve, Update, and Delete Expense Category

**Endpoint:** `/expense-categories/<category_id>/`

- **Method:** `GET`
  
  Retrieves details of a specific expense category.

- **Method:** `PUT` or `PATCH`

  Updates details of a specific expense category.

  **Request Body:**
  ```json
  {
    "category_name": "Updated Category Name",
    "category_code": "Updated Category Code",
    "subcategory": 1
  }
  ```

- **Method:** `DELETE`

  Deletes a specific expense category.

## Expense Subcategories

### List and Create Expense Subcategories

**Endpoint:** `/expense-subcategories/`

- **Method:** `GET`
  
  Retrieves a list of all expense subcategories.

- **Method:** `POST`

  Creates a new expense subcategory.

  **Request Body:**
  ```json
  {
    "subcategory_name": "Subcategory Name"
  }
  ```

  - `subcategory_name` (string): The name of the expense subcategory.

### Retrieve, Update, and Delete Expense Subcategory

**Endpoint:** `/expense-subcategories/<subcategory_id>/`

- **Method:** `GET`
  
  Retrieves details of a specific expense subcategory.

- **Method:** `PUT` or `PATCH`

  Updates details of a specific expense subcategory.

  **Request Body:**
  ```json
  {
    "subcategory_name": "Updated Subcategory Name"
  }
  ```

- **Method:** `DELETE`

  Deletes a specific expense subcategory.

## Expenses

### List and Create Expenses

**Endpoint:** `/add-expenses/`

- **Method:** `GET`
  
  Retrieves a list of all expenses.

- **Method:** `POST`

  Creates a new expense.

  **Request Body:**
  ```json
  {
    "business_location": "Business Location",
    "reference_no": "Reference Number",
    "date": "2023-12-20T12:00:00Z",
    "expense_for": 1,
    "expense_for_contact": 1,
    "attached_document": null,
    "applicable_tax": 10.00,
    "total_amount": 100.00,
    "is_refund": false,
    "expense_note": "Expense Note",
    "is_recurring": false,
    "recurring_interval": "Months",
    "recurring_interval_value": 2,
    "number_of_receipts": 3,
    "payment_due": 30.00,
    "payment_status": "partial",
    "payments": [
      {
        "amount": 30.00,
        "date": "2023-12-20T12:00:00Z",
        "method": "card",
        "payment_account": "Card Account",
        "card_number": "1234567890123456",
        "card_holder_name": "John Doe",
        "card_transaction_no": "TX123",
        "card_type": "credit",
        "card_expiry_month": 12,
        "card_expiry_year": 2025,
        "card_security_code": "123",
        "cheque_no": null,
        "bank_account_no": null,
        "other": null,
        "payment_note": "Payment Note"
      }
    ]
  }
  ```

  - `business_location` (string): The location of the business.
  - `reference_no` (string): The reference number of the expense.
  - `date` (string): The date of the expense in ISO 8601 format.
  - `expense_for` (integer): The ID of the user for whom the expense is made.
  - `expense_for_contact` (integer): The ID of the contact associated with the expense.
  - `attached_document` (file, optional): The attached document for the expense.
  - `applicable_tax` (decimal, optional): The applicable tax for the expense.
  - `total_amount` (decimal): The total amount of the expense.
  - `is_refund` (boolean): Indicates whether the expense is a refund.
  - `expense_note` (string, optional): Additional notes for the expense.
  - `is_recurring` (boolean): Indicates whether the expense is recurring.
  - `recurring_interval` (string): The recurring interval ("Years", "Months", "Days").
  - `recurring_interval_value` (integer, optional): The value for the recurring interval.
  - `number_of_receipts` (integer, optional): The number of receipts associated with the expense.
  - `payment_due` (decimal): The amount due for the payment.
  - `payment_status` (string): The payment status ("paid", "due", "partial").
  - `payments` (array, optional): List of payments associated with the expense.

### Retrieve, Update, and Delete Expense

**Endpoint:** `/add-expenses/<expense_id>/`

- **Method:** `GET`
  
  Retrieves details of a specific expense.

- **Method:** `PUT` or `PATCH`

  Updates details of a specific expense.

  **Request Body:**
  ```json
  {
    "business_location": "Updated Business Location",
    "reference_no": "Updated Reference Number",
    "date": "2023-12-21T12:00:00Z",
    "expense_for": 2,
    "expense_for_contact": 2,
    "attached_document": null,
    "applicable_tax": 15.00,
    "total_amount": 150.00,
    "is_refund": true,
    "expense_note": "Updated Expense Note",
    "is_recurring": true,
    "recurring_interval": "Days",
    "recurring_interval_value": 3,
    "number_of_receipts": 5,
    "payment_due": 120.00,
    "payment_status": "due",
    "payments": [
      {
        "amount": 50.00,
        "date": "2023-12-21T12:00:00Z",
        "method": "cash",
        "payment_account": null,
        "card_number": null,
        "card_holder_name": null,
        "card_transaction_no": null,
        "card_type": null,
        "card_expiry_month": null,
        "card_expiry_year": null,
        "card_security_code": null,
        "cheque_no": null,
        "bank_account_no": null,
        "other": null,
        "payment_note": "Updated Payment Note"
      }
    ]
  }
  
  ```

- **Method:** `DELETE`

  Deletes a specific expense.

---

Feel free to use the provided examples as a reference when making requests to the API. If you have any questions or encounter issues, please refer to this documentation or contact the API administrator for assistance (RONY). 

Happy coding!
