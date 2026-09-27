# Test Scenarios Specification

**Project:** OrangeHRM – Manual Testing Project  
**Author:** Pranali (QA Engineer Fresher)  
**Total Scenarios:** 32  

| Scenario ID | Requirement ID | Module | Test Scenario Description | Priority | Test Type |
| :--- | :--- | :--- | :--- | :---: | :--- |
| `TS_LOGIN_001` | `REQ_LOGIN_001` | Login | Verify login functionality with valid username and valid password | **High** | Positive / Functional |
| `TS_LOGIN_002` | `REQ_LOGIN_002` | Login | Verify login error handling with invalid credentials (invalid username or password) | **High** | Negative |
| `TS_LOGIN_003` | `REQ_LOGIN_003` | Login | Verify mandatory field validation when username or password fields are left blank | **High** | Negative / Validation |
| `TS_LOGIN_004` | `REQ_LOGIN_004` | Login | Verify password masking for character privacy in the password input field | **Medium** | Security-UI |
| `TS_LOGIN_005` | `REQ_LOGIN_004` | Login | Verify navigation and page rendering of 'Forgot your password?' link | **Medium** | Navigation / Functional |
| `TS_LOGIN_006` | `REQ_LOGIN_005` | Login | Verify user logout functionality from top-right user profile dropdown menu | **High** | Positive / Functional |
| `TS_LOGIN_007` | `REQ_LOGIN_005` | Login | Verify session termination and browser back-button behavior after logout | **High** | Security / Session |
| `TS_EMP_001` | `REQ_EMP_001` | Employee Management | Verify navigation to PIM module and rendering of Add Employee form | **High** | Navigation / UI |
| `TS_EMP_002` | `REQ_EMP_001` | Employee Management | Verify adding an employee record with valid mandatory and optional details | **High** | Positive / Functional |
| `TS_EMP_003` | `REQ_EMP_002` | Employee Management | Verify mandatory field validation when First Name or Last Name is left blank | **High** | Negative / Validation |
| `TS_EMP_004` | `REQ_EMP_001` | Employee Management | Verify boundary value length constraints on Employee ID field | **Medium** | Boundary Value Analysis |
| `TS_EMP_005` | `REQ_EMP_003` | Employee Management | Verify searching employee records using valid Employee Name with autocomplete | **High** | Positive / Functional |
| `TS_EMP_006` | `REQ_EMP_003` | Employee Management | Verify searching employee records using valid Employee ID | **High** | Positive / Functional |
| `TS_EMP_007` | `REQ_EMP_003` | Employee Management | Verify search behavior when querying with non-existent employee name or ID | **Medium** | Negative |
| `TS_EMP_008` | `REQ_EMP_004` | Employee Management | Verify viewing and editing existing employee personal details and saving updates | **High** | Positive / Functional |
| `TS_EMP_009` | `REQ_EMP_005` | Employee Management | Verify deleting an employee record from Employee List with confirmation dialog | **High** | Positive / Workflow |
| `TS_EMP_010` | `REQ_EMP_006` | Employee Management | Verify cancelling Add and Edit employee operations without saving changes | **Medium** | UI / Navigation |
| `TS_LEAVE_001` | `REQ_LEAVE_001` | Leave Management | Verify navigation to Leave module and rendering of Apply Leave form | **High** | Navigation / UI |
| `TS_LEAVE_002` | `REQ_LEAVE_001` | Leave Management | Verify submitting leave application with valid leave type and forward date range | **High** | Positive / Functional |
| `TS_LEAVE_003` | `REQ_LEAVE_002` | Leave Management | Verify mandatory field validation when required leave fields are omitted | **High** | Negative / Validation |
| `TS_LEAVE_004` | `REQ_LEAVE_003` | Leave Management | Verify chronological date validation when To Date is earlier than From Date | **High** | Boundary / Negative |
| `TS_LEAVE_005` | `REQ_LEAVE_001` | Leave Management | Verify applying for single-day leave where From Date equals To Date | **Medium** | Boundary / Positive |
| `TS_LEAVE_006` | `REQ_LEAVE_004` | Leave Management | Verify searching and filtering leave records in Leave List by status and dates | **High** | Positive / Functional |
| `TS_LEAVE_007` | `REQ_LEAVE_005` | Leave Management | Verify cancelling a leave request and verifying state in Leave List | **Medium** | Workflow |
| `TS_REC_001` | `REQ_REC_001` | Recruitment | Verify navigation to Recruitment module and rendering of Add Candidate form | **High** | Navigation / UI |
| `TS_REC_002` | `REQ_REC_001` | Recruitment | Verify adding candidate record with valid mandatory details and vacancy selection | **High** | Positive / Functional |
| `TS_REC_003` | `REQ_REC_002` | Recruitment | Verify validation when mandatory candidate fields (Name, Email) are missing | **High** | Negative / Validation |
| `TS_REC_004` | `REQ_REC_002` | Recruitment | Verify email address format validation on Add Candidate form | **High** | Equivalence Partitioning / Negative |
| `TS_REC_005` | `REQ_REC_003` | Recruitment | Verify candidate resume file upload with supported and unsupported file formats | **Medium** | Functional / Validation |
| `TS_REC_006` | `REQ_REC_004` | Recruitment | Verify searching candidate records in Candidates directory by name and vacancy | **High** | Positive / Functional |
| `TS_REC_007` | `REQ_REC_005` | Recruitment | Verify recruitment application stage progression (Shortlist / Reject) | **High** | Business Rule / Workflow |
| `TS_REC_008` | `REQ_REC_006` | Recruitment | Verify cancelling Add Candidate operation and returning to Candidates directory | **Low** | UI / Navigation |
