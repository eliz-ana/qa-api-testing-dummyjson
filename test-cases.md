# Test Cases — DummyJSON API

- API type: Public REST API
- Data source: DummyJSON (mocked data)

## Convenciones
- Tools: Postman
- Evidence: save screenshot or response in `/evidence/`
- Expected status: 200, 201, 400, 401, 404

---

## Auth — POST /user/login

### TC-A01 — successful login with valid credentials
**Precondition:** None  
**Steps:**
1. Send POST a `/user/login` with valid username and password
**Expected:**
- Status: 200 OK
- Response includes authentication token and user data
**Actual:**  
- Status: 200 OK
- Response includes authentication token and user data
**Result (Pass/Fail):**  
- Pass 
**Evidence:**
- Response saved in Postman

### TC-A02 — Login fails with invalid password
**Precondition:** Invalid password   
**Steps:**
1. Send POST a `/user/login` with valid username and invalid password
**Expected:**
- Status: 400 Bad Request
- Error message indicating invalid credentials
**Actual:**  
- Status: 400 Bad Request
- Error message indicating invalid credentials
**Result (Pass/Fail):**
- Pass  
**Evidence:**
- Response saved in Postman
---
### TC-A03 — Login fails when username is missing
**Precondition:** Username not provided 
**Steps:**
1. Send POST a `/user/login` with body missing the username field
**Expected:**
- Status: 400 Bad Request
- Error message indicating invalid credentials
**Actual:**  
- Status: 400 Bad Request
- Error message indicating invalid credentials
**Result (Pass/Fail):**
- Pass  
**Evidence:**
- Response saved in Postman
---
### TC-A04 — Login fails with empty request body
**Precondition:** Empty request body
**Steps:**
1. Send POST a `/user/login` with empty body (`{}`)
**Expected:**
- Status: 400 Bad Request
- Error message returned (Username and password required)
**Actual:**  
- Status: 400 Bad Request
- Error message returned (Username and password required)
**Result (Pass/Fail):**
- Pass  
**Evidence:**
- Response saved in Postman
---

## Products — GET /products (Public endpoint)
...

### TC-P01 — Get product list successfully
**Precondition:** None  
**Steps:**
1. Send GET a `/products` 
**Expected:**
- Status: 200 OK
- Response contains a `products` array
- Response includes pagination fields (`total`, `skip`, `limit`)
**Actual:**  
- Status: 200 OK
- Response contains `products` array with product objects
- Pagination fields returned
**Result (Pass/Fail):**  
- Pass 
**Evidence:**
- Response saved in Postman

### TC-P02 — Get product with pagination
**Precondition:** None  
**Steps:**
1. Send GET a `/products?limit=5&skip=10` 
**Expected:**
- Status: 200 OK
- Response returns 5 products
- Pagination fields include `total`, `skip`, and `limit`
- Pagination values reflect request (`limit=5`, `skip=10`)
**Actual:**  
- Status: 200 OK
- Response returns 5 products
- Pagination fields returned with correct values
**Result (Pass/Fail):**  
- Pass 
**Evidence:**
- Response saved in Postman

### TC-P03 — Get product by id (valid id)
**Precondition:** Product with given ID exists 
**Steps:**
1. Send GET a `/products/{id}` using a valid product ID (e.g. `/products/1`)
**Expected:**
- Status: 200 OK
- Response returns a product object
- Product `id` matches the requested ID
**Actual:**  
- Status: 200 OK
- Response returns a product object
- Product `id` matches the requested ID
**Result (Pass/Fail):**  
- Pass 
**Evidence:**
- Response saved in Postman

### TC-P04 — Get product by ID (not found)
**Precondition:** Product with given ID does not exist  
**Steps:**
1. Send GET request to `/products/{id}` using a non-existing product ID
**Expected:**
- Status: 404 Not Found
- Error message indicating product not found
**Actual:**
- Status: 404 Not Found
- Error message returned ("Product with id '198' not found")
**Result (Pass/Fail):**
- Pass
**Evidence:**
- Response saved in Postman

### TC-P05 — Create product successfully (valid body)
**Precondition:** None  
**Steps:**
1. Send POST request to `/products/add` with valid JSON body
**Expected:**
- Status: 200 OK or 201 Created
- Response returns a product object with an `id`
- Returned `title` matches the request body
**Actual:**
- Status: 201 Created
- Response returns a product object with generated `id`
- Returned `title` matches the request body
**Result (Pass/Fail):**
- Pass
**Evidence:**
- Response saved in Postman

### TC-P06 — Create product without title
**Precondition:** None  
**Steps:**
1. Send POST request to `/products/add` with body missing `title`
**Expected:**
- Status: 400 Bad Request
- Error message indicating missing required field
**Actual:**
- Status: 201 Created
- Product created despite missing required `title` field
**Result (Pass/Fail):**
- Fail
**Evidence:**
- Response saved in Postman
- Response saved in `/evidence/tc-p06-missing-title-response.json`

### TC-P07 — Create product with invalid price (string)
**Precondition:** None  
**Steps:**
1. Send POST request to `/products/add` with `price` as a string
**Expected:**
- Status: 400 Bad Request
- Error message indicating invalid price type
**Actual:**
- Status: 201 Created
- Product created despite `price` being an invalid type (string)
**Result (Pass/Fail):**
- Fail
**Evidence:**
- Response saved in Postman
- Response saved in `/evidence/tc-p07-invalid-price-response.json`

