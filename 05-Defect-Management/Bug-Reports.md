# Defect Reports Log

**Project:** OrangeHRM – Manual Testing Project  
**Author:** Pranali (QA Engineer Fresher)  
**Total Defects Logged:** 6 (Confirmed Defects: 2, Exploratory Findings: 3, Simulated Defect: 1)  
**Status Distribution:** 5 Open, 1 Closed (Simulated Retest)  

---

### [BUG_EMP_001] Employee search by Employee Name fails when trailing whitespace is present in search input
- **Classification:** `Confirmed Defect`
- **Module:** Employee Management (PIM)
- **Environment:** Windows 11 / Chrome v128 / OrangeHRM 5.x Public Demo
- **Preconditions:** Active employee 'Pranali Test' exists in PIM Employee List.
- **Test Data:** `Employee Name: "Pranali " (with trailing whitespace)`
- **Steps to Reproduce:**  
  1. Navigate to PIM > Employee List.<br>2. In Employee Name search input box, type 'Pranali ' (with a trailing space).<br>3. Click 'Search' button.
- **Expected Result:** System should trim leading and trailing whitespace automatically and retrieve the matching record for 'Pranali Test'.
- **Actual Result:** System queries literal string with space, fails to resolve autocomplete entry, and displays 'No Records Found'.
- **Severity:** **Medium** | **Priority:** **Medium** | **Status:** `Open`
- **Reproducibility:** Always (100%)
- **Associated Test Case:** `TC_EMP_009`
- **Evidence Reference:** `BUG_EMP_001_trailing_space_search.png`
- **Comments:** Observed during manual exploratory testing. Affects real users who copy-paste names with accidental whitespace.

---
### [BUG_LEAVE_001] Leave Date picker allows manual entry of past dates without immediate validation warning
- **Classification:** `Confirmed Defect`
- **Module:** Leave Management
- **Environment:** Windows 11 / Chrome v128 / OrangeHRM 5.x Public Demo
- **Preconditions:** User is logged in and on Leave > Apply page with allocated balance.
- **Test Data:** `Leave Type: "US - Vacation", From Date: "2023-01-01", To Date: "2023-01-02"`
- **Steps to Reproduce:**  
  1. Select active Leave Type.<br>2. Manually enter past date '2023-01-01' into From Date field.<br>3. Manually enter past date '2023-01-02' into To Date field.<br>4. Click 'Apply' button.
- **Expected Result:** System should validate date chronology against current system date and trigger inline warning: 'Leave cannot be applied for past dates'.
- **Actual Result:** UI accepts past dates without client-side warning; submission attempts processing and returns generic server error banner.
- **Severity:** **Medium** | **Priority:** **Medium** | **Status:** `Open`
- **Reproducibility:** Always (100%)
- **Associated Test Case:** `TC_LEAVE_002`
- **Evidence Reference:** `BUG_LEAVE_001_past_date_warning.png`
- **Comments:** Client-side boundary validation missing on manual text entry for date picker fields.

---
### [BUG_REC_001] Resume file upload accepts double extension files (e.g., 'resume.pdf.doc') without explicit MIME-type verification
- **Classification:** `Exploratory Finding`
- **Module:** Recruitment
- **Environment:** Windows 11 / Chrome v128 / OrangeHRM 5.x Public Demo
- **Preconditions:** User is on Recruitment > Add Candidate page.
- **Test Data:** `File Name: "sample_resume.pdf.doc" (Size: 250 KB)`
- **Steps to Reproduce:**  
  1. Fill mandatory candidate fields (First Name, Last Name, Email).<br>2. Under Resume upload, select file named 'sample_resume.pdf.doc'.<br>3. Click 'Save' button.
- **Expected Result:** System should validate that file extensions are singular and verify file MIME type prior to acceptance.
- **Actual Result:** System accepts the file because it only inspects the terminal extension (.doc), bypassing compound extension checks.
- **Severity:** **Low** | **Priority:** **Low** | **Status:** `Open`
- **Reproducibility:** Always (100%)
- **Associated Test Case:** `TC_REC_008`
- **Evidence Reference:** `BUG_REC_001_double_extension.png`
- **Comments:** Security and file handling exploratory observation.

---
### [BUG_LOGIN_001] Password input allows pasting plain text containing leading spaces without input sanitation warning
- **Classification:** `Simulated Defect`
- **Module:** Login
- **Environment:** Windows 11 / Microsoft Edge v128 / OrangeHRM 5.x Public Demo
- **Preconditions:** User is on the login page.
- **Test Data:** `Username: "Admin", Password: " admin123" (with leading space)`
- **Steps to Reproduce:**  
  1. Copy ' admin123' (with leading space) to clipboard.<br>2. Paste into Password field.<br>3. Enter 'Admin' in Username and click 'Login'.
- **Expected Result:** Authentication should fail with standard message, but helper tooltip or trim behavior should guide user on whitespace.
- **Actual Result:** System displays generic 'Invalid credentials' banner; retested in cycle 2 to verify strict character preservation.
- **Severity:** **Low** | **Priority:** **Low** | **Status:** `Closed (Simulated Fix & Retest)`
- **Reproducibility:** Always (100%)
- **Associated Test Case:** `TC_LOGIN_002`
- **Evidence Reference:** `BUG_LOGIN_001_password_space.png`
- **Comments:** Simulated defect used to demonstrate full STLC Defect Lifecycle (New -> Open -> Fixed -> Retest -> Closed).

---
### [BUG_EMP_002] Employee ID leading zeros stripped in data table view causing visual discrepancy with search input
- **Classification:** `Exploratory Finding`
- **Module:** Employee Management (PIM)
- **Environment:** Windows 11 / Chrome v128 / OrangeHRM 5.x Public Demo
- **Preconditions:** Add employee with custom ID '0089'.
- **Test Data:** `Employee ID: "0089", Names: "Test", "LeadingZero"`
- **Steps to Reproduce:**  
  1. In PIM > Add Employee, enter names and Employee ID '0089'.<br>2. Click 'Save'.<br>3. In Employee List, search for '0089'.
- **Expected Result:** Employee List table should display ID formatted as '0089', preserving user-entered leading zeros.
- **Actual Result:** System strips leading zeros and renders ID as '89' in data table, requiring search query '89'.
- **Severity:** **Low** | **Priority:** **Low** | **Status:** `Open`
- **Reproducibility:** Always (100%)
- **Associated Test Case:** `TC_EMP_007`
- **Evidence Reference:** `BUG_EMP_002_leading_zeros.png`
- **Comments:** String versus integer datatype parsing discrepancy in UI table component.

---
### [BUG_REC_002] Candidate search by Vacancy does not reset results count text until full page reload
- **Classification:** `Exploratory Finding`
- **Module:** Recruitment
- **Environment:** Windows 11 / Chrome v128 / OrangeHRM 5.x Public Demo
- **Preconditions:** User has applied a search filter in Recruitment > Candidates.
- **Test Data:** `Job Vacancy filter: Active Vacancy -> Reset action`
- **Steps to Reproduce:**  
  1. Search candidates by vacancy that yields 2 records.<br>2. Click 'Reset' button.<br>3. Observe '(2) Records Found' counter text.
- **Expected Result:** Counter text should dynamically update to reflect total unfiltered candidate count upon clicking Reset.
- **Actual Result:** Data grid refreshes to display all candidates, but '(2) Records Found' text counter intermittently retains old count until page reload.
- **Severity:** **Low** | **Priority:** **Low** | **Status:** `Open`
- **Reproducibility:** Intermittent (50%)
- **Associated Test Case:** `TC_REC_011`
- **Evidence Reference:** `BUG_REC_002_counter_lag.png`
- **Comments:** Minor UI reactivity lag in Vue.js frontend state management.

---
