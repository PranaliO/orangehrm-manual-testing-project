# Test Design Techniques Applied: OrangeHRM

**Project:** OrangeHRM – Manual Testing Project  
**Author:** Pranali (QA Engineer Fresher)  
**Testing Methodology:** Black-Box Test Design Techniques  

---

## 1. Overview
Rather than writing test cases purely through intuition or repetitive guessing, test cases in this portfolio were systematically derived using industry-standard **Black-Box Test Design Techniques**:
1. **Boundary Value Analysis (BVA)**
2. **Equivalence Partitioning (EP)**
3. **Decision Table Testing**
4. **Error Guessing**

Applying these formal techniques ensures comprehensive test coverage across typical, edge, and erroneous system states while avoiding redundant test bloat.

---

## 2. Boundary Value Analysis (BVA)

Boundary Value Analysis focuses on testing the values at the boundaries of input domains (Minimum, Minimum - 1, Minimum + 1, Maximum - 1, Maximum, Maximum + 1), where software defects are statistically most likely to occur.

### BVA Application 1: Employee ID Field Length (PIM Module)
- **Field Rule:** OrangeHRM Employee ID is configured to accept between 1 and 10 alphanumeric characters.
- **Boundary Range:** $[1, 10]$ characters.

| Boundary Point | Value Tested | Test Data Input | Expected System Behavior | Test Case ID |
| :--- | :--- | :--- | :--- | :--- |
| **Min - 1 (0 chars)** | 0 characters | `""` (Empty string) | System auto-populates default incremental ID or requires input. | `TC_EMP_003` |
| **Min (1 char)** | 1 character | `"7"` | Value accepted; record created successfully. | `TC_EMP_008` |
| **Min + 1 (2 chars)**| 2 characters | `"45"` | Value accepted; record created successfully. | `TC_EMP_008` |
| **Max - 1 (9 chars)**| 9 characters | `"123456789"` | Value accepted; record created successfully. | `TC_EMP_008` |
| **Max (10 chars)** | 10 characters | `"1234567890"` | Value accepted; saved without truncation. | `TC_EMP_008` |
| **Max + 1 (11 chars)**| 11 characters | `"12345678901"`| Field prevents 11th keystroke or shows validation `"Should not exceed 10 characters"`. | `TC_EMP_008` |

---

### BVA Application 2: Leave Application Comments Field
- **Field Rule:** Comments textarea has a defined operational boundary of 250 characters.
- **Boundary Range:** $[0, 250]$ characters.

| Boundary Point | Value Tested | Test Data Input | Expected System Behavior | Test Case ID |
| :--- | :--- | :--- | :--- | :--- |
| **Min (0 chars)** | 0 characters | `""` (Empty) | Comments are optional; application submits successfully. | `TC_LEAVE_002` |
| **Max - 1 (249 chars)**| 249 characters | 249 alphanumeric characters | String accepted without warning. | `TC_LEAVE_007` |
| **Max (250 chars)** | 250 characters | 250 alphanumeric characters | String accepted; counter indicates 0 remaining. | `TC_LEAVE_007` |
| **Max + 1 (251 chars)**| 251 characters | 251 alphanumeric characters | Input blocked at 250 or error banner `"Should not exceed 250 characters"` displayed. | `TC_LEAVE_007` |

---

### BVA Application 3: Leave Duration Range (Start Date vs End Date)
- **Field Rule:** Leave duration must be at least 1 calendar day; End Date must be greater than or equal to Start Date.

| Boundary Point | Value Tested | Condition | Expected System Behavior | Test Case ID |
| :--- | :--- | :--- | :--- | :--- |
| **Boundary (Min = 1 Day)** | From Date = To Date | `2026-10-25` to `2026-10-25` | Valid 1-day leave duration accepted and recorded. | `TC_LEAVE_006` |
| **Boundary (Min - 1 Day)** | To Date < From Date | `2026-10-20` to `2026-10-19` | System triggers validation: `"To date should be after from date"`. | `TC_LEAVE_005` |
| **Multi-Day (> 1 Day)** | To Date > From Date | `2026-10-15` to `2026-10-16` | Multi-day leave (2 days) calculated and submitted. | `TC_LEAVE_002` |

---

## 3. Equivalence Partitioning (EP)

Equivalence Partitioning divides input data into valid and invalid partitions such that testing one representative value from a partition is considered equivalent to testing all values within that class.

### EP Matrix 1: Candidate Email Syntax (Recruitment Module)

| Field | Partition Type | Partition Description | Representative Test Data | Expected System Behavior | Test Case ID |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Email** | **Valid Partition 1** | Standard format (`user@domain.com`) | `ananya.iyer@testqa.com` | Accepted; passes syntax check. | `TC_REC_002` |
| **Email** | **Valid Partition 2** | Subdomain & special symbols (`user.name+tag@sub.domain.org`) | `valid.candidate_01@sub.domain.org` | Accepted; passes syntax check. | `TC_REC_007` |
| **Email** | **Invalid Partition 1**| Missing `@` symbol | `invalidemailformat.com` | Rejected; `"Expected format: admin@example.com"`. | `TC_REC_006` |
| **Email** | **Invalid Partition 2**| Missing top-level domain (`.com`) | `candidate@domain` | Rejected; inline validation triggered. | `TC_REC_006` |
| **Email** | **Invalid Partition 3**| Missing username before `@` | `@example.com` | Rejected; inline validation triggered. | `TC_REC_006` |
| **Email** | **Invalid Partition 4**| Completely empty / blank string | `""` | Rejected; mandatory validation `"Required"` displayed. | `TC_REC_005` |

---

### EP Matrix 2: User Login Authentication Credentials

| Input Field | Partition Type | Partition Class | Representative Data | Expected Behavior | Test Case ID |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Username** | Valid | Registered Admin user | `Admin` | Accepted | `TC_LOGIN_001` |
| **Username** | Invalid | Unregistered string | `InvalidAdminUser` | Triggers `"Invalid credentials"` | `TC_LOGIN_003` |
| **Username** | Invalid | Empty string | `""` | Triggers inline `"Required"` | `TC_LOGIN_005` |
| **Password** | Valid | Correct registered password | `admin123` | Accepted | `TC_LOGIN_001` |
| **Password** | Invalid | Incorrect password string | `WrongPassword999` | Triggers `"Invalid credentials"` | `TC_LOGIN_002` |
| **Password** | Invalid | Empty string | `""` | Triggers inline `"Required"` | `TC_LOGIN_006` |

---

### EP Matrix 3: Candidate Resume Attachment File Formats

| Input Field | Partition Type | Partition Class | Representative Data | Expected Behavior | Test Case ID |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Resume File** | **Valid** | Document file (.pdf, .docx, .odt) < 1MB | `sample_resume.pdf` (250 KB) | File uploaded and attached. | `TC_REC_008` |
| **Resume File** | **Invalid 1** | Executable file extension (.exe, .bat) | `malicious_test.exe` | File rejected with format error. | `TC_REC_009` |
| **Resume File** | **Invalid 2** | Oversized document (> 1MB) | `large_portfolio.pdf` (5.2 MB) | Rejected with size limit error. | `TC_REC_008` |

---

## 4. Decision Table Testing

Decision Table Testing is used to test complex business logic and combinations of input conditions that result in distinct system actions.

### Decision Table 1: Leave Application Submission Logic
**Business Rule:** A leave request can be submitted if and only if a valid Leave Type is selected, From and To dates are entered, and the To Date is chronologically equal to or after the From Date.

| Rule / Condition | Rule 1 (R1) | Rule 2 (R2) | Rule 3 (R3) | Rule 4 (R4) | Rule 5 (R5) |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Condition 1 (C1):** Is Leave Type selected? | **Y** | **N** | **Y** | **Y** | **Y** |
| **Condition 2 (C2):** Are From Date & To Date entered? | **Y** | **Y** | **N** | **Y** | **Y** |
| **Condition 3 (C3):** Is To Date >= From Date? | **Y** | **Y** | **N/A** | **N** | **Y** |
| **Condition 4 (C4):** Is From Date = To Date (Single Day)? | **N** | **N** | **N/A** | **N** | **Y** |
| **Action 1 (A1):** Submit Multi-Day Leave Request | **X** | | | | |
| **Action 2 (A2):** Submit Single-Day (1.0 Day) Leave | | | | | **X** |
| **Action 3 (A3):** Display inline `"Required"` on Leave Type | | **X** | | | |
| **Action 4 (A4):** Display inline `"Required"` on Date fields | | | **X** | | |
| **Action 5 (A5):** Display `"To date should be after from date"` | | | | **X** | |
| **Associated Test Case ID** | `TC_LEAVE_002` | `TC_LEAVE_003` | `TC_LEAVE_004` | `TC_LEAVE_005` | `TC_LEAVE_006` |

---

### Decision Table 2: Login Authentication Logic

| Conditions & Actions | R1 | R2 | R3 | R4 | R5 | R6 | R7 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Username entered?** | Y | Y | Y | N | Y | N | N |
| **Username correct (`Admin`)?** | Y | Y | N | N/A | Y | N/A | N/A |
| **Password entered?** | Y | Y | Y | Y | N | N | N |
| **Password correct (`admin123`)?** | Y | N | Y | N/A | N/A | N/A | N/A |
| **Action: Navigate to Dashboard** | **X** | | | | | | |
| **Action: Display `"Invalid credentials"`** | | **X** | **X** | | | | |
| **Action: Display `"Required"` under Username** | | | | **X** | | **X** | **X** |
| **Action: Display `"Required"` under Password** | | | | | **X** | **X** | **X** |
| **Mapped Test Case ID** | `TC_LOGIN_001` | `TC_LOGIN_002` | `TC_LOGIN_003` | `TC_LOGIN_005` | `TC_LOGIN_006` | `TC_LOGIN_007` | `TC_LOGIN_007` |

---

## 5. Error Guessing

Error Guessing is an experience-based, proactive testing technique where the tester anticipates common user mistakes, system edge conditions, and failure-prone operations.

| # | Error Guessing Scenario | Anticipated Risk / Potential Defect | Applied Test Case / Defect Log |
| :- | :--- | :--- | :--- |
| **EG-01** | User copies and pastes names with leading or trailing whitespace. | Autocomplete search fails to sanitize strings, showing false "No Records Found". | `TC_EMP_009` / `BUG_EMP_001` |
| **EG-02** | User attempts to submit leave with past historical dates. | Backend accepts past dates or crashes without clear frontend warning. | `TC_LEAVE_002` / `BUG_LEAVE_001` |
| **EG-03** | User rapidly double-clicks the "Save" or "Apply" button. | Duplicate records generated or server throws duplicate key constraint exception. | `TC_EMP_002`, `TC_LEAVE_002` |
| **EG-04** | User attaches file with double extension (`resume.pdf.exe`). | Upload filter checks only the first extension and permits malicious executable upload. | `TC_REC_009` / `BUG_REC_001` |
| **EG-05** | User clicks the browser Back button immediately after logging out. | Cached authenticated session reveals sensitive employee dashboard data. | `TC_LOGIN_011` |
| **EG-06** | User fills an extensive form and accidentally clicks "Cancel" instead of "Save". | Modal confirmation missing, causing silent data loss. | `TC_EMP_015`, `TC_REC_013` |
