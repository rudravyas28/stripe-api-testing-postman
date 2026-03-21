# Stripe API Testing Project (Postman)

## Overview

This project demonstrates API testing using Postman for Stripe Customer APIs. It focuses on validating real-world scenarios such as functional testing, negative testing, authentication handling, and idempotency behavior.

The goal of this project is to build a structured and scalable API testing suite similar to what is used in real QA environments.

---

## Objectives

- Validate API functionality with multiple input scenarios  
- Perform negative and boundary testing  
- Verify response structure and data integrity  
- Test idempotency behavior for duplicate requests  
- Implement authentication validation scenarios  
- Build a modular and scalable API testing project  

---

## Tools Used

- Postman  
- Stripe API  
- JavaScript (Postman test scripts)  

---

## Project Structure

```text
STRIPE_API_TESTING/
│
├── collections/
│ └── customers/
│ └── Customers.postman_collection.json
│
├── environments/
│ └── Stripe_API_env.postman_environment.json
│
├── docs/
│
├── screenshots/
│
└── README.md
```

---

## Modules Covered

### Customers API (In Progress)

---

### Create Customer (POST)

Test scenarios implemented:

- CUST-001 Valid Data  
- CUST-002 Empty Body / Null Data  
- CUST-003 Invalid Email Format  
- CUST-004 Email Too Long  
- CUST-005 Name Too Long  
- CUST-006 Phone Too Long  
- CUST-007 Invalid Tax Exempt Value  
- CUST-008 Partial Address  
- CUST-009 Invalid Address Type  
- CUST-010 Business Name Too Long  
- CUST-011 Duplicate Request (Same Idempotency Key)  
- CUST-012 Same Idempotency Key with Different Data  
- CUST-013 No Auth Request  
- CUST-014 Invalid Auth Request  

---

### Get Customer by ID (GET)

Test scenarios implemented:

- Retrieve-001 Valid Customer Retrieval  
- Retrieve-002 Invalid Customer ID  
- Retrieve-003 No Auth Request  
- Retrieve-004 Invalid Auth Request  

Planned / In Progress:

- Retrieve-005 Deleted Customer Scenario (to be implemented)

---

## How to Run

1. Import the collection into Postman  
2. Import the environment file  
3. Add your Stripe API key in environment variable:  
   `secret_key`  
4. Execute requests individually or via Collection Runner  

---

## Notes

- Secret keys are not included in the repository for security reasons  
- Environment variables are exported without sensitive values  
- Dynamic test data is used to avoid duplication conflicts  
- Idempotency key handling is implemented for duplicate request validation  
- This project is being built incrementally and will be extended with additional APIs  

---

## Upcoming Enhancements

- Implement List All Customers API  
- Add Update and Delete Customer APIs  
- Expand to other Stripe modules (Payment Intents, Accounts, Webhooks)  
- Integrate Newman for command-line execution  
- Set up CI/CD using GitHub Actions  
- Improve response schema validation and reporting  