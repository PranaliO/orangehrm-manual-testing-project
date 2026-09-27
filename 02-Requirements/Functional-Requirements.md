# Functional Requirements Specification (FRS)

**Project:** OrangeHRM – Manual Testing Project  
**Author:** Pranali (QA Engineer Fresher)  
**Application Version:** OrangeHRM Open Source 5.x  
**Scope:** Login, Employee Management (PIM), Leave Management, Recruitment  

---

## 1. Document Overview
This document specifies the 22 functional requirements for the OrangeHRM Manual Testing project. Each requirement reflects actual features available on the public OrangeHRM Open Source demo instance and serves as the baseline for test scenario identification, test case design, and the Requirement Traceability Matrix (RTM).

---

## 2. Requirements Matrix

### 2.1 Module: Login & Session Management

| Requirement ID | Requirement Title | Requirement Description | Priority |
| :--- | :--- | :--- | :--- |
| **REQ_LOGIN_001** | Valid User Authentication | The system shall authenticate a user upon receiving a valid registered username (`Admin`) and password (`admin123`) and navigate the user to the application Dashboard (`/web/index.php/dashboard/index`). | High |
| **REQ_LOGIN_002** | Invalid Credentials Handling | The system shall reject login attempts containing invalid usernames, invalid passwords, or invalid username/password combinations, retaining the login page and displaying an alert banner: `Invalid credentials`. | High |
| **REQ_LOGIN_003** | Mandatory Credentials Validation | The system shall enforce mandatory inputs for both Username and Password fields; submitting the form with either or both fields blank shall prevent request submission and display an inline `Required` error message under each empty field. | High |
| **REQ_LOGIN_004** | Password Masking & Reset Link | The system shall mask password input characters with bullets/asterisks for security, and provide a functional `Forgot your password?` link that redirects the user to the password reset request page (`/web/index.php/auth/requestPasswordResetCode`). | Medium |
| **REQ_LOGIN_005** | User Logout & Session Invalidation | The system shall allow an authenticated user to log out via the user profile dropdown, terminate the active session, redirect to the login screen, and prevent unauthorized dashboard access when the browser Back button is clicked. | High |

---

### 2.2 Module: Employee Management (PIM)

| Requirement ID | Requirement Title | Requirement Description | Priority |
| :--- | :--- | :--- | :--- |
| **REQ_EMP_001** | Add New Employee Record | The system shall allow authorized users to add an employee record by entering First Name (mandatory), Middle Name (optional), Last Name (mandatory), and Employee ID (auto-generated or custom alphanumeric), persisting the record on clicking `Save`. | High |
| **REQ_EMP_002** | Add Employee Mandatory Validation | The system shall validate mandatory fields on the Add Employee form; leaving First Name or Last Name blank upon clicking `Save` shall prevent record creation and display inline `Required` validation messages. | High |
| **REQ_EMP_003** | Employee Search & Filtering | The system shall allow searching employee records in the Employee List by Employee Name (with autocomplete suggestions) or Employee ID, and display matching records in the results table upon clicking `Search`. | High |
| **REQ_EMP_004** | View & Edit Employee Information | The system shall allow viewing an employee's personal details by clicking on their record in the Employee List and permit editing personal fields (e.g., Other ID, License Number, Nickname), saving changes upon clicking `Save`. | Medium |
| **REQ_EMP_005** | Employee Record Deletion | The system shall provide an option to delete an employee record from the Employee List with a mandatory confirmation modal (`The selected record will be permanently deleted. Are you sure you want to continue?`) before permanent deletion. | High |
| **REQ_EMP_006** | Cancel Employee Operation | The system shall provide a `Cancel` button on Add Employee and Edit Employee forms that dismisses the operation and navigates the user back to the Employee List without saving uncommitted changes. | Medium |

---

### 2.3 Module: Leave Management

| Requirement ID | Requirement Title | Requirement Description | Priority |
| :--- | :--- | :--- | :--- |
| **REQ_LEAVE_001** | Leave Application Submission | The system shall permit users to submit a leave request by selecting an active Leave Type, specifying valid From Date and To Date, optionally entering comments, and submitting via the `Apply` button. | High |
| **REQ_LEAVE_002** | Leave Mandatory Field Validation | The system shall enforce mandatory selection of Leave Type, From Date, and To Date; attempting to apply with any required field omitted shall display inline `Required` validation messages and prevent submission. | High |
| **REQ_LEAVE_003** | Chronological Date Validation | The system shall enforce date sequence rules such that the `To Date` cannot precede the `From Date`. Selecting an end date earlier than the start date shall display a validation error message (`To date should be after from date`). | High |
| **REQ_LEAVE_004** | Leave List Filter & Status Display | The system shall allow users to search and filter leave records in the Leave List by Date Range, Leave Type, and Status (e.g., Pending Approval, Scheduled, Taken, Cancelled), displaying matching records in the data grid. | Medium |
| **REQ_LEAVE_005** | Leave Request Cancellation | The system shall allow users to cancel an unsubmitted leave application via the `Cancel` button or cancel a pending leave request from the Leave List data grid where allowed by business workflow. | Medium |

---

### 2.4 Module: Recruitment

| Requirement ID | Requirement Title | Requirement Description | Priority |
| :--- | :--- | :--- | :--- |
| **REQ_REC_001** | Add Candidate Profile | The system shall allow authorized users to add a candidate by entering First Name (mandatory), Middle Name (optional), Last Name (mandatory), Vacancy selection, and Email (mandatory), saving the candidate upon clicking `Save`. | High |
| **REQ_REC_002** | Candidate Mandatory & Email Validation | The system shall enforce mandatory First Name, Last Name, and Email fields, and validate email syntax to ensure standard email format (`username@domain.extension`), displaying an error message if invalid. | High |
| **REQ_REC_003** | Candidate Resume File Upload | The system shall allow attaching candidate resume documents in supported formats (`.pdf`, `.docx`, `.doc`, `.odt`) within size limits (up to 1MB) and display appropriate warnings if unsupported file types are selected. | Medium |
| **REQ_REC_004** | Candidate Search & Filter | The system shall allow searching and filtering candidate records in the Candidates directory by Job Vacancy, Candidate Name, Keywords, and Date of Application. | High |
| **REQ_REC_005** | Candidate Application Workflow | The system shall allow updating candidate status through supported recruitment stages (e.g., transitioning from `Application Initiated` to `Shortlisted` or `Rejected`) with optional notes. | Medium |
| **REQ_REC_006** | Cancel Candidate Operation | The system shall provide a `Cancel` button on the Add Candidate form that aborts candidate entry and navigates back to the Candidates directory without persisting uncommitted data. | Low |

---

## 3. Requirement Traceability Summary
- **Total Functional Requirements:** 22
  - Login Module: 5 Requirements
  - Employee Management (PIM): 6 Requirements
  - Leave Management: 5 Requirements
  - Recruitment Module: 6 Requirements
- Every requirement defined above is mapped directly to Test Scenarios (`03-Test-Design/Test-Scenarios.xlsx`) and Test Cases (`03-Test-Design/Test-Cases.xlsx`) in the Requirement Traceability Matrix (`06-RTM/Requirement-Traceability-Matrix.xlsx`).
