
## Purchase API

### 1. Get Purchase Details
- **URL:** `/purchaseapid/{purchase_id}`
- **Method:** `GET`
- **Description:** Retrieve details of a specific purchase.
- **Parameters:** `{purchase_id}` - ID of the purchase to retrieve.

### 2. Create a Purchase
- **URL:** `/purchaseadd/`
- **Method:** `POST`
- **Description:** Create a new purchase entry.
- **Parameters:**
  - `Location` (int): Location ID.
  - `Supplier` (int): Supplier ID.
  - `Purchase_Status` (str): Purchase status (e.g., 'Due').
  - `Payment_Status` (str): Payment status (e.g., 'Due').
  - `Grand_Total` (float): Total purchase amount.
  - `Payment_Due` (float): Due payment amount.
  - `Added_By` (str): User adding the purchase.

**Example JSON Data:**
```json
{
  "Location": 1,
  "Supplier": 3,
  "Purchase_Status": "Due",
  "Payment_Status": "Due",
  "Grand_Total": 1500.50,
  "Payment_Due": 1200.00,
  "Added_By": "JohnDoe"
}
```

## Add Purchase API

### 1. Get Add Purchase Details
- **URL:** `/addpurchaseapid/{purchase_id}`
- **Method:** `GET`
- **Description:** Retrieve details of a specific additional purchase.

### 2. Create an Additional Purchase
- **URL:** `/addpurchaseadd/`
- **Method:** `POST`
- **Description:** Create a new additional purchase entry.
- **Parameters:**
  - `Supplier` (int): Supplier ID.
  - `Reference_No` (str): Reference number for the purchase.
  - `Purchase_Date` (datetime): Date of the purchase.
  - `Purchase_Status` (str): Purchase status (Possible values: 'Due', 'Recieved').
  - `Address` (str): Address for the purchase.
  - `Business_Location` (int): Business location ID.
  - `Pay_Term` (str): Payment term (Possible values: 'Select', 'Daily', 'Weekly', 'Half of Month', 'Monthly', 'Half of Year', 'Yearly').
  - `Attached_Document` (file): Attached document for the purchase.
  - `Discount_Type` (str): Discount type (Possible values: 'Please Select', 'Percentage', 'Fixed').
  - `Discount_Amount` (float): Discount amount.
  - `Purchase_Tax` (float): Purchase tax amount.
  - `Additional_Notes` (str): Additional notes for the purchase.
  - `Shipping_Details` (str): Shipping details for the purchase.
  - `Additional_Shipping_Charges` (float): Additional shipping charges.
  - `Addition_expense` (int): Additional expense ID.
  - `Amount` (float): Purchase amount.
  - `Paid_On` (datetime): Date of payment.
  - `Payment_Method` (str): Payment method (Possible values: 'None', 'Cash', 'Check', 'Bank-Card', 'Bkash', 'Nagad', 'Upay').
  - `Payment_Account` (int): Payment account ID.
  - `Payment_Note` (str): Notes related to payment.

**Example JSON Data:**
```json
{
  "Supplier": 3,
  "Reference_No": "REF123",
  "Purchase_Date": "2023-01-01T12:00:00Z",
  "Purchase_Status": "Due",
  "Address": "123 Main St",
  "Business_Location": 1,
  "Pay_Term": "Weekly",
  "Attached_Document": [File Object],
  "Discount_Type": "Percentage",
  "Discount_Amount": 10.00,
  "Purchase_Tax": 5.00,
  "Additional_Notes": "Special instructions",
  "Shipping_Details": "Express Shipping",
  "Additional_Shipping_Charges": 15.00,
  "Addition_expense": 2,
  "Amount": 1200.00,
  "Paid_On": "2023-01-07T12:00:00Z",
  "Payment_Method": "Bank-Card",
  "Payment_Account": 1,
  "Payment_Note": "Payment received on time"
}
```

## List Purchase Return API

### 1. Get List Purchase Return Details
- **URL:** `/listpurchasereturnapid/{return_id}`
- **Method:** `GET`
- **Description:** Retrieve details of a specific purchase return.

### 2. Create a List Purchase Return
- **URL:** `/listpurchasereturnadd/`
- **Method:** `POST`
- **Description:** Create a new purchase return entry.
- **Parameters:**
  - `Reference_No` (str): Reference number for the return.
  - `Location` (int): Location ID.
  - `Supplier` (int): Supplier ID.
  - `Payment_Status` (str): Payment status (Possible values: 'Due', 'Partial', 'Paid').
  - `Grand_Total` (float): Total return amount.
  - `Payment_Due` (float): Due payment amount.

**Example JSON Data:**
```json
{
  "Reference_No": "RET123",
  "Location": 1,
  "Supplier": 3,
  "Payment_Status": "Due",
  "Grand_Total": 500.00,
  "Payment_Due": 400.00
}
```

## Additional Expense API

### 1. Get Additional Expense Details
- **URL:** `/expenseapid/{expense_id}`
- **Method:** `GET`
- **Description:** Retrieve details of a specific additional expense.

### 2. Create an Additional Expense
- **URL:** `/expenseaddandsearch/`
- **Method:** `POST`
- **Description:** Create a new additional expense entry.
- **Parameters:**
  - `Expense_Name` (str): Name of the expense.
  - `Amount` (float): Expense amount.

**Example JSON Data:**
```json
{
  "Expense_Name": "Travel Expense",
  "Amount": 50.00
}
```

## Add Quotation API

### 1. Get Add Quotation Details
- **URL:** `/addquotationapid/{quotation_id}`
- **Method:** `GET`
- **Description:** Retrieve details of a specific quotation.

### 2. Create an Add Quotation
- **URL:** `/addquotationadd/`
- **Method:** `POST`
- **Description:** Create a new quotation entry.
- **Parameters:**
  - `Location` (int): Location ID.
  - `Customer` (int): Customer ID.
  - `Pay_Term` (str): Payment term (Possible values: 'Select', 'Daily', 'Weekly', 'Half of Month', 'Monthly', 'Half of Year', 'Yearly').
  - `Commss

ion_Agent` (int): Commission agent ID.
  - `Sale_Date` (datetime): Date of sale.
  - `Billing_Address` (str): Billing address.
  - `Shipping_Address` (str): Shipping address.
  - `Invoice_Number` (str): Invoice number.
  - `Attach_Document` (file): Attached document for the quotation.
  - `Discount_Type` (str): Discount type (Possible values: 'Please Select', 'Percentage', 'Fixed').
  - `Discount_Amount` (float): Discount amount.
  - `Order_Tax` (float): Order tax amount.
  - `Sell_Note` (str): Notes related to the sale.
  - `Shipping_Details` (str): Shipping details for the sale.
  - `Shipping_Addresss` (str): Shipping address for the sale.
  - `Shipping_Charges` (float): Shipping charges for the sale.
  - `Shipping_Status` (str): Shipping status (Possible values: 'Select', 'Ordered', 'Packed', 'Shipped', 'Delivered', 'Cancel').
  - `Shipping_Document` (file): Shipping document for the sale.

**Example JSON Data:**
```json
{
  "Location": 1,
  "Customer": 5,
  "Pay_Term": "Weekly",
  "Commssion_Agent": 2,
  "Sale_Date": "2023-01-15T12:00:00Z",
  "Billing_Address": "456 Main St",
  "Shipping_Address": "789 Side St",
  "Invoice_Number": "INV456",
  "Attach_Document": [File Object],
  "Discount_Type": "Fixed",
  "Discount_Amount": 20.00,
  "Order_Tax": 8.00,
  "Sell_Note": "Special instructions",
  "Shipping_Details": "Express Shipping",
  "Shipping_Addresss": "789 Side St",
  "Shipping_Charges": 12.00,
  "Shipping_Status": "Shipped",
  "Shipping_Document": [File Object]
}
```

Please feel free to reach out if you have any questions or need further clarification on any of the endpoints.