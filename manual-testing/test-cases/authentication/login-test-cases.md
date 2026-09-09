# 4xcollection --- Login Test Cases

## Document Control

| Field | Details |
|---|---|
| **Document Title** | 4xcollection --- Login Test Cases |
| **Document ID** | TC-LOGIN |
| **Test Scenario** | TS-002 --- Validate the working of Login functionality |
| **Reference** | Test Plan |
| **Version** | 1.0 |
| **Status** | Draft |
| **QA Owner** | Ashok Budha |
| **Application** | 4xcollection |
| **Environment** | Production / Live |
| **Application URL** | https://4xcollection.vercel.app/ |
| **Browser** | Chromium |
| **Test Type** | Functional / Negative / UI |
| **Authentication** | JWT |
| **JWT Storage** | HTTP-only cookie |
| **Execution Status** | Not Run |

---

## 1. Purpose

This document contains the detailed test cases for:

> **TS-002 --- Validate the working of Login functionality**

The test cases validate the login functionality using the supported login identifier behavior:

> **Either the registered username or the registered email address must be correct, together with the correct password, for successful authentication.**

The document covers positive, negative, validation, authentication-state, UI, and error-handling scenarios without treating each individual validation as a separate test scenario.

---

## 2. Scope

### In Scope

- Login using a valid username and password
- Login using a valid email and password
- Login using an incorrect username
- Login using an incorrect email
- Login using an incorrect password
- Login with missing credentials
- Login with invalid email format where email is used as the identifier
- Login with an unregistered account
- Login with invalid input
- Authentication state after successful login
- Login error handling
- Login form presentation and usability
- Prevention of incorrect authentication after unsuccessful login attempts

### Out of Scope

- Registration
- Logout
- Password reset
- JWT implementation/API internals
- Payment
- Admin functionality
- Performance testing
- Security testing
- Accessibility testing
- Cross-browser testing

These areas are covered by separate scenarios or future testing scope.

---

## 3. Test Case Design Principles

1. Each row in the main test-case table represents one detailed test case.
2. All test cases in this document map to **TS-002**.
3. A successful login requires a **correct registered username OR correct registered email**, together with the correct password.
4. An incorrect username/email or incorrect password must not result in successful authentication.
5. QA-owned accounts and test data must be used.
6. Real customer personal information must not intentionally be used.
7. Actual Result, Result, and Comments are completed only during execution.
8. No test case is considered passed before execution.
9. Automation status indicates planned coverage and does not claim completed automation.

---

# 4. Test Case Table

> **Important:** Each row below represents one detailed test case, and all test cases map to **TS-002**.

| Test Case ID | Test Scenario | Test Case Title | Pre-requisites | Test Steps | Test Data | Expected Result (ER) | Actual Result | Priority | Result | Comments |
|---|---|---|---|---|---|---|---|---|---|---|
| **TC_LOGIN_001** | **(TS-002) Login Functionality** | **Validate successful login using a valid registered username and correct password** | 1. Application is accessible.<br>2. A valid registered QA account is available.<br>3. The account username and password are known. | 1. Open the 4xcollection application.<br>2. Navigate to the Login functionality.<br>3. Enter the valid registered username.<br>4. Enter the correct password.<br>5. Submit the login form.<br>6. Observe the result. | Valid registered username + correct password. | 1. Login request is accepted.<br>2. User is authenticated successfully.<br>3. Application establishes the authenticated state according to its implementation.<br>4. User is taken to the appropriate post-login state/page. | Not Executed | **P0** | **NOT RUN** | --- |
| **TC_LOGIN_002** | **(TS-002) Login Functionality** | **Validate successful login using a valid registered email and correct password** | 1. Application is accessible.<br>2. A valid registered QA account is available.<br>3. The account email and password are known. | 1. Open the Login functionality.<br>2. Enter the valid registered email address.<br>3. Enter the correct password.<br>4. Submit the login form.<br>5. Observe the result. | Valid registered email + correct password. | 1. Login request is accepted.<br>2. User is authenticated successfully.<br>3. Application establishes the authenticated state according to its implementation.<br>4. User is taken to the appropriate post-login state/page. | Not Executed | **P0** | **NOT RUN** | --- |
| **TC_LOGIN_003** | **(TS-002) Login Functionality** | **Validate login rejection when an incorrect username is provided with the correct password** | 1. Application is accessible.<br>2. A registered QA account is available.<br>3. Correct password is known.<br>4. A username that is not associated with the account is available. | 1. Open the Login functionality.<br>2. Enter an incorrect/unregistered username.<br>3. Enter the correct password for the valid account.<br>4. Submit the login form.<br>5. Observe the result. | Incorrect/unregistered username + correct password. | 1. Login should not be successful.<br>2. User should not be authenticated.<br>3. Appropriate login failure feedback should be displayed.<br>4. The application should not establish an authenticated state for the invalid identifier. | Not Executed | **P0** | **NOT RUN** | --- |
| **TC_LOGIN_004** | **(TS-002) Login Functionality** | **Validate login rejection when an incorrect email is provided with the correct password** | 1. Application is accessible.<br>2. A registered QA account is available.<br>3. Correct password is known.<br>4. An email address that is not associated with the account is available. | 1. Open the Login functionality.<br>2. Enter an incorrect/unregistered email address.<br>3. Enter the correct password for the valid account.<br>4. Submit the login form.<br>5. Observe the result. | Incorrect/unregistered email + correct password. | 1. Login should not be successful.<br>2. User should not be authenticated.<br>3. Appropriate login failure feedback should be displayed.<br>4. The application should not establish an authenticated state for the invalid identifier. | Not Executed | **P0** | **NOT RUN** | --- |
| **TC_LOGIN_005** | **(TS-002) Login Functionality** | **Validate login rejection when the correct username is provided with an incorrect password** | 1. Application is accessible.<br>2. A registered QA account is available.<br>3. The correct username is known.<br>4. An incorrect password is available. | 1. Open the Login functionality.<br>2. Enter the valid registered username.<br>3. Enter an incorrect password.<br>4. Submit the login form.<br>5. Observe the result. | Valid registered username + incorrect password. | 1. Login should fail.<br>2. User should not be authenticated.<br>3. Appropriate authentication failure feedback should be displayed.<br>4. No authenticated session should be established. | Not Executed | **P0** | **NOT RUN** | --- |
| **TC_LOGIN_006** | **(TS-002) Login Functionality** | **Validate login rejection when the correct email is provided with an incorrect password** | 1. Application is accessible.<br>2. A registered QA account is available.<br>3. The correct email is known.<br>4. An incorrect password is available. | 1. Open the Login functionality.<br>2. Enter the valid registered email address.<br>3. Enter an incorrect password.<br>4. Submit the login form.<br>5. Observe the result. | Valid registered email + incorrect password. | 1. Login should fail.<br>2. User should not be authenticated.<br>3. Appropriate authentication failure feedback should be displayed.<br>4. No authenticated session should be established. | Not Executed | **P0** | **NOT RUN** | --- |
| **TC_LOGIN_007** | **(TS-002) Login Functionality** | **Validate login behavior when the username/email field is empty** | 1. Application is accessible.<br>2. Login functionality is available. | 1. Open the Login functionality.<br>2. Leave the username/email field empty.<br>3. Enter a password where applicable.<br>4. Submit the login form.<br>5. Observe the validation response. | Empty username/email + password value. | 1. Login should not be completed.<br>2. Required-field validation should be displayed where applicable.<br>3. The application should not authenticate the user. | Not Executed | **P1** | **NOT RUN** | --- |
| **TC_LOGIN_008** | **(TS-002) Login Functionality** | **Validate login behavior when the password field is empty** | 1. Application is accessible.<br>2. Login functionality is available.<br>3. A registered QA username or email is available. | 1. Open the Login functionality.<br>2. Enter a valid registered username or email.<br>3. Leave the password field empty.<br>4. Submit the login form.<br>5. Observe the validation response. | Valid registered username/email + empty password. | 1. Login should not be completed.<br>2. Required password validation should be displayed where applicable.<br>3. The application should not authenticate the user. | Not Executed | **P1** | **NOT RUN** | --- |
| **TC_LOGIN_009** | **(TS-002) Login Functionality** | **Validate login behavior when both username/email and password are empty** | 1. Application is accessible.<br>2. Login functionality is available. | 1. Open the Login functionality.<br>2. Leave the username/email field empty.<br>3. Leave the password field empty.<br>4. Submit the login form.<br>5. Observe the validation response. | Empty username/email + empty password. | 1. Login should not be submitted successfully.<br>2. Appropriate required-field validation should be displayed.<br>3. No authenticated state should be established. | Not Executed | **P1** | **NOT RUN** | --- |
| **TC_LOGIN_010** | **(TS-002) Login Functionality** | **Validate login using an invalid email format** | 1. Application is accessible.<br>2. Login functionality is available.<br>3. A valid password is available. | 1. Open the Login functionality.<br>2. Enter an email value that does not satisfy the application's accepted email format.<br>3. Enter a password.<br>4. Submit the login form.<br>5. Observe the validation response. | Invalid-format email + password. | 1. Invalid email input should be rejected or prevented from successful authentication where email-format validation applies.<br>2. Appropriate validation feedback should be displayed.<br>3. User should not be authenticated. | Not Executed | **P1** | **NOT RUN** | --- |
| **TC_LOGIN_011** | **(TS-002) Login Functionality** | **Validate login using an unregistered username** | 1. Application is accessible.<br>2. Login functionality is available.<br>3. An unregistered QA test identifier is available. | 1. Open the Login functionality.<br>2. Enter an unregistered username.<br>3. Enter a password.<br>4. Submit the login form.<br>5. Observe the response. | Unregistered username + password. | 1. Login should fail.<br>2. User should not be authenticated.<br>3. Appropriate authentication failure feedback should be displayed. | Not Executed | **P0** | **NOT RUN** | --- |
| **TC_LOGIN_012** | **(TS-002) Login Functionality** | **Validate login using an unregistered email address** | 1. Application is accessible.<br>2. Login functionality is available.<br>3. An unregistered QA email address is available. | 1. Open the Login functionality.<br>2. Enter an unregistered email address.<br>3. Enter a password.<br>4. Submit the login form.<br>5. Observe the response. | Unregistered email + password. | 1. Login should fail.<br>2. User should not be authenticated.<br>3. Appropriate authentication failure feedback should be displayed. | Not Executed | **P0** | **NOT RUN** | --- |
| **TC_LOGIN_013** | **(TS-002) Login Functionality** | **Validate login form presentation and availability** | 1. Application is accessible.<br>2. Browser is available. | 1. Open the 4xcollection application.<br>2. Navigate to the Login functionality.<br>3. Inspect the login form.<br>4. Verify the username/email input.<br>5. Verify the password input.<br>6. Verify the login submission control.<br>7. Inspect the overall form presentation. | Not Applicable | 1. Login functionality should load successfully.<br>2. Required login controls should be displayed.<br>3. Username/email and password inputs should be usable.<br>4. Login submission control should be available.<br>5. No obvious UI issue should prevent login. | Not Executed | **P1** | **NOT RUN** | --- |
| **TC_LOGIN_014** | **(TS-002) Login Functionality** | **Validate successful authentication state after login** | 1. Application is accessible.<br>2. A valid registered QA account is available.<br>3. Valid username/email and password are known. | 1. Open the Login functionality.<br>2. Enter the correct registered username or email.<br>3. Enter the correct password.<br>4. Submit the login form.<br>5. Navigate or interact with the application as an authenticated user.<br>6. Observe the resulting authentication state. | Valid registered username or email + correct password. | 1. User should be authenticated successfully.<br>2. Application should reflect the authenticated state.<br>3. Protected/authenticated functionality should behave according to the application's implemented access rules.<br>4. Authentication should persist for the active session according to the implementation. | Not Executed | **P0** | **NOT RUN** | --- |
| **TC_LOGIN_015** | **(TS-002) Login Functionality** | **Validate that unsuccessful login does not establish an authenticated state** | 1. Application is accessible.<br>2. A registered QA account is available.<br>3. An invalid login combination is available. | 1. Open the Login functionality.<br>2. Enter an incorrect username/email or incorrect password.<br>3. Submit the login form.<br>4. Observe the response.<br>5. Attempt to access functionality that requires authentication. | Invalid username/email or incorrect password. | 1. Login should fail.<br>2. No authenticated state should be established.<br>3. Protected functionality should not incorrectly treat the user as authenticated.<br>4. Appropriate login failure behavior should be displayed. | Not Executed | **P0** | **NOT RUN** | --- |
| **TC_LOGIN_016** | **(TS-002) Login Functionality** | **Validate login error handling when authentication cannot be completed** | 1. Application is accessible.<br>2. Login functionality is available.<br>3. A reproducible authentication failure condition is available for testing. | 1. Open the Login functionality.<br>2. Enter appropriate QA test data.<br>3. Execute the login under the reproducible failure condition.<br>4. Observe the application response.<br>5. Verify the resulting authentication state. | QA test credentials and a safely reproducible login failure condition. | 1. Authentication failure should be handled gracefully.<br>2. Application should provide an appropriate error response/message.<br>3. Application should not incorrectly indicate successful login.<br>4. No unauthorized authenticated state should be established. | Not Executed | **P1** | **NOT RUN** | --- |
| **TC_LOGIN_017** | **(TS-002) Login Functionality** | **Validate login after correcting previously invalid credentials** | 1. Application is accessible.<br>2. A valid QA account is available.<br>3. Correct credentials are known. | 1. Open the Login functionality.<br>2. Enter an invalid username/email or password.<br>3. Submit the login form.<br>4. Observe the failure response.<br>5. Replace the invalid credential with the correct registered username or email and correct password.<br>6. Submit the login form again.<br>7. Observe the result. | Initially invalid credentials followed by correct registered username/email + correct password. | 1. Initial invalid credentials should fail authentication.<br>2. Corrected credentials should be accepted.<br>3. Successful authentication should occur after valid credentials are submitted.<br>4. Previous validation/error state should not incorrectly prevent successful login. | Not Executed | **P1** | **NOT RUN** | --- |
| **TC_LOGIN_018** | **(TS-002) Login Functionality** | **Validate login behavior after repeated submission of valid credentials** | 1. Application is accessible.<br>2. A valid QA account is available.<br>3. Correct credentials are known. | 1. Open the Login functionality.<br>2. Enter the correct registered username or email.<br>3. Enter the correct password.<br>4. Submit the login form.<br>5. Repeat the submission where the application permits it.<br>6. Observe the resulting authentication state. | Correct registered username/email + correct password submitted repeatedly. | 1. Repeated valid login attempts should be handled correctly.<br>2. The application should maintain a consistent authenticated state.<br>3. No incorrect error or duplicate account behavior should result from repeated login submission. | Not Executed | **P1** | **NOT RUN** | --- |

---

# 5. Test Case Classification

| Test Type | Test Cases |
|---|---|
| **Functional** | TC_LOGIN_001, TC_LOGIN_002, TC_LOGIN_014, TC_LOGIN_017, TC_LOGIN_018 |
| **Negative** | TC_LOGIN_003, TC_LOGIN_004, TC_LOGIN_005, TC_LOGIN_006, TC_LOGIN_007, TC_LOGIN_008, TC_LOGIN_009, TC_LOGIN_010, TC_LOGIN_011, TC_LOGIN_012, TC_LOGIN_015, TC_LOGIN_016, TC_LOGIN_017, TC_LOGIN_018 |
| **UI** | TC_LOGIN_013 |
| **Authentication** | TC_LOGIN_001 -- TC_LOGIN_018, where applicable |
| **Regression Candidate** | TC_LOGIN_001 -- TC_LOGIN_018 |

---

# 6. Login Credential Rules

The following rule is critical for this test suite:

### Successful Login

A user should be able to authenticate when:

```text
Registered Username + Correct Password
                    OR
Registered Email + Correct Password
```

### Failed Login

Authentication should not succeed when:

```text
Incorrect Username + Correct Password
Incorrect Email + Correct Password
Correct Username + Incorrect Password
Correct Email + Incorrect Password
Unregistered Username + Password
Unregistered Email + Password
Missing Username/Email
Missing Password
Invalid Email Format
```

This distinction is important because **username and email are alternative login identifiers**, while the password must also be correct.

---

# 7. Test Data Rules

Because testing is performed against the production/live environment:

1. Use dedicated QA accounts.
2. Use QA-owned credentials.
3. Do not intentionally use real customer credentials.
4. Maintain valid username, email, and password combinations for approved QA accounts.
5. Maintain invalid/unregistered identifiers specifically for negative testing.
6. Do not place actual passwords in this Markdown document.
7. Store sensitive test credentials in an appropriate protected test-data mechanism.

---

# 8. Execution Result Rules

| Result | Definition |
|---|---|
| **PASS** | Actual behavior matches the expected result |
| **FAIL** | Actual behavior does not match the expected result |
| **BLOCKED** | Execution cannot proceed because of a dependency |
| **NOT RUN** | Test case has not been executed |

All test cases in this document initially have:

**Result: NOT RUN**

---

# 9. Defect Traceability

If a login test case fails and the failure is confirmed as an application defect:

```text
Test Plan
    ↓
TS-002 — Login Functionality
    ↓
TC_LOGIN_XXX
    ↓
FAIL
    ↓
BUG-XXX
```

The actual defect ID must be added after defect creation. No defect ID is fabricated in this document.

---

# 10. Automation Mapping

The project uses **Playwright + TypeScript**.

Login is a critical customer workflow and is therefore a high-priority automation candidate.

| Test Case | Automation Status |
|---|---|
| TC_LOGIN_001 | Automation Planned |
| TC_LOGIN_002 | Automation Planned |
| TC_LOGIN_003 | Automation Planned |
| TC_LOGIN_004 | Automation Planned |
| TC_LOGIN_005 | Automation Planned |
| TC_LOGIN_006 | Automation Planned |
| TC_LOGIN_007 | Automation Planned |
| TC_LOGIN_008 | Automation Planned |
| TC_LOGIN_009 | Automation Planned |
| TC_LOGIN_010 | Automation Planned |
| TC_LOGIN_011 | Automation Planned |
| TC_LOGIN_012 | Automation Planned |
| TC_LOGIN_013 | Automation Planned |
| TC_LOGIN_014 | Automation Planned |
| TC_LOGIN_015 | Automation Planned |
| TC_LOGIN_016 | Automation Planned |
| TC_LOGIN_017 | Automation Planned |
| TC_LOGIN_018 | Automation Planned |

**Current automation status:** No login test case is claimed as already automated.

---

# 11. Traceability Matrix

| Requirement / Feature | Test Scenario | Test Cases |
|---|---|---|
| Login using registered username | TS-002 | TC_LOGIN_001, TC_LOGIN_003, TC_LOGIN_005, TC_LOGIN_011, TC_LOGIN_014, TC_LOGIN_015 |
| Login using registered email | TS-002 | TC_LOGIN_002, TC_LOGIN_004, TC_LOGIN_006, TC_LOGIN_010, TC_LOGIN_012, TC_LOGIN_014, TC_LOGIN_015 |
| Login validation | TS-002 | TC_LOGIN_007, TC_LOGIN_008, TC_LOGIN_009, TC_LOGIN_010 |
| Authentication state | TS-002 | TC_LOGIN_001, TC_LOGIN_002, TC_LOGIN_014, TC_LOGIN_015 |
| Login error handling | TS-002 | TC_LOGIN_003 -- TC_LOGIN_006, TC_LOGIN_011, TC_LOGIN_012, TC_LOGIN_016 |
| Login UI | TS-002 | TC_LOGIN_013 |

---

# 12. Execution History

Execution history should be maintained separately for each execution cycle so that reusable test-case definitions are not overwritten.

| Execution Cycle | Test Case Range | Result | Executed By | Date | Evidence |
|---|---|---|---|---|---|
| Not Executed | TC_LOGIN_001 -- TC_LOGIN_018 | Not Run | --- | --- | --- |

---

# 13. Review Checklist

Before execution, verify:

- [ ] Login functionality is accessible.
- [ ] Dedicated QA account is available.
- [ ] Valid username is available.
- [ ] Valid email is available.
- [ ] Correct password is available.
- [ ] Invalid/unregistered username test data is available.
- [ ] Invalid/unregistered email test data is available.
- [ ] Incorrect password test data is available.
- [ ] Required login validation behavior is confirmed.
- [ ] Test cases have been reviewed.
- [ ] Production test-data policy is being followed.
- [ ] No real customer credentials are intentionally used.

---

# 14. Summary

| Metric | Value |
|---|---|
| **Test Scenario** | TS-002 |
| **Feature** | Login |
| **Total Test Cases** | **18** |
| **P0 Test Cases** | **8** |
| **P1 Test Cases** | **10** |
| **Current Result** | Not Run |
| **Current Automated Test Cases** | **0** |
| **Automation Planned** | Yes |

---

## Document Status

| Field | Value |
|---|---|
| **Document** | 4xcollection --- Login Test Cases |
| **Version** | 1.0 |
| **Status** | Draft |
| **Reference** | Test Plan |
| **Scenario** | TS-002 --- Validate the working of Login functionality |
| **QA Owner** | Ashok Budha |

**End of Document**
