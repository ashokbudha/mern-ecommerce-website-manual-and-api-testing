# 4xcollection --- Software Test Plan

**Document Version:** 1.0\
**Document Status:** Draft\
**Application:** 4xcollection\
**QA Repository:** `4xcollection-qa-test`\
**Testing Environment:** Production / Live Deployment\
**QA Role:** Ashok Budha --- Developer & QA Tester\
**Document Audience:** QA Interviewers, Recruiters, Technical Reviewers

------------------------------------------------------------------------

## 1. Purpose

This Test Plan defines the scope, objectives, approach, environment,
test coverage, test data strategy, defect management process, entry and
exit criteria, risks, deliverables, traceability, metrics, and
automation strategy for quality assurance of the 4xcollection clothing
e-commerce application.

The plan is intended to provide a structured, risk-aware, evidence-based
testing process for the current application version. It distinguishes
implemented functionality from functionality that is currently
unavailable or under development.

Testing will be performed against the deployed production/live
application at:

**https://4xcollection.vercel.app/**

The plan is aligned with recognized software testing practices,
including ISO/IEC/IEEE 29119 concepts, risk-based testing, requirements
traceability, evidence-based execution, defect lifecycle management,
entry/exit criteria, test metrics, and CI/CD-aware testing. This
alignment does not represent formal ISO certification.

------------------------------------------------------------------------

## 2. Application Overview

4xcollection is a clothing e-commerce web application built using the
MERN stack with Cloudinary.

The application allows customers to:

-   Register an account.
-   Log in.
-   Browse products.
-   View product details.
-   Select product variants.
-   Add products to the cart.
-   Complete checkout.
-   Place orders.
-   View order history.

The application is partially completed. Administrative functionality is
currently under development and no administrative functionality is
currently working.

### 2.1 Technology Stack

  Layer              Technology
  ------------------ ----------------------
  Frontend           React.js
  Backend            Node.js + Express.js
  Database           MongoDB
  Database ODM       Mongoose
  Authentication     JWT
  JWT Storage        HTTP-only cookie
  Image Management   Cloudinary
  API Architecture   RESTful API
  Frontend Hosting   Vercel
  Backend Hosting    Render
  Database Hosting   MongoDB Atlas

### 2.2 Primary Customer Workflow

The primary customer workflow covered by this test plan is:

**Register → Login → Browse Products → View Product Details → Select
Product Variant → Add to Cart → Checkout → Place Order → View Order
History**

This workflow is a major priority for functional, integration,
end-to-end, regression, and automation testing.

------------------------------------------------------------------------

## 3. Test Objectives

The primary objective is to verify that critical customer workflows
function as expected, validate API and database behavior, identify and
document defects, and establish automated regression coverage for
critical business scenarios.

The testing effort will specifically seek to:

1.  Verify functional correctness of implemented application features.
2.  Validate the user interface and important user interactions.
3.  Validate REST API behavior using the existing Postman collection.
4.  Validate MongoDB CRUD operations and application data behavior.
5.  Verify authentication and authorization behavior.
6.  Validate positive and negative scenarios.
7.  Verify integration between frontend, backend, and database
    components.
8.  Validate complete customer-facing end-to-end workflows.
9.  Protect critical functionality through regression testing.
10. Establish maintainable automated regression coverage using
    Playwright and TypeScript.
11. Produce traceable, evidence-based QA documentation and defect
    records.

------------------------------------------------------------------------

## 4. Quality Priorities

The following quality areas are in scope:

-   Functional correctness
-   UI correctness
-   API correctness
-   Database/data integrity
-   Authentication and authorization
-   Error handling
-   Negative scenarios
-   Integration behavior
-   End-to-end business workflows
-   Regression protection
-   Usability
-   Performance
-   Accessibility
-   Security
-   Compatibility/cross-browser behavior

Performance, security, and accessibility are identified as future-scope
testing activities. Browser compatibility testing is not included in the
current test effort; Playwright execution will target Chromium only.

------------------------------------------------------------------------

## 5. Scope

### 5.1 In Scope

The following areas are explicitly in scope:

#### Customer-facing functionality

-   Registration
-   Login
-   Logout
-   JWT authentication
-   Product listing
-   Product categories
-   Product details
-   Product variants
-   Shopping cart
-   Wishlist 
-   Checkout
-   Order creation
-   Order history

#### API testing

-   Authentication APIs
-   Users APIs
-   Products APIs
-   Categories APIs
-   Cart APIs
-   Wishlist APIs
-   Orders APIs
-   Checkout APIs

The existence of a backend API does not imply that the corresponding
frontend functionality is currently available. API testing will
therefore assess implemented backend endpoints independently where
applicable.

#### Database testing

-   MongoDB CRUD validation

### 5.2 Out of Scope / Not Testable in the Current Application Version

The following functionality is currently unavailable, incomplete, or
planned for future development and will not be treated as working
application functionality in the current test execution:

-   Product search
-   Category filtering
-   Wishlist frontend functionality
-   Administrative functionality
-   Payment gateway
-   Order cancellation
-   Email notifications
-   Product reviews
-   Ratings
-   Related products
-   Recommended products
-   Other planned filtering and sorting functionality

Known future functionality also includes additional product
filtering/sorting and product-management capabilities that are not
currently available.

------------------------------------------------------------------------

## 6. Test Approach

Testing will use a layered approach covering manual testing, API
testing, database validation, integration testing, end-to-end testing,
regression testing, and automation.

### 6.1 Manual Testing

Manual testing will begin with requirement and workflow analysis,
followed by test scenario and test case design. Test cases will be
executed against the live application, with actual results and evidence
recorded. Failed tests will be investigated and converted into defect
reports where appropriate.

Manual testing will prioritize critical customer workflows and include
both positive and negative scenarios.

### 6.2 Functional and UI Testing

Functional testing will verify that implemented features behave
according to their expected business behavior.

UI testing will validate:

-   Page and component behavior
-   User interactions
-   Form behavior
-   Navigation
-   Visible validation/error behavior
-   Product and cart interactions
-   Checkout interactions

### 6.3 Negative Testing

Negative testing will intentionally use invalid, incomplete,
unauthorized, or otherwise unexpected inputs where applicable to verify
appropriate error handling and system behavior.

### 6.4 API Testing

The application has an existing Postman collection. API testing will
cover:

-   Positive scenarios
-   Negative scenarios
-   Authentication and authorization
-   Request validation
-   Response validation
-   HTTP status codes
-   Error handling
-   Data consistency
-   API-to-database validation

### 6.5 Database Testing

Database testing is intentionally scoped to **CRUD validation**.

Testing will verify the relevant create, read, update, and delete
behavior of application data in MongoDB where those operations are
supported by the application.

### 6.6 Integration Testing

Integration testing will validate interactions between application
components, including:

**Frontend → REST API → Backend → MongoDB**

Integration testing will verify that actions initiated through one
application layer produce the expected behavior in connected components.

### 6.7 End-to-End Testing

End-to-end testing will validate complete business workflows from the
customer perspective.

The primary E2E workflow is:

**Registration/Login → Product Selection → Variant Selection → Cart →
Checkout → Order Placement → Order History**

### 6.8 Regression Testing

Regression testing will verify that existing functionality remains
stable after application changes.

Critical customer workflows will be prioritized for repeatable
regression execution and eventual automation.

------------------------------------------------------------------------

## 7. Automation Strategy

Automation will use:

-   **Playwright**
-   **TypeScript**

The selected strategy is a combination of feature-level automation and
critical end-to-end workflows.

### 7.1 Feature-Level Automation

Individual application features will have focused automated tests where
appropriate, including:

-   Authentication
-   Products
-   Cart
-   Checkout
-   Orders

### 7.2 Critical End-to-End Automation

A smaller set of high-value end-to-end scenarios will validate the
critical customer journey across multiple application components.

### 7.3 Automation Priorities

Automation will prioritize:

1.  Login/authentication
2.  Product interaction
3.  Product variant selection
4.  Cart
5.  Checkout
6.  Order placement
7.  Order history

### 7.4 Framework Structure

The automation implementation will use reusable components such as:

-   Page objects
-   Fixtures
-   Test data
-   Utility functions
-   Playwright configuration
-   Automated reports

GitHub Actions will be used for CI/CD integration of the automated test
suite.

------------------------------------------------------------------------

## 8. Browser and Responsive Coverage

### 8.1 Browser

Current Playwright automation coverage will target:

-   **Chromium / Chrome**

Cross-browser compatibility testing is outside the current test scope.

### 8.2 Responsive Testing

Responsive/mobile UI testing is in scope.

The defined viewport sizes are:

  Device Category       Viewport
  ----------------- ------------
  Mobile               375 × 667
  Tablet              768 × 1024
  Desktop             1440 × 900

Responsive testing will verify that the application remains usable and
functionally accessible across the defined viewport sizes.

------------------------------------------------------------------------

## 9. Test Environment

Testing will be performed against the production/live deployment.

**Application URL:** https://4xcollection.vercel.app/

  Component             Environment
  --------------------- -------------------
  Frontend              Vercel
  Backend               Render
  Database              MongoDB Atlas
  Image Management      Cloudinary
  Testing Environment   Production / Live

Because testing is performed against the live environment, test
execution will use dedicated QA accounts and controlled test data.

------------------------------------------------------------------------

## 10. Test Data Management

### 10.1 Test Accounts

Dedicated QA accounts will be created for testing.

These accounts will support scenarios involving:

-   Registration
-   Login
-   Authentication
-   Cart
-   Checkout
-   Orders
-   Negative testing

### 10.2 Test Data Owner

**Ashok Budha** is responsible for creating and managing QA test data.

### 10.3 Production Data Policy

Testing will use controlled test data and will not intentionally use
real customer personal information.

Because the application is tested in production, test activities must
avoid unnecessary impact on real users and real customer data.

------------------------------------------------------------------------

## 11. Defect Management

Defects will be tracked using both:

-   **GitHub Issues**
-   **Markdown bug reports within the QA repository**

This provides an operational defect-tracking mechanism together with
persistent documentation within the QA project.

### 11.1 Severity

  Severity   Definition
  ---------- --------------------------------------------------------
  Critical   Blocks a critical business flow or prevents system use
  High       Major functionality is broken
  Medium     Significant issue where a workaround exists
  Low        Minor functional or UI issue

### 11.2 Priority

  Priority   Definition
  ---------- -------------------------------------------------
  P0         Critical priority requiring immediate attention
  P1         High priority
  P2         Medium priority
  P3         Low priority

### 11.3 Defect Lifecycle

The planned defect lifecycle is:

**New → Triaged → Assigned → In Progress → Fixed → Retest → Closed**

Additional states may include:

-   Rejected
-   Duplicate
-   Won't Fix
-   Reopened
-   Referred

------------------------------------------------------------------------

## 12. Test Case Result Rules

Each test case will use one of the following execution statuses:

  -----------------------------------------------------------------------
  Status                              Definition
  ----------------------------------- -----------------------------------
  PASS                                Actual result meets the expected
                                      result

  FAIL                                Actual result does not meet the
                                      expected result

  BLOCKED                             Test cannot be executed because of
                                      a dependency or environment issue

  NOT RUN                             Test has not yet been executed
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 13. Entry Criteria

Formal test execution may begin when the following conditions are
satisfied:

-   Test environment is accessible.
-   Application build is available.
-   Critical application workflows are accessible.
-   Test data is prepared.
-   Test cases have been reviewed.
-   Required testing tools are available.

If a required entry condition is not satisfied, the affected testing
activity may be delayed or recorded as blocked.

------------------------------------------------------------------------

## 14. Exit Criteria

A testing cycle can be considered complete when:

-   Planned critical test cases have been executed.
-   Critical defects are resolved or formally accepted.
-   Regression testing has been completed for affected critical
    workflows.
-   API and database validation has been completed for the defined
    scope.
-   Required test evidence has been documented.
-   Test results and outstanding risks have been reported.

Exit criteria apply to the defined testing cycle and do not imply that
every future feature of the application has been tested.

------------------------------------------------------------------------

## 15. Test Deliverables

The QA project will produce the following deliverables.

### Planning

-   Test Plan
-   Test Scenarios
-   Manual Test Cases

### Execution

-   Test Execution Report
-   Test Evidence
-   Test Summary Report

### Defect Management

-   Bug Reports
-   Bug Summary

### API Testing

-   Postman Collection
-   API Test Cases
-   API Test Documentation
-   API Reports

### Database Testing

-   Database Test Cases
-   Database Queries
-   Database Test Documentation

### Automation

-   Playwright + TypeScript Test Suite
-   Automation Reports
-   Test Data
-   Fixtures
-   Page Objects

### CI/CD

-   GitHub Actions Workflow

------------------------------------------------------------------------

## 16. Requirements Traceability

The QA project will maintain traceability between requirements and
testing artifacts.

The intended relationship is:

**Requirement → Test Scenario → Test Case → Execution Result → Defect**

Traceability will help demonstrate that critical application behavior is
covered and that failed tests can be connected to documented defects.

------------------------------------------------------------------------

## 17. Test Metrics

Metrics will be collected only after actual test execution. No
fabricated execution results will be included.

The following metrics will be tracked where applicable:

-   Total test cases
-   Executed test cases
-   Passed test cases
-   Failed test cases
-   Blocked test cases
-   Not-run test cases
-   Pass rate
-   Defect count by severity
-   Defect closure rate
-   Automation coverage
-   Regression coverage

Metrics will be reported based on actual evidence from the relevant test
cycle.

------------------------------------------------------------------------

## 18. Risks and Mitigation

The following risks are included in the test plan.

  ----------------------------------------------------------------------------------------
  Risk                  Impact             Likelihood     Mitigation      Contingency
  --------------------- ------------------ -------------- --------------- ----------------
  Production            Test execution may Medium         Verify          Record affected
  environment           be affected by                    environment     tests as blocked
  dependency            live-environment                  availability    and resume when
                        availability or                   before          available
                        changes                           execution       

  Application is        Some workflows     High           Clearly         Exclude
  partially completed   cannot currently                  separate        unavailable
                        be validated                      implemented and functionality
                                                          unavailable     from current
                                                          functionality   execution and
                                                                          revisit after
                                                                          implementation

  Admin functionality   Administrative     High           Document admin  Add coverage
  unavailable           workflows cannot                  functionality   when the
                        be executed                       as out of scope functionality
                                                          for the current becomes
                                                          version         available

  Payment gateway       Real payment       High           Exclude payment Add payment
  unavailable           workflow cannot be                gateway testing testing after
                        validated                         from current    integration is
                                                          execution       implemented

  Missing product       Search/filter      Medium         Document them   Add tests after
  search/filter         scenarios cannot                  as unavailable  implementation
  functionality         be executed                       functionality   

  Test data changes in  Test execution     Medium         Use dedicated   Remove or
  a live environment    could affect                      QA accounts and correct test
                        application data                  controlled test data where
                                                          data            appropriate

  Third-party           Cloud services may Medium         Record          Re-run affected
  dependency failures   affect application                dependency      tests after
                        behavior                          failures        dependency
                                                          separately from recovery
                                                          application     
                                                          defects         

  Automation            Automated tests    Medium         Use             Investigate and
  instability caused by may fail after                    maintainable    update affected
  UI changes            application                       page objects,   automation
                        changes                           fixtures, and   components
                                                          stable          
                                                          selectors       

  Network/environment   Test execution may Medium         Verify          Mark affected
  availability          be interrupted                    connectivity    tests as blocked
                                                          and environment and re-execute
                                                          availability    

  Limited testing       Full planned       Medium         Prioritize      Defer
  time/resources        coverage may not                  critical        lower-priority
                        be completed                      business        testing and
                                                          workflows and   document
                                                          risk-based      remaining risk
                                                          coverage        
  ----------------------------------------------------------------------------------------

Risk assessment will use:

**Risk → Impact → Likelihood → Mitigation → Contingency**

------------------------------------------------------------------------

## 19. Roles and Responsibilities

### Ashok Budha --- Developer & QA Tester

Ashok Budha is responsible for:

-   Test planning
-   Test case design
-   Manual test execution
-   API testing
-   Database testing
-   Defect reporting
-   Test automation
-   Test reporting
-   CI/CD test integration
-   Test data management

Gyanendra Chaudhary's development contribution is documented in the
Project Overview and is not assigned QA responsibilities within this
Test Plan.

------------------------------------------------------------------------

## 20. Testing Schedule

No fixed calendar dates are defined for the current QA project.

Testing will follow a phase-based sequence:

### Phase 1 --- Test Planning

Define scope, objectives, risks, environments, test approach, and test
deliverables.

### Phase 2 --- Manual Test Design

Create test scenarios and detailed manual test cases for the defined
scope.

### Phase 3 --- Manual Execution

Execute manual functional, UI, negative, and critical workflow tests and
record evidence.

### Phase 4 --- API Testing

Execute and document API tests using the existing Postman collection.

### Phase 5 --- Database Testing

Validate MongoDB CRUD behavior associated with the defined application
scope.

### Phase 6 --- Integration and End-to-End Testing

Validate interactions between application components and complete
customer workflows.

### Phase 7 --- Test Automation

Implement Playwright + TypeScript automation for selected feature-level
and critical end-to-end scenarios.

### Phase 8 --- CI/CD

Integrate the automation suite into GitHub Actions.

### Phase 9 --- Regression and Final Reporting

Execute critical regression coverage, analyze results, document
outstanding risks and defects, and produce the final test summary.

------------------------------------------------------------------------

## 21. Future-Scope Testing

The following testing areas are explicitly future scope:

### Performance Testing

Performance/load testing will be considered in a future phase and is not
part of the current execution scope.

### Security Testing

Security testing will be considered in a future phase. This includes
deeper validation of authentication, authorization, unauthorized API
access, JWT behavior, input validation, and security-focused negative
scenarios.

### Accessibility Testing

Accessibility testing will be considered in a future phase.

### Additional Functional Testing

Testing will expand when currently unavailable functionality is
implemented, including areas such as:

-   Product search
-   Category filtering
-   Wishlist frontend functionality
-   Payment gateway
-   Order cancellation
-   Email notifications
-   Reviews and ratings
-   Related/recommended products
-   Additional product filtering and sorting
-   Administrative functionality

------------------------------------------------------------------------

## 22. Current QA Baseline

At the start of this Test Plan:

-   The application is partially completed.
-   Manual QA is starting.
-   No execution metrics are being claimed.
-   No test results are being fabricated.
-   No defects are being claimed as discovered through this QA project.
-   API testing on this application has not yet been performed as part
    of this QA project.
-   Database testing on this application has not yet been performed as
    part of this QA project.
-   Playwright automation has not yet been implemented for this
    application.

Future execution reports will replace this baseline with actual evidence
and measured results.

------------------------------------------------------------------------

## 23. Success Criteria

The project will be considered successful when:

> **Critical application workflows have documented test coverage,
> identified defects are tracked, APIs and database behavior are
> validated, and critical regression scenarios are automated.**

The success criteria emphasize practical QA outcomes rather than simply
producing documentation.

------------------------------------------------------------------------

## 24. Conclusion

This Test Plan establishes the quality assurance framework for the
4xcollection e-commerce application.

The testing strategy prioritizes critical customer workflows while
validating the application across the UI, REST API, database,
integration, end-to-end, regression, and automation layers.

The plan also establishes controlled test data practices, formal defect
management, traceability, risk management, execution criteria,
measurable QA metrics, and CI/CD-aware automation.

Because the application is partially completed, the current test effort
explicitly separates implemented functionality from unavailable
functionality and future scope. Actual test results, defect counts, pass
rates, automation coverage, and other metrics will be added only after
corresponding testing activities have been executed and supported by
evidence.
