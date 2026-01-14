### BUG-01 — Product can be created without required field `title`

**Endpoint:** POST /products/add  
**Severity:** Medium  
**Priority:** Medium  

**Description:**  
The API allows creating a product without providing the required `title` field.

**Steps to Reproduce:**
1. Send POST request to `/products/add`
2. Use a JSON body without `title`
   ```json
   {
     "price": 123,
     "description": "Product without title"
   }

  ```

**Expected Result:**
- API should return `400 Bad Request`
- Error message indicating missing required field title

**Actual Result:**
- API returns 201 Created
- Product is created successfully without title
**Result (Pass/Fail):**
- Fail
**Evidence:**
- Response saved in Postman
- Response saved in `/evidence/tc-p06-missing-title-response.json`

### BUG-02 — Product can be created with invalid price type

**Endpoint:** POST /products/add  
**Severity:** Medium  
**Priority:** Medium  

**Description:**  
The API allows creating a product with an invalid `price` value (string instead of number).

**Steps to Reproduce:**
1. Send POST request to `/products/add`
2. Use the following body:
   ```json
   {
     "title": "Invalid price product",
     "price": "abc",
     "description": "Price is a string"
   }

  ```
**Expected Result:**
- API should return `400 Bad Request`
- Error message indicating invalid price type  

**Actual Result:**
- API returns `201 Created`
- Product is created with price as a string
**Result (Pass/Fail):**
- Fail
**Evidence:**
- Response saved in Postman
- Response saved in `/evidence/tc-p07-invalid-price-response.json`
