# Test Plan: OrangeHRM Manual Testing Project

**Document Version:** 1.0  
**Author:** Pranali (QA Engineer Fresher / Manual Tester)  
**Date:** September 2026  
**Status:** Approved for Execution  
**Project:** OrangeHRM Open-Source Web Application Testing  

---

## 1. Introduction
This Test Plan describes the manual testing strategy, scope, resources, environment, and deliverables for verifying key functionalities of the **OrangeHRM** web application (Open-Source version 5.x). 

This project is a personal Manual Testing portfolio initiative designed to demonstrate practical Software Testing Life Cycle (STLC) stages—including requirement analysis, test design techniques (BVA, Equivalence Partitioning, Decision Tables), test execution planning, defect reporting, regression planning, and Requirement Traceability Matrix (RTM) maintenance.

> **Note on Testing Approach:**  
> This project is designed and documented **strictly using Manual Testing methodologies**. No automated test tools, scripts, or CI/CD frameworks such as Selenium, Playwright, Cypress, TestNG, Cucumber, or Appium are utilized.

---

## 2. Objective
The primary objectives of this testing effort are:
- Verify that core human resource management workflows operate according to documented functional expectations.
- Validate authentication mechanisms and security UI behaviors (such as password masking and session logout).
- Ensure input validations prevent bad, incomplete, or boundary-violating data from corrupting system state.
- Identify, isolate, and document reproducible functional defects with precise severity, priority, and reproduction steps.
- Maintain complete bidirectional traceability from requirements to test scenarios, test cases, and defects.
- Validate that previous features remain unbroken during retesting and regression testing cycles.

---

## 3. Application Under Test (AUT)
- **Application Name:** OrangeHRM Open Source (Demo Instance)
- **Version:** OrangeHRM 5.x
- **Application Type:** Web-based Enterprise Human Resource Management (HRM) System
- **Public Demo URL:** `https://opensource-demo.orangehrmlive.com/web/index.php/auth/login`
- **Default Test Credentials:**
  - **Username:** `Admin`
  - **Password:** `admin123`

---

## 4. Scope

### 4.1 In-Scope
Manual functional, UI, positive, negative, and workflow testing of four core modules:
1. **Login & Session Management:** Valid/invalid authentication, blank field validations, password masking, logout, session security.
2. **Employee Management (PIM):** Adding employees, mandatory field validations, employee search, viewing profile details, editing personal details, record deletion, and record persistence.
3. **Leave Management:** Applying for leave, date range validations, leave type selections, comments, partial day configurations, leave list filtering, and cancel operations.
4. **Recruitment:** Adding candidates, vacancy associations, email syntax validations, resume upload checks, candidate search, profile view, and application workflow status transitions.

### 4.2 Out-of-Scope
- Performance, Load, and Stress Testing (JMeter, Locust, etc.).
- Automated Scripting (Selenium, Cypress, Playwright, etc.).
- Direct backend Database/API access (no direct MySQL access or Postman integration; testing is conducted purely via web UI).
- Unselected modules: Admin/User Management, Time/Timesheets, Performance/KPIs, Payroll, Directory, Buzz, Maintenance.
- Mobile native application testing (iOS/Android native apps).
- Multi-tenant enterprise cloud configurations.

---

## 5. Modules Under Test

| Module Name | Key Sub-features Tested |
| :--- | :--- |
| **01. Login** | Login form rendering, valid login, invalid login (wrong user/pass), blank fields, password masking, forgot password link navigation, user dropdown menu, logout redirection, session back-navigation. |
| **02. Employee Management (PIM)** | PIM navigation, Add Employee (First, Middle, Last, Employee ID), mandatory field checks, duplicate ID handling, Employee List search (by name & ID), Edit employee details, Save, Cancel, Delete employee with modal confirmation. |
| **03. Leave Management** | Apply Leave form, Leave Type selection, From Date and To Date pickers, chronological date validations (To date before From date), Comments field, Apply submission, Leave List search/filter by status and date range, Cancel leave request. |
| **04. Recruitment** | Candidates tab, Add Candidate form, mandatory fields (First Name, Last Name, Email), Email format validation, Contact number validation, Resume attachment, Candidate search by vacancy/name, Candidate status progression (Application Initiated to Shortlisted/Rejected). |

---

## 6. Testing Approach & Strategy
Testing is conducted strictly manually through black-box testing methodologies:
1. **Requirement Analysis:** Understand OrangeHRM web behavior and derive 22 precise functional requirements.
2. **Test Design:** Formulate 32 high-level Test Scenarios and design 56 comprehensive Test Cases utilizing:
   - **Boundary Value Analysis (BVA)**
   - **Equivalence Partitioning (EP)**
   - **Decision Table Testing**
   - **Error Guessing**
3. **Execution Rounds:**
   - **Smoke Testing Suite (10 test cases):** Verifies basic build stability before detailed testing.
   - **Functional & UI Execution Suite (56 test cases):** Comprehensive verification of all positive and negative conditions.
   - **Defect Logging & Retesting:** Formal logging of defects in standard defect format and retesting after simulated or real fixes.
   - **Regression Suite (14 test cases):** Critical path tests rerun to ensure modifications do not introduce secondary defects.
   - **Exploratory Testing:** Time-boxed unscripted charters to uncover edge cases.

---

## 7. Testing Types

| Testing Type | Description & Purpose in Project |
| :--- | :--- |
| **Functional Testing** | Verifies that every feature behaves strictly in conformance with functional requirements. |
| **Smoke Testing** | A subset of 10 high-priority test cases run on the login, dashboard, and modules to verify application stability. |
| **Sanity Testing** | Focused verification performed on a specific module/fix to confirm whether a reported defect has been resolved before executing wider tests. |
| **Positive Testing** | Validating system behavior with valid, expected inputs (happy path). |
| **Negative Testing** | Validating error handling, validation banners, and system resistance against invalid or missing inputs. |
| **Boundary Value Analysis** | Testing values at boundaries (Min-1, Min, Min+1, Max-1, Max, Max+1) on length-limited fields. |
| **Equivalence Partitioning** | Partitioning valid and invalid input sets (e.g., email syntax, date ranges). |
| **UI Validation** | Verifying alignment, button visibility, field labels, typography, clear error indicators, and responsive rendering. |
| **Regression Testing** | Rerunning 14 core functional test cases across affected modules after changes. |
| **Retesting** | Re-executing failed test cases specifically associated with reported defect fixes. |
| **Exploratory Testing** | Time-boxed 45-minute charter session exploring edge behaviors without rigid step constraints. |
| **Cross-Browser Compatibility** | Verifying consistency across major desktop browsers (Google Chrome and Microsoft Edge). |

---

## 8. Test Environment

| Component | Specification |
| :--- | :--- |
| **Operating System** | Microsoft Windows 11 (64-bit) |
| **Primary Browser** | Google Chrome |
| **Secondary Browser** | Microsoft Edge |
| **Screen Resolution** | 1920 x 1080 (Full HD, 100% display scaling) |
| **Network** | Broadband Internet (50+ Mbps stable connection) |
| **Test Documentation Tools** | Microsoft Excel / Markdown editors / Git & GitHub |

---

## 9. Test Data Strategy
Test data is systematically organized in `03-Test-Design/Test-Data.xlsx` covering:
- **Valid Data Sets:** Standard employee names, official demo credentials, legitimate email strings, valid upcoming date ranges.
- **Negative Data Sets:** Empty strings, leading/trailing whitespaces, special character injections (`<script>`, `#@$%^&*`), alphanumeric employee IDs exceeding boundaries.
- **Date Boundary Sets:** Past dates, identical start and end dates, end dates preceding start dates.
- **File Upload Sets:** Valid resume formats (`.pdf`, `.docx`) under 1MB vs. unsupported formats (`.exe`, `.mp4`) and oversized files (>1MB).

---

## 10. Entry Criteria
Testing commences only when the following criteria are satisfied:
1. OrangeHRM demo instance is publicly accessible and responsive via HTTP/HTTPS.
2. Demo administrator credentials (`Admin` / `admin123`) permit successful login.
3. Test Plan, Functional Requirements, and Test Cases are documented and reviewed.
4. Test environment and browsers are configured and verified.

---

## 11. Exit Criteria
Testing concludes when:
1. 100% of planned test cases (56 test cases) have been formally executed and recorded.
2. All discovered defects are documented with clear steps, screenshots, severity, and priority.
3. 100% of Critical and High severity defects are either verified, tracked, or assigned clear status.
4. Requirement Traceability Matrix (RTM) shows 100% requirement coverage.
5. Test Execution Report and Test Summary Report are finalized.

---

## 12. Assumptions
- The public demo instance of OrangeHRM maintains stable uptime during testing sessions.
- Default demo data (existing employees, leave types, vacancies) remains sufficiently intact without erratic external resets during active test rounds.
- All testing activities are purely manual through the standard web browser interface.

---

## 13. Risks and Mitigation

| Risk | Impact | Likelihood | Mitigation Strategy |
| :--- | :--- | :--- | :--- |
| **Public demo instance reset:** External users or automated nightly scripts might delete newly created test records. | High | Medium | Use distinct, identifiable test prefixes (e.g., `TestQA_Emp_01`, `qa_candidate_01@mail.com`). Record test evidence immediately upon execution. |
| **Network connectivity dropouts:** Intermittent internet issues could cause false positive timeouts or request drops. | Medium | Low | Verify internet stability before test runs; re-execute any suspicious timeout case before logging a defect. |
| **Unannounced demo server downtime:** OrangeHRM server maintenance may temporarily disable the site. | High | Low | Plan execution in modular chunks and resume testing when the demo server returns to normal operation. |
| **Dynamic data alteration by other users:** Simultaneous public users modifying shared records. | Medium | Medium | Avoid modifying default admin profile records; operate solely on newly generated test entities. |

---

## 14. Limitations
- Direct database query validation cannot be conducted because the public demo server does not provide external MySQL connection access.
- Email delivery (SMTP notifications for leave approval or candidate emails) cannot be verified in the public sandbox.
- System administrator configurations (LDAP integration, email server setup) are outside manual testing capabilities on shared demo environments.

---

## 15. Deliverables

| Deliverable Name | File Location | Purpose |
| :--- | :--- | :--- |
| **Test Plan** | `01-Project-Documentation/Test-Plan.md` | Strategic framework for the test project. |
| **Scope & Objectives** | `01-Project-Documentation/Scope-and-Objectives.md` | Clear boundary and goal definitions. |
| **Test Environment** | `01-Project-Documentation/Test-Environment.md` | Hardware, software, and browser setup. |
| **Functional Requirements** | `02-Requirements/Functional-Requirements.md` | 22 functional specifications. |
| **Test Scenarios** | `03-Test-Design/Test-Scenarios.xlsx` | 32 high-level test scenarios. |
| **Test Cases** | `03-Test-Design/Test-Cases.xlsx` | 56 detailed manual test cases. |
| **Test Data Matrix** | `03-Test-Design/Test-Data.xlsx` | Complete test data inputs. |
| **Test Design Techniques** | `03-Test-Design/Test-Design-Techniques.md` | BVA, EP, Decision Tables, Error Guessing. |
| **Test Execution Report** | `04-Test-Execution/Test-Execution-Report.xlsx` | Step-by-step execution tracking. |
| **Execution Summary** | `04-Test-Execution/Execution-Summary.md` | Smoke, Sanity, Regression, & Retesting. |
| **Bug Reports** | `05-Defect-Management/Bug-Reports.xlsx` | Formatted defect tracking sheet. |
| **Defect Summary** | `05-Defect-Management/Defect-Summary.md` | Defect analysis, lifecycle, and severity/priority. |
| **Requirement Traceability Matrix**| `06-RTM/Requirement-Traceability-Matrix.xlsx` | Bidirectional requirement-to-test mapping. |
| **Test Summary Report** | `07-Test-Summary/Test-Summary-Report.md` | Final evaluation and test metrics report. |
| **Project README** | `README.md` | GitHub portfolio homepage. |
