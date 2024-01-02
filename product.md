
## Brand

### List Brands

**Endpoint:** `/api/brands/`  
**Method:** GET  
**Description:** Retrieve a list of all brands.

**Query Parameters:**
- `brand_name` (string): Filter brands by name.

**Example Request:**
```bash
GET /api/brands/?brand_name=SearchKeyword
```

### Create Brand

**Endpoint:** `/api/brands/`  
**Method:** POST  
**Description:** Create a new brand.

**Required Fields:**
- `brand_name` (string): The name of the brand.
- `short_description` (text): A short description of the brand.

**JSON Data Example:**
```json
{
  "brand_name": "New Brand",
  "short_description": "A short description of the new brand."
}
```

### Retrieve Brand

**Endpoint:** `/api/brands/{brand_id}/`  
**Method:** GET  
**Description:** Retrieve details of a specific brand.

### Update Brand

**Endpoint:** `/api/brands/{brand_id}/`  
**Method:** PUT  
**Description:** Update details of a specific brand.

**Required Fields:**
- `brand_name` (string): The updated name of the brand.
- `short_description` (text): The updated short description of the brand.

**JSON Data Example:**
```json
{
  "brand_name": "Updated Brand",
  "short_description": "An updated short description."
}
```

### Delete Brand

**Endpoint:** `/api/brands/{brand_id}/`  
**Method:** DELETE  
**Description:** Delete a specific brand.

---

## Category

### List Categories

**Endpoint:** `/api/categories/`  
**Method:** GET  
**Description:** Retrieve a list of all categories.

**Query Parameters:**
- `category_name` (string): Filter categories by name.

**Example Request:**
```bash
GET /api/categories/?category_name=SearchKeyword
```

### Create Category

**Endpoint:** `/api/categories/`  
**Method:** POST  
**Description:** Create a new category.

**Required Fields:**
- `category_name` (string): The name of the category.
- `category_code` (string): The code assigned to the category.
- `description` (text): A description of the category.
- `brand` (integer): The ID of the associated brand.

**JSON Data Example:**
```json
{
  "category_name": "New Category",
  "category_code": "CAT001",
  "description": "A description of the new category.",
  "brand": 1
}
```

### Retrieve Category

**Endpoint:** `/api/categories/{category_id}/`  
**Method:** GET  
**Description:** Retrieve details of a specific category.

### Update Category

**Endpoint:** `/api/categories/{category_id}/`  
**Method:** PUT  
**Description:** Update details of a specific category.

**Required Fields:**
- `category_name` (string): The updated name of the category.
- `category_code` (string): The updated code assigned to the category.
- `description` (text): The updated description of the category.

**JSON Data Example:**
```json
{
  "category_name": "Updated Category",
  "category_code": "CAT002",
  "description": "An updated description."
}
```

### Delete Category

**Endpoint:** `/api/categories/{category_id}/`  
**Method:** DELETE  
**Description:** Delete a specific category.

---

## Subcategory

### List Subcategories

**Endpoint:** `/api/subcategories/`  
**Method:** GET  
**Description:** Retrieve a list of all subcategories.

**Query Parameters:**
- `subcategory_name` (string): Filter subcategories by name.

**Example Request:**
```bash
GET /api/subcategories/?subcategory_name=SearchKeyword
```

### Create Subcategory

**Endpoint:** `/api/subcategories/`  
**Method:** POST  
**Description:** Create a new subcategory.

**Required Fields:**
- `subcategory_name` (string): The name of the subcategory.
- `category` (integer): The ID of the associated category.

**JSON Data Example:**
```json
{
  "subcategory_name": "New Subcategory",
  "category": 1
}
```

### Retrieve Subcategory

**Endpoint:** `/api/subcategories/{subcategory_id}/`  
**Method:** GET  
**Description:** Retrieve details of a specific subcategory.

### Update Subcategory

**Endpoint:** `/api/subcategories/{subcategory_id}/`  
**Method:** PUT  
**Description:** Update details of a specific subcategory.

**Required Fields:**
- `subcategory_name` (string): The updated name of the subcategory.

**JSON Data Example:**
```json
{
  "subcategory_name": "Updated Subcategory"
}
```

### Delete Subcategory

**Endpoint:** `/api/subcategories/{subcategory_id}/`  
**Method:** DELETE  
**Description:** Delete a specific subcategory.

---

## Warranty

### List Warranties

**Endpoint:** `/api/warranties/`  
**Method:** GET  
**Description:** Retrieve a list of all warranties.

**Query Parameters:**
- `warranty_name` (string): Filter warranties by name.

**Example Request:**
```bash
GET /api/warranties/?warranty_name=SearchKeyword
```

### Create Warranty

**Endpoint:** `/api/warranties/`  
**Method:** POST  
**Description:** Create a new warranty.

**Required Fields:**
- `warranty_name` (string): The name of the warranty.
- `warranty_description` (text): A description of the warranty.
- `warranty_duration` (integer): The duration of the warranty.
- `warranty_duration_type` (integer): Choose from available duration types.

**JSON Data Example:**
```json
{
  "warranty_name": "New Warranty",
  "warranty_description": "A description of the new warranty.",
  "warranty_duration": 2,
  "warranty_duration_type": 1
}
```

### Retrieve Warranty

**Endpoint:** `/api/warranties/{warranty_id}/`  
**Method:** GET  
**Description:** Retrieve details of a specific warranty.

### Update Warranty

**Endpoint:** `/api/warranties/{warranty_id}/`  
**Method:** PUT  
**Description:** Update details of a specific warranty.

**Required Fields:**
- `warranty_name` (string): The updated name of the warranty.
- `warranty_description` (text): The updated description of the warranty.
- `warranty_duration` (integer): The updated duration of the warranty.

**JSON Data Example:**
```json


{
  "warranty_name": "Updated Warranty",
  "warranty_description": "An updated description.",
  "warranty_duration": 3
}
```

### Delete Warranty

**Endpoint:** `/api/warranties/{warranty_id}/`  
**Method:** DELETE  
**Description:** Delete a specific warranty.



## Stock API Documentation

### List Opening Stocks
- **URL:** `GET /api/openingstocks/`
- **Example:** `https://your-api-domain.com/api/openingstocks/`

### Get Opening Stock Details
- **URL:** `GET /api/openingstocks/<int:pk>/`
- **Example:** `https://your-api-domain.com/api/openingstocks/1/`

### Create Opening Stock
- **URL:** `POST /api/openingstocks/`
- **Example:** `https://your-api-domain.com/api/openingstocks/`
- **Request Body:**
  ```json
  {
    "sku": "XYZ789",
    "location": "Warehouse B",
    "quantity": 50,
    "unit_cost_before_tax": 8.75,
    "lot_number": "LOT002",
    "expiry_date": "2023-10-15",
    "product": 1
  }
  ```
- **Parameters:**
  - **sku** (string, required): Stock Keeping Unit.
  - **location** (string): Warehouse location.
  - **quantity** (integer): Quantity of the product.
  - **unit_cost_before_tax** (decimal): Cost per unit before tax.
  - **lot_number** (string): Lot number for tracking.
  - **expiry_date** (date): Expiry date of the product.
  - **product** (Id): It take Product  `id`.
