# Test Data Matrix

**Project:** OrangeHRM – Manual Testing Project  
**Author:** Pranali (QA Engineer Fresher)  

| Test Data ID | Module | Data Category | Test Data Input | Description / Rule | Target Test Purpose |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `TD_LOGIN_01` | Login | Valid Credentials | `Username: Admin | Password: admin123` | Valid registered credentials | Positive Login |
| `TD_LOGIN_02` | Login | Invalid Password | `Username: Admin | Password: WrongPassword999` | Incorrect password | Negative Login |
| `TD_LOGIN_03` | Login | Invalid Username | `Username: InvalidAdminUser | Password: admin123` | Unregistered username | Negative Login |
| `TD_LOGIN_04` | Login | Both Invalid | `Username: FakeUser99 | Password: FakePassword99` | Unregistered username & password | Negative Login |
| `TD_LOGIN_05` | Login | Blank Username | `Username: [BLANK] | Password: admin123` | Empty username string | Field Validation |
| `TD_LOGIN_06` | Login | Blank Password | `Username: Admin | Password: [BLANK]` | Empty password string | Field Validation |
| `TD_LOGIN_07` | Login | Both Blank | `Username: [BLANK] | Password: [BLANK]` | Both inputs empty | Field Validation |
| `TD_LOGIN_08` | Login | Case Variation | `Username: admin | Password: admin123` | Lowercase username | Equivalence Partitioning |
| `TD_EMP_01` | Employee Management | Valid Full Details | `First: Pranali, Middle: QA, Last: Test, ID: 9812` | Standard valid employee | Positive Add Employee |
| `TD_EMP_02` | Employee Management | Mandatory Only | `First: Rohan, Middle: [BLANK], Last: Sharma, ID: Auto` | Omit optional middle name | Positive Add Employee |
| `TD_EMP_03` | Employee Management | Blank First Name | `First: [BLANK], Middle: Kumar, Last: Verma` | Missing mandatory First Name | Negative Validation |
| `TD_EMP_04` | Employee Management | Blank Last Name | `First: Priya, Middle: [BLANK], Last: [BLANK]` | Missing mandatory Last Name | Negative Validation |
| `TD_EMP_05` | Employee Management | Custom Alphanumeric ID | `First: Amit, Last: Patel, ID: EMP2026A` | Alphanumeric Employee ID | Positive ID Format |
| `TD_EMP_06` | Employee Management | BVA ID Length Min/Max | `ID: 1 char ('1'), 10 chars ('1234567890'), 11 chars ('12345678901')` | Boundary limits for ID field | Boundary Value Analysis |
| `TD_EMP_07` | Employee Management | Search Existing Name | `Employee Name: Pranali Test` | Registered active employee name | Positive Search |
| `TD_EMP_08` | Employee Management | Search Non-Existent | `Employee Name: NonExistentPersonZZZ999` | String with zero matches | Negative Search |
| `TD_EMP_09` | Employee Management | Edit Details | `Nickname: PranuQA, Other ID: OTH7788` | Valid personal details update | Positive Edit |
| `TD_LEAVE_01` | Leave Management | Valid Multi-day Leave | `Type: Vacation, From: 2026-10-15, To: 2026-10-16, Comment: Personal` | Standard future multi-day | Positive Apply |
| `TD_LEAVE_02` | Leave Management | Single Day Leave | `Type: Vacation, From: 2026-10-25, To: 2026-10-25 (Same date)` | Boundary single date (1 day) | Boundary Value Positive |
| `TD_LEAVE_03` | Leave Management | Blank Leave Type | `Type: [NONE / --Select--], From: 2026-10-15, To: 2026-10-16` | Unselected mandatory dropdown | Negative Validation |
| `TD_LEAVE_04` | Leave Management | Blank Dates | `Type: Vacation, From: [BLANK], To: [BLANK]` | Missing start/end dates | Negative Validation |
| `TD_LEAVE_05` | Leave Management | Invalid Chronology | `Type: Vacation, From: 2026-10-20, To: 2026-10-10` | To date earlier than From date | Negative Date Logic |
| `TD_LEAVE_06` | Leave Management | Comment Limit BVA | `Comment: 250 characters vs 255 characters` | Boundary limit on textarea | BVA Textarea |
| `TD_LEAVE_07` | Leave Management | Leave List Search Dates | `From: 2026-01-01, To: 2026-12-31` | Full calendar year filter | Positive Filter |
| `TD_REC_01` | Recruitment | Valid Candidate | `First: Ananya, Last: Iyer, Email: ananya.iyer@testqa.com, Vacancy: Active, Contact: 9876543210` | Standard candidate profile | Positive Candidate |
| `TD_REC_02` | Recruitment | Blank Mandatory Fields | `First: [BLANK], Last: [BLANK], Email: [BLANK]` | Missing required candidate data | Negative Validation |
| `TD_REC_03` | Recruitment | Invalid Email Syntax | `Email: invalidemailformat.com (No @ or domain)` | Malformed email string | EP Negative |
| `TD_REC_04` | Recruitment | Valid Complex Email | `Email: valid.candidate_01@sub.domain.org` | Sub-domain and underscore email | EP Positive |
| `TD_REC_05` | Recruitment | Valid Resume File | `sample_resume.pdf (Size 250 KB)` | Permitted PDF document | Positive File Upload |
| `TD_REC_06` | Recruitment | Invalid File Extension | `malicious_test.exe` | Disallowed executable format | Negative File Upload |
| `TD_REC_07` | Recruitment | Workflow Shortlist Note | `Notes: Candidate shortlisted for screening` | Recruitment stage comments | Positive Workflow |
