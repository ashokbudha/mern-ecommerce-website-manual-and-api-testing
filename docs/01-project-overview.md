# 4xcollection — Project Overview

> **QA Portfolio Project | Web E-commerce Application | Developer & QA Tester**

## 1. Project Overview

**4xcollection** is a clothing e-commerce web application developed using the MERN technology stack. The platform provides customers with an online interface for discovering clothing products, viewing product information, selecting product variants, adding products to a cart, completing checkout, placing orders, and reviewing their order history.

The application is currently **partially completed**, with the customer-facing shopping workflow available while several advanced customer and administrative capabilities remain under development.

This repository, **`4xcollection-qa-test`**, is a dedicated QA portfolio project created to demonstrate a structured and professional software testing process across manual testing, API testing, database validation, integration testing, end-to-end testing, regression testing, and test automation.

The QA project is designed to validate the application's critical business workflows, identify and document defects, verify API and database behavior, and establish automated regression coverage for important user journeys.

### Application

* **Application Name:** 4xcollection
* **Application Type:** Clothing E-commerce Web Application
* **Application Status:** Partially completed
* **QA Project:** 4xcollection QA & Test Automation
* **QA Repository:** `4xcollection-qa-test`
* **QA Repository Visibility:** Public
* **Application Source Repository:** Private repository
* **Live Application:** https://4xcollection.vercel.app/

---

## 2. Business Context

### 2.1 Purpose

4xcollection is intended to provide customers with an online platform for discovering and purchasing clothing products.

The application supports the core activities required in a typical clothing e-commerce customer journey, from account creation and authentication through product discovery, cart management, checkout, order placement, and order-history access.

From a QA perspective, the application provides a realistic testing scope because it contains multiple interconnected components, including:

* User authentication
* Product and category management
* Product variants
* Shopping cart
* Checkout
* Order creation
* Order history
* REST APIs
* Database persistence
* Cloud-based image management
* Authentication using JWT
* Multiple deployed application components

### 2.2 Target Users

The primary users of the application are:

1. **Customers**

   * Customers looking to browse and purchase clothing products online.
   * Customers who need to manage their shopping activity and view previous orders.

2. **Administrators**

   * Administrators responsible for managing products and e-commerce data.
   * Administrative functionality is currently under development.

### 2.3 Primary Business Goal

The primary business goal of 4xcollection is:

> **Provide customers with an online platform for discovering and purchasing clothing products.**

---

## 3. Current Functional Scope

The current application supports the following customer-facing functionality.

| Functional Area          | Current Status          |
| ------------------------ | ----------------------- |
| Product listing          | Implemented             |
| Product categories       | Implemented             |
| Product search           | Not implemented         |
| Category filtering       | Not implemented         |
| Product details          | Implemented             |
| Product variants         | Implemented             |
| User registration        | Implemented             |
| User login               | Implemented             |
| JWT authentication       | Implemented             |
| Wishlist                 | Not currently available |
| Shopping cart            | Implemented             |
| Checkout                 | Implemented             |
| Order creation           | Implemented             |
| Order history            | Implemented             |
| Admin product management | Not currently available |
| Payment gateway          | Not implemented         |
| Order cancellation       | Not implemented         |
| Email notifications      | Not implemented         |

### 3.1 Current Customer Workflow

The currently supported primary customer journey is:

**Register → Login → Browse Products → View Product Details → Select Product Variant → Add to Cart → Checkout → Place Order → View Order History**

This workflow represents the application's primary end-to-end business flow and will therefore be an important focus of functional, integration, end-to-end, regression, and automation testing.

### 3.2 Administrative Scope

Administrative functionality is currently under development.

At the present stage:

> **Nothing from the administrative functionality is currently working.**

Therefore, administrative functionality will be treated as an identified application limitation rather than as an available feature in current QA execution.

---

## 4. Known Limitations and Planned Functionality

The current application does not yet provide several features that may be considered for future development and QA coverage.

Known limitations and planned functionality include:

* Product reviews
* Average product ratings
* Related products
* Recommended products
* Product view counts
* Server-side product search
* Server-side category filtering
* Price-range filtering
* Sorting by price/popularity
* Stock-availability filtering
* Backend wishlist status
* Backend cart status
* Individual product-variant updates
* Bulk product updates
* Product update history
* Payment gateway integration
* Order cancellation
* Email notifications
* Administrative product-management functionality

These items will not be represented as currently working application features in QA documentation or test results.

Where backend APIs have already been implemented for functionality that is not currently exposed or usable through the frontend, API testing will distinguish **backend implementation status** from **frontend feature availability**.

---

## 5. Technical Architecture

4xcollection is built using the **MERN stack with Cloudinary**.

### 5.1 Technology Stack

| Layer            | Technology           |
| ---------------- | -------------------- |
| Frontend         | React.js             |
| Backend          | Node.js + Express.js |
| Database         | MongoDB              |
| Database ODM     | Mongoose             |
| Authentication   | JWT                  |
| JWT Storage      | HTTP-only cookie     |
| Image Management | Cloudinary           |
| API Architecture | RESTful API          |
| Frontend Hosting | Vercel               |
| Backend Hosting  | Render               |
| Database Hosting | MongoDB Atlas        |

### 5.2 Architecture Overview

The application follows a client-server architecture in which the React.js frontend communicates with the Node.js/Express.js backend through RESTful APIs.

The backend handles application logic, authentication, data processing, and communication with MongoDB. MongoDB is accessed through Mongoose, while Cloudinary is used for storing and managing product images.

The major application flow can be represented as:

**React.js Frontend**

↓

**RESTful API**

↓

**Node.js + Express.js Backend**

↓

**Mongoose**

↓

**MongoDB Atlas**

Additional image-management operations use:

**Application → Cloudinary**

Authentication is implemented using JWT, with authentication tokens stored in **HTTP-only cookies**.

### 5.3 Deployment Architecture

The application is deployed using separate cloud services:

* **Frontend:** Vercel
* **Backend:** Render
* **Database:** MongoDB Atlas
* **Product Images:** Cloudinary

The QA project uses the deployed production application as its testing environment.

---

## 6. API Scope

The application exposes RESTful APIs covering the major application domains.

Currently implemented backend API areas include:

* Authentication
* Users
* Products
* Categories
* Cart
* Wishlist
* Orders
* Checkout

An important QA consideration is that **backend API availability does not necessarily mean the corresponding frontend feature is currently available**.

For example, an API endpoint may exist for a functionality while the corresponding frontend workflow is still incomplete or unavailable. API testing will therefore validate the backend independently from frontend feature status.

An existing **Postman collection** is available for the application and will form part of the API testing activities.

API testing will focus on areas such as:

* Request and response validation
* HTTP status codes
* Authentication and authorization
* Request validation
* Response data
* Negative scenarios
* Error handling
* API-to-database behavior
* Business-rule validation
* Integration between related endpoints

---

## 7. QA Scope

The QA project covers multiple layers of software testing rather than relying only on UI-based testing.

### 7.1 Testing Types

The planned QA scope includes:

* **Manual Testing**
* **Functional Testing**
* **UI Testing**
* **Negative Testing**
* **API Testing**
* **Database Testing**
* **Integration Testing**
* **End-to-End Testing**
* **Regression Testing**
* **Test Automation**

### 7.2 Manual Testing

Manual testing will establish the initial functional baseline of the application.

Testing will cover the critical customer workflows, including:

* Registration
* Login
* Product browsing
* Product details
* Variant selection
* Cart operations
* Checkout
* Order placement
* Order-history verification

Manual testing will also cover negative scenarios and validation of expected application behavior.

### 7.3 API Testing

Postman will be used to validate the application's REST APIs.

The existing Postman collection will be used as the starting point for API testing, with test coverage expanded and documented as part of the QA project.

### 7.4 Database Testing

MongoDB will be validated to ensure that backend operations correctly persist and retrieve application data.

Database testing will focus on areas such as:

* User records
* Product data
* Cart data
* Order data
* Data consistency
* Relationships between application operations and persisted data

### 7.5 Integration Testing

Integration testing will validate interactions between application components, particularly:

**Frontend → Backend API → Database**

Examples include validating that an order placed through the frontend results in the expected backend processing and database persistence.

### 7.6 End-to-End Testing

End-to-end testing will validate complete business workflows from the user's perspective.

The primary E2E flow is:

**Registration/Login → Product Selection → Cart → Checkout → Order → Order History**

### 7.7 Regression Testing

Regression testing will verify that existing functionality remains stable after application changes.

Critical workflows will eventually become candidates for automated regression testing using Playwright.

---

## 8. Test Automation Strategy

The automation stack selected for this project is:

* **Playwright**
* **TypeScript**

Playwright will be used to automate important browser-based workflows and provide repeatable regression coverage.

The automation suite will prioritize critical business functionality rather than attempting to automate every application behavior immediately.

Initial automation priorities include:

* Authentication
* Product workflows
* Cart
* Checkout
* Orders

The automation framework will be structured to support maintainability and scalability through reusable page objects, fixtures, test data, utilities, and configuration.

### Automation Architecture

The planned automation structure includes:

* **Tests** — business-level automated test cases
* **Pages** — Page Object Model implementations
* **Fixtures** — reusable test setup and context
* **Test Data** — controlled test inputs
* **Utils** — reusable helper functions and API utilities
* **Configuration** — Playwright and TypeScript configuration
* **Reports** — automated test execution results

GitHub Actions will be used as the CI/CD platform for executing automated tests within the QA workflow.

---

## 9. QA Deliverables

The project is intended to produce a complete set of QA artifacts covering the software testing lifecycle.

Planned deliverables include:

### Test Documentation

* Project Overview
* Test Plan
* Test Strategy
* Test Scenarios
* Manual Test Cases
* Test Execution Report
* Test Summary Report

### Defect Management

* Bug Reports
* Bug Summary
* Evidence and screenshots where applicable

### API Testing

* Postman API Collection
* API Test Cases
* API Testing Documentation
* API Test Reports

### Database Testing

* Database Test Cases
* Database Validation Queries
* Database Testing Documentation

### Automation

* Playwright + TypeScript Test Suite
* Page Object Model
* Test Fixtures
* Test Data
* Automation Utilities
* Automated Test Reports

### CI/CD

* GitHub Actions workflow
* Automated test execution through CI/CD

---

## 10. Current QA State

The QA project is currently at the **manual testing starting stage**.

Testing activities on the application have not yet been executed as part of this QA project. Consequently:

* No manual test execution results are currently claimed.
* No test cases have yet been executed.
* No defects have yet been formally identified through this QA project.
* No pass/fail metrics are reported.
* API testing on the application has not yet been performed as part of this QA project.
* Database testing has not yet been performed as part of this QA project.
* Playwright automation has not yet been implemented for this application.

This distinction is intentional: **the repository will report actual QA evidence and metrics only after the corresponding testing activities have been performed.**

---

## 11. QA Success Criteria

The project will be considered successful when:

> **Critical application workflows have documented test coverage, identified defects are tracked, APIs and database behavior are validated, and critical regression scenarios are automated.**

This definition emphasizes measurable QA outcomes rather than simply producing a collection of testing documents.

The project will progressively demonstrate:

1. Structured test planning.
2. Traceable manual test coverage.
3. Evidence-based test execution.
4. Defect identification and documentation.
5. API validation.
6. Database validation.
7. Integration and end-to-end coverage.
8. Automated regression coverage.
9. Repeatable CI/CD test execution.

Actual test metrics and execution statistics will be added after testing begins.

---

## 12. Development and QA Ownership

The application was primarily developed by **Ashok Budha**, with contributions from **Gyanendra Chaudhary**.

Ashok Budha's role in this project is:

> **Developer & QA Tester**

The QA activities, including test planning, manual testing, API testing, database testing, defect documentation, automation, and QA reporting, are the responsibility of Ashok Budha.

This project therefore demonstrates both sides of the development lifecycle:

**Application Development → Quality Assurance → Test Automation → Continuous Validation**

---

## 13. Environment and Access

### Production Application

The QA project uses the deployed production/live application as its testing environment.

**Application:** 4xcollection
**Environment:** Production / Live Deployment
**Frontend:** Vercel
**Backend:** Render
**Database:** MongoDB Atlas

The application source repository remains private, while the dedicated QA repository is public to provide visibility into the testing methodology, documentation, test artifacts, automation framework, and CI/CD implementation.

---

## 14. Project Objective

The primary objective of **4xcollection QA & Test Automation** is to transform testing of the 4xcollection application into a structured, evidence-based QA process.

The project will demonstrate the ability to:

* Understand an application's business workflows.
* Identify functional and non-functional testing requirements.
* Design meaningful test scenarios and test cases.
* Perform manual functional and negative testing.
* Validate REST APIs using Postman.
* Validate persisted data using MongoDB.
* Test integrations between application layers.
* Validate complete end-to-end workflows.
* Identify, document, and track defects.
* Build maintainable Playwright automation using TypeScript.
* Establish automated regression coverage.
* Integrate automated tests into GitHub Actions.
* Produce professional QA documentation and reporting.

The final QA repository is intended to serve as a practical demonstration of a complete software testing lifecycle applied to a real web application rather than as a collection of theoretical testing examples.

---

## 15. Project Status Summary

| Area                         | Status                      |
| ---------------------------- | --------------------------- |
| Application development      | Partially completed         |
| Customer shopping workflow   | Available                   |
| Administrative functionality | Under development           |
| Manual QA                    | Starting                    |
| Manual test cases            | Planned                     |
| Test execution               | Not started                 |
| API testing                  | Planned                     |
| Database testing             | Planned                     |
| Integration testing          | Planned                     |
| E2E testing                  | Planned                     |
| Regression testing           | Planned                     |
| Playwright automation        | Planned                     |
| CI/CD                        | Planned                     |
| Defect reporting             | Planned                     |
| QA metrics                   | To be added after execution |

---

## 16. Conclusion

4xcollection provides a realistic foundation for demonstrating modern software quality assurance practices across a full-stack e-commerce application.

The QA project will progressively validate the application from multiple perspectives: user-facing functionality, API behavior, database persistence, integration between system components, complete business workflows, and automated regression coverage.

Because the application is still partially completed, the QA documentation will explicitly distinguish between **implemented functionality, unavailable functionality, known limitations, and planned testing activities**.

The overall goal is to establish a professional QA process around 4xcollection that is **structured, traceable, repeatable, evidence-driven, and suitable for demonstrating practical QA engineering capability to recruiters, QA interviewers, and technical reviewers.**
