# Defect Reports Log

**Project:** OrangeHRM – Manual Testing Project  
**Author:** Pranali (QA Engineer Fresher)  
**Total Defects Logged:** 6 (5 Open, 1 Closed/Retested)  

---

### [BUG_EMP_001] Employee search by Employee Name fails when trailing whitespace is present in search input
- **Module:** Employee Management (PIM)
- **Environment:** Windows 11 / Chrome v128 / OrangeHRM 5.x Demo
- **Severity:** **Medium** | **Priority:** **Medium** | **Status:** `Open`
- **Reproducibility:** Always (100%)
- **Associated Test Case:** `TC_EMP_009`
- **Preconditions:** Employee 'Pranali Test' exists in the PIM Employee List.
- **Steps to Reproduce:**  
  1. Navigate to PIM > Employee List.<br>2. In the Employee Name input box, type 'Pranali ' (with a trailing space character).<br>3. Click the 'Search' button.
- **Expected Result:** System should trim leading and trailing whitespace automatically and return the matching record for 'Pranali Test'.
- **Actual Result:** System displays 'No Records Found' toast notification because trailing whitespace is not sanitized prior to search lookup.
- **Evidence Reference:** `BUG_EMP_001_trailing_space_search.png`
- **Comments:** Observed during manual exploratory testing. Affects user experience when copying and pasting names.

---
### [BUG_LEAVE_001] Leave Date picker allows manual typing of past dates without immediate validation warning
- **Module:** Leave Management
- **Environment:** Windows 11 / Chrome v128 / OrangeHRM 5.x Demo
- **Severity:** **Medium** | **Priority:** **Medium** | **Status:** `Open`
- **Reproducibility:** Always (100%)
- **Associated Test Case:** `TC_LEAVE_002`
- **Preconditions:** User is on the Leave > Apply page.
- **Steps to Reproduce:**  
  1. Select a valid Leave Type.<br>2. Manually type a past date '2023-01-01' into From Date field.<br>3. Type '2023-01-02' into To Date field.<br>4. Click 'Apply' button.
- **Expected Result:** System should immediately validate date fields and alert the user that leave cannot be requested for historical dates.
- **Actual Result:** System does not validate past dates on client-side; form attempts submission and fails with a generic error banner.
- **Evidence Reference:** `BUG_LEAVE_001_past_date_warning.png`
- **Comments:** Past date validation logic should be handled with explicit error messaging on the UI.

---
### [BUG_REC_001] Resume file upload allows double extension files (e.g., 'resume.pdf.doc') without explicit extension check
- **Module:** Recruitment
- **Environment:** Windows 11 / Chrome v128 / OrangeHRM 5.x Demo
- **Severity:** **Low** | **Priority:** **Low** | **Status:** `Open`
- **Reproducibility:** Always (100%)
- **Associated Test Case:** `TC_REC_008`
- **Preconditions:** User is on Recruitment > Add Candidate page.
- **Steps to Reproduce:**  
  1. Fill required candidate fields (Name, Email).<br>2. Under Resume, select a file named 'sample_resume.pdf.doc'.<br>3. Click 'Save' button.
- **Expected Result:** System should strictly parse file extensions and verify MIME type before accepting multi-extension files.
- **Actual Result:** System accepts the file attachment based solely on the final extension without MIME validation.
- **Evidence Reference:** `BUG_REC_001_double_extension.png`
- **Comments:** Minor security risk; file MIME-type verification recommended.

---
### [BUG_LOGIN_001] Password input allows pasting plain text containing leading spaces without input sanitation warning
- **Module:** Login
- **Environment:** Windows 11 / Edge v128 / OrangeHRM 5.x Demo
- **Severity:** **Low** | **Priority:** **Low** | **Status:** `Closed (Simulated)`
- **Reproducibility:** Always (100%)
- **Associated Test Case:** `TC_LOGIN_002`
- **Preconditions:** User is on the login page.
- **Steps to Reproduce:**  
  1. Copy ' admin123' (with a leading space) to clipboard.<br>2. Paste into the Password field.<br>3. Enter 'Admin' in Username.<br>4. Click 'Login'.
- **Expected Result:** System should either warn user about leading/trailing space in password or clarify authentication failure cause.
- **Actual Result:** System displays generic 'Invalid credentials' banner without any indication of inadvertent whitespace.
- **Evidence Reference:** `BUG_LOGIN_001_password_space.png`
- **Comments:** Retested in simulated cycle; verified standard behavior aligns with security best practices.

---
### [BUG_EMP_002] Employee ID leading zeros stripped in table view causing visual discrepancy with search input
- **Module:** Employee Management (PIM)
- **Environment:** Windows 11 / Chrome v128 / OrangeHRM 5.x Demo
- **Severity:** **Low** | **Priority:** **Low** | **Status:** `Open`
- **Reproducibility:** Always (100%)
- **Associated Test Case:** `TC_EMP_007`
- **Preconditions:** Add employee with ID '0089'.
- **Steps to Reproduce:**  
  1. Navigate to PIM > Add Employee.<br>2. Enter names and specify Employee ID as '0089'.<br>3. Click 'Save'.<br>4. Search for '0089' in Employee List.
- **Expected Result:** Employee record in table should retain formatted leading zeros ('0089') as entered.
- **Actual Result:** System strips leading zeros and renders ID as '89' in certain list views, requiring search for '89'.
- **Evidence Reference:** `BUG_EMP_002_leading_zeros.png`
- **Comments:** Cosmetic/formatting defect in string handling.

---
### [BUG_REC_002] Candidate search by Vacancy does not reset results count text until full page reload
- **Module:** Recruitment
- **Environment:** Windows 11 / Chrome v128 / OrangeHRM 5.x Demo
- **Severity:** **Low** | **Priority:** **Low** | **Status:** `Open`
- **Reproducibility:** Intermittent (50%)
- **Associated Test Case:** `TC_REC_011`
- **Preconditions:** User has performed a search in Recruitment > Candidates.
- **Steps to Reproduce:**  
  1. Search candidates by a vacancy that yields 2 records.<br>2. Click 'Reset' button.<br>3. Observe '(2) Records Found' header label.
- **Expected Result:** Records found counter should update dynamically to reflect total unfiltered candidate count upon clicking Reset.
- **Actual Result:** Table refreshes all records, but '(2) Records Found' label intermittently lags until manual browser reload.
- **Evidence Reference:** `BUG_REC_002_counter_lag.png`
- **Comments:** Minor UI synchronization issue in frontend state management.

---
