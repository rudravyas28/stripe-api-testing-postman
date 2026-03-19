# Stripe API Testing Project (Postman)

## Overview

This project demonstrates API testing using Postman for Stripe APIs. It focuses on validating real-world scenarios such as functional testing, negative testing, and idempotency behavior.

The goal of this project is to build a structured and scalable API testing suite similar to what is used in real QA environments.

## Objectives

* Validate API functionality with different input scenarios
* Perform negative and boundary testing
* Verify response structure and data integrity
* Test idempotency behavior for duplicate requests
* Build a modular and scalable API testing project

## Tools Used

* Postman
* Stripe API
* JavaScript (Postman test scripts)

## Project Structure

```text
collections/
└── customers/
    └── Stripe_Customers_API.postman_collection.json

environments/
└── Stripe_Test_Environment.postman_environment.json
```

## Modules Covered

### Customers API (In Progress)

#### Create Customer (POST)

Test scenarios implemented:

* Valid customer creation
* Empty request handling
* Invalid email format
* Field length validations
* Invalid data types
* Partial address validation
* Idempotency key validation
* Duplicate request handling

## How to Run

1. Import the collection into Postman
2. Import the environment file
3. Add your Stripe API key in environment variable:
   `STRIPE_API_KEY`
4. Execute requests individually or via Collection Runner

## Notes

* Secret keys are not included for security reasons
* Dynamic test data is used to avoid duplication conflicts
* This project is being built incrementally and will be extended with additional APIs

## Upcoming Enhancements

* Add GET, UPDATE, DELETE for Customers API
* Expand to other Stripe modules (Payment Intents, Accounts, Webhooks)
* Improve response validations and test coverage
