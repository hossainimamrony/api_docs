# Sales  API Documentation

## Introduction

Welcome to the Sales  API documentation. This guide will walk you through the available endpoints and their functionalities for seamless integration into your frontend application.

## Table of Contents


1. [Locations](#1-locations)
   - [Get All Locations](#11-get-all-locations)
   - [Get Location Details](#12-get-location-details)
   - [Create a New Location](#13-create-a-new-location)
   - [Update Location Details](#14-update-location-details)
   - [Delete a Location](#15-delete-a-location)
2. [Sales](#2-sales)
   - [Get All Sales](#21-get-all-sales)
   - [Get Sale Details](#22-get-sale-details)
   - [Create a New Sale](#23-create-a-new-sale)
   - [Update Sale Details](#24-update-sale-details)
   - [Delete a Sale](#25-delete-a-sale)
   - [Search and Filter Sales](#26-search-and-filter-sales)
3. [Drafts](#3-drafts)
   - [Get All Drafts](#31-get-all-drafts)
   - [Get Draft Details](#32-get-draft-details)
   - [Create a New Draft](#33-create-a-new-draft)
   - [Update Draft Details](#34-update-draft-details)
   - [Delete a Draft](#35-delete-a-draft)
   - [Search and Filter Drafts](#36-search-and-filter-drafts)
4. [Sell Returns](#4-sell-returns)
   - [Get All Sell Returns](#41-get-all-sell-returns)
   - [Get Sell Return Details](#42-get-sell-return-details)
   - [Create a New Sell Return](#43-create-a-new-sell-return)
   - [Update Sell Return Details](#44-update-sell-return-details)
   - [Delete a Sell Return](#45-delete-a-sell-return)
   - [Search and Filter Sell Returns](#46-search-and-filter-sell-returns)
5. [Shipments](#5-shipments)
   - [Get All Shipments](#51-get-all-shipments)
   - [Get Shipment Details](#52-get-shipment-details)
   - [Create a New Shipment](#53-create-a-new-shipment)
   - [Update Shipment Details](#54-update-shipment-details)
   - [Delete a Shipment](#55-delete-a-shipment)
   - [Search and Filter Shipments](#56-search-and-filter-shipments)
6. [Discounts](#6-discounts)
   - [Get All Discounts](#61-get-all-discounts)
   - [Get Discount Details](#62-get-discount-details)
   - [Create a New Discount](#63-create-a-new-discount)
   - [Update Discount Details](#64-update-discount-details)
   - [Delete a Discount](#65-delete-a-discount)
   - [Search and Filter Discounts](#66-search-and-filter-discounts)





# 1. Locations

### 1.1 Get All Locations

- **URL:** `/locationapil/`
- **Method:** `GET`
- **Description:** Retrieve a list of all locations.

### 1.2 Get Location Details

- **URL:** `/locationapid/{pk}`
- **Method:** `GET`
- **Description:** Retrieve details of a specific location by providing its primary key (`pk`).
- **Note:** Please refrain from adding a trailing `/` after the primary key (`pk`).
  
### 1.3 Create a New Location

- **URL:** `/locationapil/`
- **Method:** `POST`
- **Description:** Create a new location.

#### Sample Request Body

```json
{
  "Location": "New Location"
}
```

#### Parameters

- `Location` (string, required): The name of the new location.

### 1.4 Update Location Details

- **URL:** `/locationapid/{pk}`
- **Method:** `PUT`
- **Description:** Update details of a specific location by providing its primary key (`pk`).

#### Sample Request Body

```json
{
  "Location": "Updated Location Name"
}
```

#### Parameters

- `Location` (string, required): The updated name of the location.

### 1.5 Delete a Location

- **URL:** `/locationapid/{pk}`
- **Method:** `DELETE`
- **Description:** Delete a location by providing its primary key (`pk`).

# 2. Sales

### 2.1 Get All Sales

- **URL:** `/allsalesadd/`
- **Method:** `GET`
- **Description:** Retrieve a list of all sales.

### 2.2 Get Sale Details

- **URL:** `/allsalesapid/{pk}`
- **Method:** `GET`
- **Description:** Retrieve details of a specific sale by providing its primary key (`pk`).
- **Note:** Please refrain from adding a trailing `/` after the primary key (`pk`).

### 2.3 Create a New Sale

- **URL:** `/allsalesadd/`
- **Method:** `POST`
- **Description:** Create a new sale

#### Sample Request Body

```json
{
  "Invoice_No": "INV123",
  "Customer_Name": 1,
  "Contact_Number": "1234567890",
  "Location": 1,
  "Payment_Status": "None",
  "Payment_Method": "Cash",
  "Total_Amount": "150.00",
  "Total_Paid": "100.00",
  "Sell_Due": "50.00",
  "Shipping_Status": "None",
  "Shipping_Address": "123 Street, City",
  "Total_Items": "5",
  "Added_By": "John Doe"
}
```

#### Parameters

- `Invoice_No` (string, required): The invoice number for the sale.
- `Customer_Name` (integer, required): The ID of the customer associated with the sale.
- `Contact_Number` (string, required): The contact number for the sale.
- `Location` (integer, required): The ID of the location where the sale occurred.
- `Payment_Status` (string, required): The payment status of the sale (`None`, `Due`, `Partial`, or `Paid`).
- `Payment_Method` (string, required): The payment method used for the sale (`None`, `Cash`, `Check`, `Bank-Card`, `Bkash`, `Nagad`, `Upay`).
- `Total_Amount` (string, required): The total amount of the sale.
- `Total_Paid` (string, required): The total amount paid for the sale.
- `Sell_Due` (string, required): The remaining amount due for the sale.
- `Shipping_Status` (string, required): The shipping status of the sale (`None`, `Ordered`, `Pending`, `Paid`).
- `Shipping_Address` (string, required): The shipping address for the sale.
- `Total_Items` (string, required): The total number of items in the sale.
- `Added_By` (string, required): The name of the user who added the sale.

### 2.4 Update Sale Details

- **URL:** `/allsalesapid/{pk}`
- **Method:** `PUT`
- **Description:** Update details of a specific sale by providing its primary key (`pk`).

#### Sample Request Body

```json
{
  "Total_Paid": "120.00"
}
```

#### Parameters

- `Total_Paid` (string, required): The updated total amount paid for the sale.

### 2.5 Delete a Sale

- **URL:** `/allsalesapid/{pk}`
- **Method:** `DELETE`
- **Description:** Delete a sale by providing its primary key (`pk`).

### 2.6 Search and Filter Sales

- **URL:** `/allsalesdisplayfilter/?search=query`
- **Method:** `GET`
- **Description:** Search and filter sales. You can use the `search` parameter for search queries (only skip `customer` and `locations` field).

# 3. Drafts

### 3.1 Get All Drafts

- **URL:** `/listdraftadd/`
- **Method:** `GET`
- **Description:** Retrieve a list of all drafts.

### 3.2 Get Draft Details

- **URL:** `/listdraftapid/{pk}`
- **Method:** `GET`
- **Description:** Retrieve details of a specific draft by providing its primary key (`pk`).

### 3.3 Create a New Draft

- **URL:** `/listdraftadd/`
- **Method:** `POST`
- **Description:** Create a new draft.

#### Sample Request Body

```json
{
  "Reference_No": "REF123",
  "Customer_Name": 1,
  "Contact_Number": "1234567890",
  "Location": 1,
  "Total_Items": "3",
  "Added_By": "John Doe"
}
```

#### Parameters

- `Reference_No` (string, required): The reference number for the draft.
- `Customer_Name` (integer, required): The ID of the customer associated with the draft.
- `Contact_Number` (string, required): The contact number for the draft.
- `Location` (integer, required): The ID of the location where the draft is created.
- `Total_Items` (string, required): The total number of items in the draft.
- `Added_By` (string, required): The name of the user who added the draft.

### 3.4 Update Draft Details

- **URL:** `/listdraftapid/{pk}`
- **Method:** `PUT`
- **Description:** Update details of a specific draft by providing its primary key (`pk`).

#### Sample Request Body

```json
{
  "Total_Items": "5"
}
```

#### Parameters

- `Total_Items` (string, required): The updated total number of items in the draft.

### 3.5 Delete a Draft

- **URL:** `/listdraftapid/{pk}`
- **Method:** `DELETE`
- **Description:** Delete a draft by providing its primary key (`pk`).

### 3.6 Search and Filter Drafts

- **URL:** `/listdraftdisplayfilter/?search=query&ordering=field_name`
- **Method:** `GET`
- **Description:** Search and filter drafts. You can use the `search` parameter for search queries (only skip `customer` and `locations` field .



# 4. Sell Returns

### 4.1 Get All Sell Returns

- **URL:** `/listsellreturnadd/`
- **Method:** `GET`
- **Description:** Retrieve a list of all sell returns.

### 4.2 Get Sell Return Details

- **URL:** `/listsellreturnapid/{pk}`
- **Method:** `GET`
- **Description:** Retrieve details of a specific sell return by providing its primary key (`pk`).

### 4.3 Create a New Sell Return

- **URL:** `/listsellreturnadd/`
- **Method:** `POST`
- **Description:** Create a new sell return.

##### Sample Request Body

```json
{
  "Invoice_No": "INV123",
  "Parent_Sale": 1,
  "Customer_Name": 1,
  "Contact_Number": "1234567890",
  "Location": 1,
  "Payment_Status": "Due",
  "Total_Amount": "100.00",
  "Payment_Due": "25.00"
}
```

##### Parameters

- **Invoice_No (String):** The invoice number for the sell return.
- **Parent_Sale (Integer):** The primary key of the parent sale.
- **Customer_Name (Integer):** The primary key of the customer associated with the sell return.
- **Contact_Number (String):** The contact number of the customer.
- **Location (Integer):** The primary key of the location associated with the sell return.
- **Payment_Status (String):** The payment status of the sell return (choices: 'None', 'Due', 'Partial', 'Paid').
- **Total_Amount (String):** The total amount for the sell return.
- **Payment_Due (String):** The due amount for payment.

### 4.4 Update Sell Return Details

- **URL:** `/listsellreturnapid/{pk}`
- **Method:** `PUT`
- **Description:** Update details of a specific sell return by providing its primary key (`pk`).

##### Sample Request Body

```json
{
  "Payment_Due": "30.00"
}
```

##### Parameters

- **Payment_Due (String):** The updated due amount for payment.

### 4.5 Delete a Sell Return

- **URL:** `/listsellreturnapid/{pk}`
- **Method:** `DELETE`
- **Description:** Delete a sell return by providing its primary key (`pk`).

### 4.6 Search and Filter Sell Returns

- **URL:** `/listsellreturndisplayfilter/?search=query`
- **Method:** `GET`
- **Description:** Search and filter sell returns. You can use the `search` parameter for search queries.

# 5. Shipments

### 5.1 Get All Shipments

- **URL:** `/shipmentadd/`
- **Method:** `GET`
- **Description:** Retrieve a list of all shipments.

### 5.2 Get Shipment Details

- **URL:** `/shipmentapid/{pk}`
- **Method:** `GET`
- **Description:** Retrieve details of a specific shipment by providing its primary key (`pk`).

### 5.3 Create a New Shipment

- **URL:** `/shipmentadd/`
- **Method:** `POST`
- **Description:** Create a new shipment.

##### Sample Request Body

```json
{
  "Invoice_No": "INV123",
  "Customer_Name": 1,
  "Contact_Number": "1234567890",
  "Location": 1,
  "Shipping_Status": "Ordered",
  "Payment_Status": "None",
  "Service_Staff": "John Doe"
}
```

##### Parameters

- **Invoice_No (String):** The invoice number for the shipment.
- **Customer_Name (Integer):** The primary key of the customer associated with the shipment.
- **Contact_Number (String):** The contact number of the customer.
- **Location (Integer):** The primary key of the location associated with the shipment.
- **Shipping_Status (String):** The shipping status of the shipment (choices: 'None', 'Ordered', 'Pending').
- **Payment_Status (String):** The payment status of the shipment (choices: 'None', 'Due', 'Partial', 'Paid').
- **Service_Staff (String):** The staff member responsible for the service.

### 5.4 Update Shipment Details

- **URL:** `/shipmentapid/{pk}`
- **Method:** `PUT`
- **Description:** Update details of a specific shipment by providing its primary key (`pk`).

##### Sample Request Body

```json
{
  "Shipping_Status": "Pending"
}
```

##### Parameters

- **Shipping_Status (String):** The updated shipping status of the shipment.

### 5.5 Delete a Shipment

- **URL:** `/shipmentapid/{pk}`
- **Method:** `DELETE`
- **Description:** Delete a shipment by providing its primary key (`pk`).

### 5.6 Search and Filter Shipments

- **URL:** `/shipmentdisplayfilter/?search=query`
- **Method:** `GET`
- **Description:** Search and filter shipments. You can use the `search` parameter for search queries .

# 6. Discounts

### 6.1 Get All Discounts

- **URL:** `/discountadd/`
- **Method:** `GET`
- **Description:** Retrieve a list of all discounts.

### 6.2 Get Discount Details

- **URL:** `/discountapid/{pk}`
- **Method:** `GET`
- **Description:** Retrieve details of a specific discount by providing its primary key (`pk`).

### 6.3 Create a New Discount

- **URL:** `/discountadd/`
- **Method:** `POST`
- **Description:** Create a new discount.

##### Sample Request Body

```json
{
  "Name": 1,
  "Starts_At": "2023-01-01",
  "Ends_At": "2023-02-01",
  "Discount_Amount": "10.00",
  "Priority": "High",
  "Brand": "Brand Name",
  "Category": "Category Name",
  "Product": "Product Name",
  "Location": 1
}
```

##### Parameters

- **Name (Integer):** The primary key of the business name associated with the discount.
- **Starts_At (String):** The start date of the discount.
- **Ends_At (String):** The end date of the discount.
- **Discount_Amount (String):** The discount amount.
- **Priority (String):** The priority level of the discount.
- **Brand (String):** The brand associated with the discount.
- **Category (String):** The category associated with the discount.
- **Product (String):** The product associated with the discount.
- **Location (Integer):** The primary key of the location associated with the discount.

### 6.4 Update Discount Details

- **URL:** `/discountapid/{pk}`
- **Method:** `PUT`
- **Description:** Update details of a specific discount by providing its primary key (`pk`).

##### Sample Request Body

```json
{
  "Discount_Amount": "15.00"
}
```

##### Parameters

- **Discount_Amount (String):** The updated discount amount.

### 6.5 Delete a Discount

- **URL:** `/discountapid/{pk}`
- **Method:** `DELETE`
- **Description:** Delete a discount by providing its primary key (`pk`).

### 6.6 Search and Filter Discounts

- **URL:** `/discountdisplayfilter/?search=query`
- **Method:** `GET`
- **Description:** Search and filter discounts. You can use the `search` parameter for search queries.

---
