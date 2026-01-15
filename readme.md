# QA Manual API Testing — DummyJSON

This repository is part of my QA portfolio and demonstrates **manual functional API testing** of a public REST API using **Postman**, with a focus on backend validation, error handling, and real API behavior.

## 📌 Project Overview
The goal of this project is to design and execute manual test cases for selected REST API endpoints, validate both expected and unexpected behaviors, document results, and report defects based on actual API responses.

This project showcases **QA Manual skills applied to REST APIs**, including test design, execution, and defect reporting.

## 🔧 Tools Used
- Postman
- DummyJSON Public API
- API Documentation (DummyJSON Docs)

## 🧪 Testing Scope
The following endpoints were tested:

### Authentication
- POST `/user/login`

### Products
- GET `/products`
- GET `/products/{id}`
- POST `/products/add`

Both positive and negative scenarios were covered, including input validation and error handling.

## 🐞 Defect Reporting
Identified issues were documented as bug reports, including:
- Missing required field validation
- Invalid data type handling

Each bug report includes reproduction steps, expected vs actual results, and supporting evidence.

## 📂 Project Structure
```txt
qa-api-testing-dummyjson/
├── README.md
├── test-plan.md
├── test-cases.md
├── bug-reports.md
└── evidence/
```
## 🧩 Postman Collection

The `/postman` folder contains the exported Postman collection used to execute all manual API test cases.  
It can be imported directly into Postman to review or re-run the tests.

## ▶️ How to Review the Tests

1. Import the Postman collection from the `/postman` folder into Postman  
2. Review test cases and scenarios in `test-cases.md`  
3. Check documented issues in `bug-reports.md` along with supporting evidence
