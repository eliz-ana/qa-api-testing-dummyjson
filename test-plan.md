# Test Plan — DummyJSON API (Manual API Testing)

## 1. Overview
This test plan describes the manual functional testing of a public REST API (DummyJSON mock API) using Postman, focusing on authentication and product-related endpoints.

## 2. Objectives
The objective of this testing is to verify that the selected API endpoints:
- Return correct HTTP status codes
- Provide expected response bodies
- Handle invalid input and error scenarios correctly
- Are suitable for basic API smoke testing
- Identify functional gaps and validation issues in API behavior


## 3. Scope (In Scope)

### Authentication
- POST `/user/login`

### Products
- GET `/products`
- GET `/products/{id}`
- POST `/products/add`

## 4. Out of Scope
- Performance and load testing
- Advanced security testing
- Test automation
- UI testing
- Full endpoint coverage

## 5. Test Types
- Exploratory testing (basic)
- Manual functional testing
- Positive testing
- Negative testing
- Edge case testing
- Basic smoke testing

## 6. Test Environment & Tools
- API: DummyJSON (public API)
- Documentation: DummyJSON API official documentation
- Tool: Postman
- Evidence: Stored in `/evidence/` folder

## 7. Entry Criteria
- Postman installed and configured
- Access to DummyJSON API documentation
- Test collection created in Postman

## 8. Exit Criteria
- All planned test cases executed
- Test results documented (Pass/Fail)
- Defects reported with proper evidence
- Test artifacts completed

## 9. Risks & Mitigation
- Public API behavior may change → execution date documented
- Dynamic test data → validate structure instead of exact values
- Temporary API unavailability → retry and document issues

## 10. Deliverables
- test-plan.md
- test-cases.md
- bug-reports.md
- evidence/
