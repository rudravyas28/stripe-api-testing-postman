Stripe API Testing Project (Postman + CI)
=========================================

Overview
--------

This project demonstrates API testing using Postman for Stripe Customer APIs. It focuses on validating real-world scenarios such as functional testing, negative testing, authentication handling, and idempotency behavior.

The project is designed to simulate a real QA environment with structured test cases, reusable scripts, and automated execution using a CI pipeline.

* * * * *

Objectives
----------

-   Validate API functionality with multiple input scenarios
-   Perform negative and boundary testing
-   Verify response structure and data integrity
-   Test idempotency behavior for duplicate requests
-   Implement authentication validation scenarios
-   Build a modular and scalable API testing project
-   Enable automated test execution using CI pipeline

* * * * *

Tools Used
----------

-   Postman
-   Stripe API
-   JavaScript (Postman test scripts)
-   Newman (Postman CLI runner)
-   Git & GitHub
-   GitHub Actions (CI pipeline)

* * * * *

Project Structure
-----------------

STRIPE_API_TESTING/\
│\
├── .github/\
│   └── workflows/\
│       └── postman-ci.yml\
│\
├── collections/\
│   └── customers/\
│       └── Customers.postman_collection.json\
│\
├── environments/\
│   └── Stripe_API_env.postman_environment.json\
│\
├── docs/\
│\
├── screenshots/\
│\
└── README.md

* * * * *

Modules Covered
---------------

### Customers API (In Progress)

* * * * *

### Create Customer (POST)

Test scenarios implemented:

-   CUST-001 Valid Data
-   CUST-002 Empty Body / Null Data
-   CUST-003 Invalid Email Format
-   CUST-004 Email Too Long
-   CUST-005 Name Too Long
-   CUST-006 Phone Too Long
-   CUST-007 Invalid Tax Exempt Value
-   CUST-008 Partial Address
-   CUST-009 Invalid Address Type
-   CUST-010 Business Name Too Long
-   CUST-011 Duplicate Request (Same Idempotency Key)
-   CUST-012 Same Idempotency Key with Different Data
-   CUST-013 No Auth Request
-   CUST-014 Invalid Auth Request

* * * * *

### Get Customer by ID (GET)

Test scenarios implemented:

-   Retrieve-001 Valid Customer Retrieval
-   Retrieve-002 Invalid Customer ID
-   Retrieve-003 No Auth Request
-   Retrieve-004 Invalid Auth Request

Planned / In Progress:

-   Retrieve-005 Deleted Customer Scenario (to be implemented)

* * * * *

Test Design Highlights
----------------------

-   Dynamic data generation to avoid duplication conflicts
-   Idempotency key handling for safe retry validation
-   Separation of positive and negative test scenarios
-   Validation of response structure and key fields
-   Authentication and authorization testing
-   Designed for execution via Postman, Newman, and CI pipeline

* * * * *

How to Run
----------

### Option 1: Using Postman

1.  Import the collection into Postman
2.  Import the environment file
3.  Add your Stripe API key in environment variable:\
    `secret_key`
4.  Execute requests individually or via Collection Runner

* * * * *

### Option 2: Using Newman (Local CLI)

newman run collections/customers/Customers.postman_collection.json -e environments/Stripe_API_env.postman_environment.json --env-var "secret_key=YOUR_KEY"

* * * * *

CI Pipeline (GitHub Actions)
----------------------------

This project includes a CI pipeline using GitHub Actions to automate API test execution.

### Workflow Triggers

-   Push to `main` branch
-   Pull requests
-   Manual trigger (workflow_dispatch)

* * * * *

### Pipeline Steps

1.  Checkout repository
2.  Setup Node.js
3.  Install Newman
4.  Run Postman collection
5.  Inject Stripe API key securely via GitHub Secrets

* * * * *

### Secret Configuration

The following secret must be configured in GitHub:

STRIPE_SECRET_KEY

This value is securely passed to the pipeline and is not stored in the repository.

* * * * *

Notes
-----

-   Secret keys are not included in the repository for security reasons
-   Environment variables are exported without sensitive values
-   Dynamic test data is used to avoid duplication conflicts
-   Idempotency key handling is implemented for duplicate request validation
-   CI pipeline ensures automated validation on every code push
-   Project is structured to scale across multiple API modules

* * * * *

Upcoming Enhancements
---------------------

-   Implement List All Customers API
-   Add Update and Delete Customer APIs
-   Expand to other Stripe modules (Payment Intents, Accounts, Webhooks)
-   Enhance Newman reporting (HTML reports, artifacts)
-   Add test result visualization in CI
-   Improve response schema validation