# Detailed Manual Test Cases (56 Cases)

**Project:** OrangeHRM – Manual Testing Project  
**Author:** Pranali (QA Engineer Fresher)  
**Total Test Cases:** 56  
**Execution Baseline Status:** Not Executed (Awaiting candidate live execution)  

---

### TC_LOGIN_001: Valid Login with Correct Admin Credentials
- **Requirement ID:** `REQ_LOGIN_001` | **Scenario ID:** `TS_LOGIN_001` | **Module:** Login
- **Priority:** **High** | **Test Type:** Positive / Functional
- **Objective:** Verify that a registered user can successfully log in using valid username and password.
- **Preconditions:** 1. OrangeHRM login page is loaded. 2. User is on the login page.
- **Test Data:** `Username: Admin, Password: admin123`
- **Execution Steps:**  
  1. Open browser and navigate to OrangeHRM URL.<br>2. Enter 'Admin' in the Username field.<br>3. Enter 'admin123' in the Password field.<br>4. Click the 'Login' button.
- **Expected Result:** User is authenticated successfully and redirected to the Dashboard page (/web/index.php/dashboard/index). User profile pill is displayed.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LOGIN_002: Login with Valid Username and Invalid Password
- **Requirement ID:** `REQ_LOGIN_002` | **Scenario ID:** `TS_LOGIN_002` | **Module:** Login
- **Priority:** **High** | **Test Type:** Negative
- **Objective:** Verify that authentication fails and an error banner is displayed when an invalid password is entered.
- **Preconditions:** 1. User is on the OrangeHRM login page.
- **Test Data:** `Username: Admin, Password: WrongPassword999`
- **Execution Steps:**  
  1. Enter 'Admin' in the Username field.<br>2. Enter 'WrongPassword999' in the Password field.<br>3. Click 'Login' button.
- **Expected Result:** System rejects login, retains user on login page, and displays red alert message: 'Invalid credentials'.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LOGIN_003: Login with Invalid Username and Valid Password
- **Requirement ID:** `REQ_LOGIN_002` | **Scenario ID:** `TS_LOGIN_002` | **Module:** Login
- **Priority:** **High** | **Test Type:** Negative
- **Objective:** Verify that authentication fails when an unregistered username is used with a valid password.
- **Preconditions:** 1. User is on the OrangeHRM login page.
- **Test Data:** `Username: InvalidAdminUser, Password: admin123`
- **Execution Steps:**  
  1. Enter 'InvalidAdminUser' in the Username field.<br>2. Enter 'admin123' in the Password field.<br>3. Click 'Login' button.
- **Expected Result:** System rejects login and displays alert message: 'Invalid credentials'. No dashboard access granted.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LOGIN_004: Login with Both Invalid Username and Invalid Password
- **Requirement ID:** `REQ_LOGIN_002` | **Scenario ID:** `TS_LOGIN_002` | **Module:** Login
- **Priority:** **High** | **Test Type:** Negative
- **Objective:** Verify that authentication is denied when both username and password are invalid.
- **Preconditions:** 1. User is on the OrangeHRM login page.
- **Test Data:** `Username: FakeUser99, Password: FakePassword99`
- **Execution Steps:**  
  1. Enter 'FakeUser99' in the Username field.<br>2. Enter 'FakePassword99' in the Password field.<br>3. Click 'Login' button.
- **Expected Result:** System rejects login and displays alert banner: 'Invalid credentials'.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LOGIN_005: Login with Blank Username and Valid Password
- **Requirement ID:** `REQ_LOGIN_003` | **Scenario ID:** `TS_LOGIN_003` | **Module:** Login
- **Priority:** **High** | **Test Type:** Negative / Validation
- **Objective:** Verify field-level validation when the username field is left blank.
- **Preconditions:** 1. User is on the OrangeHRM login page.
- **Test Data:** `Username: [BLANK], Password: admin123`
- **Execution Steps:**  
  1. Leave Username field completely empty.<br>2. Enter 'admin123' in the Password field.<br>3. Click 'Login' button.
- **Expected Result:** Form is not submitted. Red inline error text 'Required' is displayed beneath the Username field.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LOGIN_006: Login with Valid Username and Blank Password
- **Requirement ID:** `REQ_LOGIN_003` | **Scenario ID:** `TS_LOGIN_003` | **Module:** Login
- **Priority:** **High** | **Test Type:** Negative / Validation
- **Objective:** Verify field-level validation when the password field is left blank.
- **Preconditions:** 1. User is on the OrangeHRM login page.
- **Test Data:** `Username: Admin, Password: [BLANK]`
- **Execution Steps:**  
  1. Enter 'Admin' in the Username field.<br>2. Leave Password field completely empty.<br>3. Click 'Login' button.
- **Expected Result:** Form is not submitted. Red inline error text 'Required' is displayed beneath the Password field.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LOGIN_007: Login with Both Username and Password Blank
- **Requirement ID:** `REQ_LOGIN_003` | **Scenario ID:** `TS_LOGIN_003` | **Module:** Login
- **Priority:** **High** | **Test Type:** Negative / Validation
- **Objective:** Verify that leaving both credentials fields blank triggers validation for both fields.
- **Preconditions:** 1. User is on the OrangeHRM login page.
- **Test Data:** `Username: [BLANK], Password: [BLANK]`
- **Execution Steps:**  
  1. Ensure both Username and Password fields are empty.<br>2. Click 'Login' button.
- **Expected Result:** Form is not submitted. Red inline error text 'Required' is displayed beneath both Username and Password fields.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LOGIN_008: Password Field Character Masking Verification
- **Requirement ID:** `REQ_LOGIN_004` | **Scenario ID:** `TS_LOGIN_004` | **Module:** Login
- **Priority:** **Medium** | **Test Type:** Security-UI
- **Objective:** Verify that password characters are masked with bullets/dots as they are typed.
- **Preconditions:** 1. User is on the OrangeHRM login page.
- **Test Data:** `Password: admin123`
- **Execution Steps:**  
  1. Click on the Password input field.<br>2. Type 'admin123'.<br>3. Observe the rendered characters on the screen.
- **Expected Result:** Password characters are masked with bullet symbols (input type='password'). Plain text is not visible.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LOGIN_009: Verify 'Forgot your password?' Link Redirection
- **Requirement ID:** `REQ_LOGIN_004` | **Scenario ID:** `TS_LOGIN_005` | **Module:** Login
- **Priority:** **Medium** | **Test Type:** Navigation / Functional
- **Objective:** Verify that clicking 'Forgot your password?' navigates to the password reset request page.
- **Preconditions:** 1. User is on the OrangeHRM login page.
- **Test Data:** `N/A`
- **Execution Steps:**  
  1. Locate and click the 'Forgot your password?' link on the login card.<br>2. Observe the page URL and rendered form.
- **Expected Result:** User is redirected to '/web/index.php/auth/requestPasswordResetCode'. 'Reset Password' title and Username input field are displayed.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LOGIN_010: Successful Logout from User Profile Dropdown
- **Requirement ID:** `REQ_LOGIN_005` | **Scenario ID:** `TS_LOGIN_006` | **Module:** Login
- **Priority:** **High** | **Test Type:** Positive / Functional
- **Objective:** Verify that an authenticated user can successfully log out via the user profile dropdown.
- **Preconditions:** 1. User is logged in as Admin and on Dashboard.
- **Test Data:** `N/A`
- **Execution Steps:**  
  1. Click on the user profile dropdown icon in the top-right header.<br>2. Click on 'Logout' option from the dropdown menu.
- **Expected Result:** User session is terminated. User is redirected back to the Login page (/web/index.php/auth/login).
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LOGIN_011: Verify Session Invalidation via Browser Back Button after Logout
- **Requirement ID:** `REQ_LOGIN_005` | **Scenario ID:** `TS_LOGIN_007` | **Module:** Login
- **Priority:** **High** | **Test Type:** Security / Session
- **Objective:** Verify that clicking the browser back button after logout does not allow access to the protected dashboard.
- **Preconditions:** 1. User has performed a valid logout and is on the Login page.
- **Test Data:** `N/A`
- **Execution Steps:**  
  1. Perform logout as per TC_LOGIN_010.<br>2. Click the browser's 'Back' arrow button.
- **Expected Result:** Browser does not render authenticated dashboard data; page redirects or retains login view prompting authentication.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LOGIN_012: Username Case Sensitivity Verification
- **Requirement ID:** `REQ_LOGIN_001` | **Scenario ID:** `TS_LOGIN_001` | **Module:** Login
- **Priority:** **Medium** | **Test Type:** Equivalence Partitioning
- **Objective:** Verify whether username authentication is case-insensitive (e.g., 'admin' vs 'Admin').
- **Preconditions:** 1. User is on the OrangeHRM login page.
- **Test Data:** `Username: admin (all lowercase), Password: admin123`
- **Execution Steps:**  
  1. Enter 'admin' in lowercase in Username field.<br>2. Enter 'admin123' in Password field.<br>3. Click 'Login' button.
- **Expected Result:** System either accepts lowercase username or treats it uniformly, authenticating the user to the Dashboard.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_001: Verify PIM Module Navigation and Employee List Page Rendering
- **Requirement ID:** `REQ_EMP_001` | **Scenario ID:** `TS_EMP_001` | **Module:** Employee Management
- **Priority:** **High** | **Test Type:** Navigation / UI
- **Objective:** Verify that clicking PIM in the sidebar navigates to Employee List with proper search filters.
- **Preconditions:** 1. User is logged in as Admin.
- **Test Data:** `N/A`
- **Execution Steps:**  
  1. In the left navigation menu, click 'PIM'.<br>2. Observe page header and content area.
- **Expected Result:** PIM header is displayed. Employee Information search card is rendered with Employee Name, Employee Id, and Employee List table.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_002: Add New Employee with Valid Mandatory and Optional Fields
- **Requirement ID:** `REQ_EMP_001` | **Scenario ID:** `TS_EMP_002` | **Module:** Employee Management
- **Priority:** **High** | **Test Type:** Positive / Functional
- **Objective:** Verify that an employee can be successfully created with First Name, Middle Name, Last Name, and Employee ID.
- **Preconditions:** 1. User is logged in as Admin and navigated to PIM > Add Employee.
- **Test Data:** `First: Pranali, Middle: QA, Last: Test, Emp ID: 9812`
- **Execution Steps:**  
  1. Click 'Add Employee' tab in top navigation.<br>2. Enter 'Pranali' in First Name.<br>3. Enter 'QA' in Middle Name.<br>4. Enter 'Test' in Last Name.<br>5. Enter '9812' in Employee Id.<br>6. Click 'Save' button.
- **Expected Result:** System displays green success toast message ('Successfully Saved'). Employee Personal Details page loads with saved data.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_003: Add New Employee with Only Mandatory Fields
- **Requirement ID:** `REQ_EMP_001` | **Scenario ID:** `TS_EMP_002` | **Module:** Employee Management
- **Priority:** **High** | **Test Type:** Positive
- **Objective:** Verify employee creation when optional Middle Name is omitted.
- **Preconditions:** 1. User is on PIM > Add Employee page.
- **Test Data:** `First: Rohan, Middle: [BLANK], Last: Sharma, Emp ID: Auto`
- **Execution Steps:**  
  1. Enter 'Rohan' in First Name.<br>2. Leave Middle Name blank.<br>3. Enter 'Sharma' in Last Name.<br>4. Keep auto-generated Employee Id.<br>5. Click 'Save' button.
- **Expected Result:** Record is saved successfully. Toast message 'Successfully Saved' appears. Personal details page displays 'Rohan Sharma'.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_004: Add Employee with Blank First Name
- **Requirement ID:** `REQ_EMP_002` | **Scenario ID:** `TS_EMP_003` | **Module:** Employee Management
- **Priority:** **High** | **Test Type:** Negative / Validation
- **Objective:** Verify field validation when First Name is left blank on Add Employee form.
- **Preconditions:** 1. User is on PIM > Add Employee page.
- **Test Data:** `First: [BLANK], Middle: Kumar, Last: Verma`
- **Execution Steps:**  
  1. Leave First Name field empty.<br>2. Enter 'Kumar' in Middle Name.<br>3. Enter 'Verma' in Last Name.<br>4. Click 'Save' button.
- **Expected Result:** Form is not saved. Inline validation message 'Required' is displayed under First Name input box in red text.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_005: Add Employee with Blank Last Name
- **Requirement ID:** `REQ_EMP_002` | **Scenario ID:** `TS_EMP_003` | **Module:** Employee Management
- **Priority:** **High** | **Test Type:** Negative / Validation
- **Objective:** Verify field validation when Last Name is left blank on Add Employee form.
- **Preconditions:** 1. User is on PIM > Add Employee page.
- **Test Data:** `First: Priya, Middle: [BLANK], Last: [BLANK]`
- **Execution Steps:**  
  1. Enter 'Priya' in First Name.<br>2. Leave Last Name field empty.<br>3. Click 'Save' button.
- **Expected Result:** Form is not saved. Inline validation message 'Required' is displayed under Last Name input box.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_006: Add Employee with Both First Name and Last Name Blank
- **Requirement ID:** `REQ_EMP_002` | **Scenario ID:** `TS_EMP_003` | **Module:** Employee Management
- **Priority:** **High** | **Test Type:** Negative / Validation
- **Objective:** Verify validation behavior when both mandatory name fields are empty.
- **Preconditions:** 1. User is on PIM > Add Employee page.
- **Test Data:** `First: [BLANK], Last: [BLANK]`
- **Execution Steps:**  
  1. Leave First Name empty.<br>2. Leave Last Name empty.<br>3. Click 'Save' button.
- **Expected Result:** Form is not saved. Inline validation message 'Required' is displayed under both First Name and Last Name fields.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_007: Add Employee with Custom Alphanumeric Employee ID
- **Requirement ID:** `REQ_EMP_001` | **Scenario ID:** `TS_EMP_002` | **Module:** Employee Management
- **Priority:** **Medium** | **Test Type:** Positive
- **Objective:** Verify that Employee ID field accepts alphanumeric values.
- **Preconditions:** 1. User is on PIM > Add Employee page.
- **Test Data:** `First: Amit, Last: Patel, Emp ID: EMP2026A`
- **Execution Steps:**  
  1. Enter 'Amit' in First Name.<br>2. Enter 'Patel' in Last Name.<br>3. Clear auto ID and enter 'EMP2026A'.<br>4. Click 'Save' button.
- **Expected Result:** Record is saved successfully with custom alphanumeric ID 'EMP2026A'.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_008: Boundary Value Validation on Employee ID Field Length
- **Requirement ID:** `REQ_EMP_001` | **Scenario ID:** `TS_EMP_004` | **Module:** Employee Management
- **Priority:** **Medium** | **Test Type:** Boundary Value Analysis
- **Objective:** Verify system behavior when entering Employee ID at maximum boundary (10 chars) vs exceeding boundary (11+ chars).
- **Preconditions:** 1. User is on PIM > Add Employee page.
- **Test Data:** `First: TestBVA, Last: User, Emp ID: 1234567890 (10 chars) and 12345678901 (11 chars)`
- **Execution Steps:**  
  1. Enter valid names.<br>2. Enter 10-character ID '1234567890' -> Click Save.<br>3. Repeat with 11-character ID '12345678901' -> Observe validation or truncation.
- **Expected Result:** 10-character ID is accepted. 11+ characters either triggers 'Should not exceed 10 characters' validation or restricts input at 10 chars.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_009: Search Employee by Valid Full Employee Name
- **Requirement ID:** `REQ_EMP_003` | **Scenario ID:** `TS_EMP_005` | **Module:** Employee Management
- **Priority:** **High** | **Test Type:** Positive / Functional
- **Objective:** Verify that searching an existing employee by name retrieves the exact matching record.
- **Preconditions:** 1. User is on PIM > Employee List. 2. Employee 'Pranali Test' exists.
- **Test Data:** `Employee Name: Pranali`
- **Execution Steps:**  
  1. In Employee Name field, type 'Pranali'.<br>2. Select matching name from autocomplete dropdown.<br>3. Click 'Search' button.
- **Expected Result:** Table displays matching record showing Employee Id, First Name 'Pranali', and Last Name 'Test'. Records Found count equals 1.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_010: Search Employee by Valid Employee ID
- **Requirement ID:** `REQ_EMP_003` | **Scenario ID:** `TS_EMP_006` | **Module:** Employee Management
- **Priority:** **High** | **Test Type:** Positive / Functional
- **Objective:** Verify that searching by exact Employee ID retrieves the corresponding record.
- **Preconditions:** 1. User is on PIM > Employee List. 2. Employee with ID '9812' exists.
- **Test Data:** `Employee Id: 9812`
- **Execution Steps:**  
  1. Enter '9812' in the Employee Id field.<br>2. Click 'Search' button.
- **Expected Result:** Table filters to show only the employee record corresponding to ID '9812'.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_011: Search Employee with Non-Existent Employee Name
- **Requirement ID:** `REQ_EMP_003` | **Scenario ID:** `TS_EMP_007` | **Module:** Employee Management
- **Priority:** **Medium** | **Test Type:** Negative
- **Objective:** Verify system response when searching for an employee that does not exist in the database.
- **Preconditions:** 1. User is on PIM > Employee List.
- **Test Data:** `Employee Name: NonExistentPersonZZZ999`
- **Execution Steps:**  
  1. Type 'NonExistentPersonZZZ999' into Employee Name field.<br>2. Click 'Search' button.
- **Expected Result:** Results table displays 'No Records Found' toast notification or empty state text. No records shown in grid.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_012: Search Employee with Blank Criteria (Reset / All Search)
- **Requirement ID:** `REQ_EMP_003` | **Scenario ID:** `TS_EMP_005` | **Module:** Employee Management
- **Priority:** **Medium** | **Test Type:** Functional
- **Objective:** Verify that clicking Reset or Search with blank fields restores all employee records.
- **Preconditions:** 1. User has an active search filter applied on Employee List.
- **Test Data:** `Blank filters`
- **Execution Steps:**  
  1. Click 'Reset' button on the search card.<br>2. Observe search input fields and records table.
- **Expected Result:** All filter inputs are cleared. Complete list of all employees is reloaded in the data table.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_013: View Employee Personal Details Profile from Employee List
- **Requirement ID:** `REQ_EMP_004` | **Scenario ID:** `TS_EMP_008` | **Module:** Employee Management
- **Priority:** **High** | **Test Type:** Positive
- **Objective:** Verify that clicking on an employee row navigates to their Personal Details tab.
- **Preconditions:** 1. Employee List is displayed with records.
- **Test Data:** `Select record 'Pranali Test'`
- **Execution Steps:**  
  1. Click on the row or Edit (pencil icon) for 'Pranali Test'.<br>2. Observe loaded URL and view.
- **Expected Result:** Navigates to '/web/index.php/pim/viewPersonalDetails/empNumber/...'. Personal Details tab is active displaying employee profile.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_014: Edit and Save Existing Employee Information (Nickname & Other ID)
- **Requirement ID:** `REQ_EMP_004` | **Scenario ID:** `TS_EMP_008` | **Module:** Employee Management
- **Priority:** **High** | **Test Type:** Positive / Functional
- **Objective:** Verify that modifying employee personal details and clicking Save updates the record.
- **Preconditions:** 1. User is viewing Personal Details for an existing employee.
- **Test Data:** `Nickname: PranuQA, Other ID: OTH7788`
- **Execution Steps:**  
  1. Locate 'Nickname' field and enter 'PranuQA'.<br>2. Locate 'Other Id' field and enter 'OTH7788'.<br>3. Click 'Save' button in Personal Details section.
- **Expected Result:** Green notification 'Successfully Updated' appears. Updated values persist upon page refresh.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_015: Cancel Add Employee Operation and Verify Data Discard
- **Requirement ID:** `REQ_EMP_006` | **Scenario ID:** `TS_EMP_010` | **Module:** Employee Management
- **Priority:** **Medium** | **Test Type:** UI / Navigation
- **Objective:** Verify that clicking Cancel on Add Employee form discards inputs and returns to Employee List.
- **Preconditions:** 1. User is on Add Employee page with partially filled fields.
- **Test Data:** `First: Temporary, Last: User`
- **Execution Steps:**  
  1. Type 'Temporary' in First Name and 'User' in Last Name.<br>2. Click 'Cancel' button.<br>3. Search for 'Temporary User' in Employee List.
- **Expected Result:** User is redirected to Employee List. Record 'Temporary User' is not created.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_016: Delete Existing Employee Record with Modal Confirmation
- **Requirement ID:** `REQ_EMP_005` | **Scenario ID:** `TS_EMP_009` | **Module:** Employee Management
- **Priority:** **High** | **Test Type:** Positive / Workflow
- **Objective:** Verify that an employee can be permanently deleted after confirming the deletion modal.
- **Preconditions:** 1. Test employee exists in Employee List.
- **Test Data:** `Employee to delete: Rohan Sharma`
- **Execution Steps:**  
  1. Filter for 'Rohan Sharma' in Employee List.<br>2. Click the Delete (trash can) icon in the Actions column.<br>3. Verify confirmation modal popup appearance.<br>4. Click 'Yes, Delete' button in modal.
- **Expected Result:** Confirmation popup displays 'The selected record will be permanently deleted. Are you sure you want to continue?'. On clicking 'Yes, Delete', toast 'Successfully Deleted' is displayed.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_017: Cancel Delete Employee Record Confirmation Modal
- **Requirement ID:** `REQ_EMP_005` | **Scenario ID:** `TS_EMP_009` | **Module:** Employee Management
- **Priority:** **Medium** | **Test Type:** UI / Negative
- **Objective:** Verify that clicking 'No, Cancel' on the delete confirmation modal aborts deletion.
- **Preconditions:** 1. Test employee exists in Employee List.
- **Test Data:** `Employee: Pranali Test`
- **Execution Steps:**  
  1. Click Delete (trash can) icon for 'Pranali Test'.<br>2. On the modal popup, click 'No, Cancel' button.<br>3. Observe Employee List table.
- **Expected Result:** Modal closes. Employee record is NOT deleted and remains visible in the list.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_EMP_018: Verify Deleted Employee Record Does Not Appear in Search Results
- **Requirement ID:** `REQ_EMP_005` | **Scenario ID:** `TS_EMP_009` | **Module:** Employee Management
- **Priority:** **High** | **Test Type:** Regression / Persistence
- **Objective:** Verify that a deleted employee cannot be retrieved through search (persistence/integrity check).
- **Preconditions:** 1. Employee 'Rohan Sharma' was deleted in TC_EMP_016.
- **Test Data:** `Employee Name: Rohan Sharma`
- **Execution Steps:**  
  1. Navigate to PIM > Employee List.<br>2. Search for 'Rohan Sharma' in Employee Name.<br>3. Click 'Search'.
- **Expected Result:** Record is not returned. Table displays 'No Records Found'. Data persistence is verified.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LEAVE_001: Verify Navigation to Leave Module and Apply Leave Form Display
- **Requirement ID:** `REQ_LEAVE_001` | **Scenario ID:** `TS_LEAVE_001` | **Module:** Leave Management
- **Priority:** **High** | **Test Type:** Navigation / UI
- **Objective:** Verify that clicking 'Leave' in sidebar navigates to Leave section with top tabs visible.
- **Preconditions:** 1. User is logged in as Admin.
- **Test Data:** `N/A`
- **Execution Steps:**  
  1. Click 'Leave' in left navigation bar.<br>2. Click 'Apply' tab in top sub-header.<br>3. Observe Apply Leave card.
- **Expected Result:** Apply Leave form renders with Leave Type dropdown, From Date, To Date, Partial Days, Comments, and Apply button.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LEAVE_002: Submit Leave Application with Valid Leave Type and Upcoming Dates
- **Requirement ID:** `REQ_LEAVE_001` | **Scenario ID:** `TS_LEAVE_002` | **Module:** Leave Management
- **Priority:** **High** | **Test Type:** Positive / Functional
- **Objective:** Verify successful leave submission when valid leave type and valid forward dates are selected.
- **Preconditions:** 1. User is on Leave > Apply page with allocated leave balance.
- **Test Data:** `Leave Type: CAN - Vacation / US - Vacation, From: 2026-10-15, To: 2026-10-16, Comment: Annual personal leave`
- **Execution Steps:**  
  1. Select active Leave Type from dropdown.<br>2. Select '2026-10-15' in From Date.<br>3. Select '2026-10-16' in To Date.<br>4. Enter comment 'Annual personal leave'.<br>5. Click 'Apply' button.
- **Expected Result:** System saves leave request. Toast message 'Successfully Saved' appears or leave request transitions to Pending Approval.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LEAVE_003: Submit Leave Application with Blank Leave Type
- **Requirement ID:** `REQ_LEAVE_002` | **Scenario ID:** `TS_LEAVE_003` | **Module:** Leave Management
- **Priority:** **High** | **Test Type:** Negative / Validation
- **Objective:** Verify field validation when Leave Type is not selected on Apply Leave form.
- **Preconditions:** 1. User is on Leave > Apply page.
- **Test Data:** `Leave Type: -- Select --, From: 2026-10-15, To: 2026-10-16`
- **Execution Steps:**  
  1. Keep Leave Type as '-- Select --'.<br>2. Enter valid From Date and To Date.<br>3. Click 'Apply' button.
- **Expected Result:** Application is not submitted. Red validation message 'Required' is displayed under the Leave Type dropdown.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LEAVE_004: Submit Leave Application with Blank From Date and To Date
- **Requirement ID:** `REQ_LEAVE_002` | **Scenario ID:** `TS_LEAVE_003` | **Module:** Leave Management
- **Priority:** **High** | **Test Type:** Negative / Validation
- **Objective:** Verify mandatory validation when both date fields are left empty.
- **Preconditions:** 1. User is on Leave > Apply page.
- **Test Data:** `Leave Type: Valid Type, From: [BLANK], To: [BLANK]`
- **Execution Steps:**  
  1. Select valid Leave Type.<br>2. Clear From Date and To Date fields.<br>3. Click 'Apply' button.
- **Expected Result:** Application is not submitted. Red inline 'Required' errors display below From Date and To Date input fields.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LEAVE_005: Validate Error when To Date Precedes From Date
- **Requirement ID:** `REQ_LEAVE_003` | **Scenario ID:** `TS_LEAVE_004` | **Module:** Leave Management
- **Priority:** **High** | **Test Type:** Boundary / Negative
- **Objective:** Verify chronological date boundary validation when end date is earlier than start date.
- **Preconditions:** 1. User is on Leave > Apply page.
- **Test Data:** `Leave Type: Valid, From: 2026-10-20, To: 2026-10-10`
- **Execution Steps:**  
  1. Select valid Leave Type.<br>2. Enter '2026-10-20' in From Date.<br>3. Enter '2026-10-10' in To Date.<br>4. Click 'Apply' button or tab out of To Date.
- **Expected Result:** Inline validation message appears: 'To date should be after from date'. System prevents submission.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LEAVE_006: Apply Leave for a Single Day (From Date Equals To Date)
- **Requirement ID:** `REQ_LEAVE_001` | **Scenario ID:** `TS_LEAVE_005` | **Module:** Leave Management
- **Priority:** **Medium** | **Test Type:** Boundary / Positive
- **Objective:** Verify that system allows submitting a single-day leave request where From Date equals To Date.
- **Preconditions:** 1. User is on Leave > Apply page.
- **Test Data:** `Leave Type: Valid, From: 2026-10-25, To: 2026-10-25 (Same date)`
- **Execution Steps:**  
  1. Select valid Leave Type.<br>2. Set From Date to '2026-10-25'.<br>3. Set To Date to '2026-10-25'.<br>4. Click 'Apply' button.
- **Expected Result:** Leave application is accepted. Duration is calculated as 1.0 day without validation errors.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LEAVE_007: Apply Leave with Optional Comments Exceeding Character Limit
- **Requirement ID:** `REQ_LEAVE_001` | **Scenario ID:** `TS_LEAVE_002` | **Module:** Leave Management
- **Priority:** **Medium** | **Test Type:** BVA / Negative
- **Objective:** Verify system behavior when Comments textarea exceeds defined boundary (e.g. 250 characters).
- **Preconditions:** 1. User is on Leave > Apply page.
- **Test Data:** `Comment: String of 255 alphanumeric characters`
- **Execution Steps:**  
  1. Select Leave Type and valid dates.<br>2. In Comments field, enter a string containing 255 characters.<br>3. Observe character counter or validation indicator.
- **Expected Result:** System either restricts input to 250 characters or shows 'Should not exceed 250 characters' validation message.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LEAVE_008: Search Leave Records in Leave List by Valid Date Range
- **Requirement ID:** `REQ_LEAVE_004` | **Scenario ID:** `TS_LEAVE_006` | **Module:** Leave Management
- **Priority:** **High** | **Test Type:** Positive / Functional
- **Objective:** Verify that Leave List filters records correctly based on selected From Date and To Date.
- **Preconditions:** 1. User is on Leave > Leave List page.
- **Test Data:** `From: 2026-01-01, To: 2026-12-31`
- **Execution Steps:**  
  1. Enter '2026-01-01' in From Date.<br>2. Enter '2026-12-31' in To Date.<br>3. Click 'Search' button.
- **Expected Result:** Records table refreshes to show all leave records falling between the specified date boundaries.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LEAVE_009: Filter Leave List by Specific Leave Status (e.g., Pending Approval)
- **Requirement ID:** `REQ_LEAVE_004` | **Scenario ID:** `TS_LEAVE_006` | **Module:** Leave Management
- **Priority:** **Medium** | **Test Type:** Functional
- **Objective:** Verify filtering leave records by 'Pending Approval' status.
- **Preconditions:** 1. User is on Leave > Leave List page.
- **Test Data:** `Status: Pending Approval`
- **Execution Steps:**  
  1. In 'Show Leave with Status' multi-select, ensure only 'Pending Approval' is selected.<br>2. Click 'Search' button.
- **Expected Result:** All records displayed in the table show status badge 'Pending Approval'.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LEAVE_010: Filter Leave List by Specific Leave Type
- **Requirement ID:** `REQ_LEAVE_004` | **Scenario ID:** `TS_LEAVE_006` | **Module:** Leave Management
- **Priority:** **Medium** | **Test Type:** Functional
- **Objective:** Verify filtering leave records by a specific Leave Type dropdown option.
- **Preconditions:** 1. User is on Leave > Leave List page.
- **Test Data:** `Leave Type: US - Vacation (or CAN - Vacation)`
- **Execution Steps:**  
  1. Select 'US - Vacation' in Leave Type dropdown.<br>2. Click 'Search' button.
- **Expected Result:** Only records matching the selected Leave Type are displayed in the results table.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LEAVE_011: Search Leave List with Future Date Range Having No Records
- **Requirement ID:** `REQ_LEAVE_004` | **Scenario ID:** `TS_LEAVE_006` | **Module:** Leave Management
- **Priority:** **Medium** | **Test Type:** Negative
- **Objective:** Verify that searching a date range with no leave requests displays 'No Records Found'.
- **Preconditions:** 1. User is on Leave > Leave List page.
- **Test Data:** `From: 2030-01-01, To: 2030-01-05`
- **Execution Steps:**  
  1. Enter '2030-01-01' in From Date.<br>2. Enter '2030-01-05' in To Date.<br>3. Click 'Search' button.
- **Expected Result:** Results table displays 'No Records Found' empty state message.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LEAVE_012: Cancel Pending Leave Request from Leave List Grid
- **Requirement ID:** `REQ_LEAVE_005` | **Scenario ID:** `TS_LEAVE_007` | **Module:** Leave Management
- **Priority:** **High** | **Test Type:** Workflow
- **Objective:** Verify that a pending leave request can be cancelled from the Leave List Actions dropdown.
- **Preconditions:** 1. At least one Pending Approval leave request exists in Leave List.
- **Test Data:** `Action: Cancel`
- **Execution Steps:**  
  1. Filter Leave List to find Pending Approval request.<br>2. Click the three dots / Cancel action button for the record.<br>3. Confirm cancellation if prompt appears.
- **Expected Result:** Leave status updates to 'Cancelled'. Toast message confirms action.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_LEAVE_013: Cancel Leave Application Form Entry and Discard Input
- **Requirement ID:** `REQ_LEAVE_005` | **Scenario ID:** `TS_LEAVE_007` | **Module:** Leave Management
- **Priority:** **Low** | **Test Type:** UI / Navigation
- **Objective:** Verify that clicking Cancel or navigating away from Apply Leave discards uncommitted data.
- **Preconditions:** 1. User is on Apply Leave form with fields filled.
- **Test Data:** `Leave Type and Dates entered`
- **Execution Steps:**  
  1. Select Leave Type and enter dates.<br>2. Click 'My Leave' or sidebar menu item without clicking Apply.<br>3. Return to Apply tab.
- **Expected Result:** Form is reset to clean default state. No leave request is logged in the system.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_REC_001: Verify Navigation to Recruitment Module and Add Candidate Form Rendering
- **Requirement ID:** `REQ_REC_001` | **Scenario ID:** `TS_REC_001` | **Module:** Recruitment
- **Priority:** **High** | **Test Type:** Navigation / UI
- **Objective:** Verify that clicking 'Recruitment' navigates to Candidates tab and '+ Add' button opens Add Candidate form.
- **Preconditions:** 1. User is logged in as Admin.
- **Test Data:** `N/A`
- **Execution Steps:**  
  1. Click 'Recruitment' in left navigation bar.<br>2. Verify Candidates tab is active.<br>3. Click '+ Add' button.
- **Expected Result:** Add Candidate page opens (/web/index.php/recruitment/addCandidate) showing Full Name, Vacancy, Email, Contact Number, Resume file input, and Save button.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_REC_002: Add New Candidate with Valid Mandatory and Optional Fields
- **Requirement ID:** `REQ_REC_001` | **Scenario ID:** `TS_REC_002` | **Module:** Recruitment
- **Priority:** **High** | **Test Type:** Positive / Functional
- **Objective:** Verify that a candidate profile can be successfully created with valid data.
- **Preconditions:** 1. User is on Recruitment > Add Candidate page.
- **Test Data:** `First: Ananya, Middle: K, Last: Iyer, Vacancy: QA Lead / Software Engineer, Email: ananya.iyer@testqa.com, Contact: 9876543210`
- **Execution Steps:**  
  1. Enter 'Ananya' in First Name, 'K' in Middle Name, 'Iyer' in Last Name.<br>2. Select an active vacancy from Vacancy dropdown.<br>3. Enter 'ananya.iyer@testqa.com' in Email.<br>4. Enter '9876543210' in Contact Number.<br>5. Click 'Save' button.
- **Expected Result:** System displays 'Successfully Saved' toast. Candidate Application stage page loads displaying candidate profile and status 'Application Initiated'.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_REC_003: Add Candidate with Blank First Name
- **Requirement ID:** `REQ_REC_002` | **Scenario ID:** `TS_REC_003` | **Module:** Recruitment
- **Priority:** **High** | **Test Type:** Negative / Validation
- **Objective:** Verify mandatory validation when First Name is left blank on Add Candidate form.
- **Preconditions:** 1. User is on Recruitment > Add Candidate page.
- **Test Data:** `First: [BLANK], Last: Sen, Email: sen@testqa.com`
- **Execution Steps:**  
  1. Leave First Name blank.<br>2. Enter 'Sen' in Last Name.<br>3. Enter 'sen@testqa.com' in Email.<br>4. Click 'Save' button.
- **Expected Result:** Candidate is not saved. Inline validation 'Required' appears under First Name field in red text.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_REC_004: Add Candidate with Blank Last Name
- **Requirement ID:** `REQ_REC_002` | **Scenario ID:** `TS_REC_003` | **Module:** Recruitment
- **Priority:** **High** | **Test Type:** Negative / Validation
- **Objective:** Verify mandatory validation when Last Name is left blank on Add Candidate form.
- **Preconditions:** 1. User is on Recruitment > Add Candidate page.
- **Test Data:** `First: Rahul, Last: [BLANK], Email: rahul@testqa.com`
- **Execution Steps:**  
  1. Enter 'Rahul' in First Name.<br>2. Leave Last Name blank.<br>3. Enter valid Email.<br>4. Click 'Save' button.
- **Expected Result:** Candidate is not saved. Inline validation 'Required' appears under Last Name field.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_REC_005: Add Candidate with Blank Email Address
- **Requirement ID:** `REQ_REC_002` | **Scenario ID:** `TS_REC_003` | **Module:** Recruitment
- **Priority:** **High** | **Test Type:** Negative / Validation
- **Objective:** Verify mandatory validation when Email field is left blank on Add Candidate form.
- **Preconditions:** 1. User is on Recruitment > Add Candidate page.
- **Test Data:** `First: Neha, Last: Gupta, Email: [BLANK]`
- **Execution Steps:**  
  1. Enter 'Neha' in First Name.<br>2. Enter 'Gupta' in Last Name.<br>3. Leave Email field completely empty.<br>4. Click 'Save' button.
- **Expected Result:** Candidate is not saved. Red inline error text 'Required' is displayed under the Email field.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_REC_006: Validate Candidate Email Syntax with Invalid Format (Missing @ and domain)
- **Requirement ID:** `REQ_REC_002` | **Scenario ID:** `TS_REC_004` | **Module:** Recruitment
- **Priority:** **High** | **Test Type:** Equivalence Partitioning / Negative
- **Objective:** Verify that entering an improperly formatted email triggers validation.
- **Preconditions:** 1. User is on Recruitment > Add Candidate page.
- **Test Data:** `First: Rahul, Last: Sen, Email: invalidemailformat.com`
- **Execution Steps:**  
  1. Enter valid names.<br>2. Enter 'invalidemailformat.com' (missing '@') in Email field.<br>3. Click 'Save' button.
- **Expected Result:** System blocks submission and displays inline validation: 'Expected format: admin@example.com'.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_REC_007: Validate Candidate Email Syntax with Valid Domain Format
- **Requirement ID:** `REQ_REC_002` | **Scenario ID:** `TS_REC_004` | **Module:** Recruitment
- **Priority:** **High** | **Test Type:** Equivalence Partitioning / Positive
- **Objective:** Verify that a properly formatted email (user@domain.com) is accepted.
- **Preconditions:** 1. User is on Recruitment > Add Candidate page.
- **Test Data:** `Email: valid.candidate_01@sub.domain.org`
- **Execution Steps:**  
  1. Enter valid names.<br>2. Enter 'valid.candidate_01@sub.domain.org' in Email field.<br>3. Click 'Save' button.
- **Expected Result:** Email format passes validation without syntax error message.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_REC_008: Upload Resume with Supported File Format (.pdf / .docx within 1MB)
- **Requirement ID:** `REQ_REC_003` | **Scenario ID:** `TS_REC_005` | **Module:** Recruitment
- **Priority:** **Medium** | **Test Type:** Positive
- **Objective:** Verify that attaching a valid .pdf or .docx resume file succeeds.
- **Preconditions:** 1. User is on Add Candidate page with a sample valid PDF file (size < 1MB).
- **Test Data:** `File: sample_resume.pdf (size 250 KB)`
- **Execution Steps:**  
  1. Fill required candidate fields.<br>2. Click 'Browse' under Resume section.<br>3. Select 'sample_resume.pdf' and click Open.<br>4. Click 'Save' button.
- **Expected Result:** File is attached successfully. File name is shown in the field and record saves without file upload errors.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_REC_009: Upload Resume with Unsupported File Format (.exe / .bat)
- **Requirement ID:** `REQ_REC_003` | **Scenario ID:** `TS_REC_005` | **Module:** Recruitment
- **Priority:** **Medium** | **Test Type:** Negative / Security
- **Objective:** Verify that attaching an unsupported executable file type is rejected by the system.
- **Preconditions:** 1. User is on Add Candidate page with a file named 'malicious_test.exe'.
- **Test Data:** `File: malicious_test.exe`
- **Execution Steps:**  
  1. Fill required candidate fields.<br>2. Click 'Browse' under Resume.<br>3. Select 'malicious_test.exe'.<br>4. Observe validation response.
- **Expected Result:** System rejects file attachment with validation error: 'File type not allowed' or restricts file picker to allowed document formats.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_REC_010: Search Candidate by Candidate Name in Candidates Directory
- **Requirement ID:** `REQ_REC_004` | **Scenario ID:** `TS_REC_006` | **Module:** Recruitment
- **Priority:** **High** | **Test Type:** Positive / Functional
- **Objective:** Verify that searching candidate by full/partial name retrieves matching candidate record.
- **Preconditions:** 1. Candidate 'Ananya Iyer' exists in the Candidates directory.
- **Test Data:** `Candidate Name: Ananya`
- **Execution Steps:**  
  1. Navigate to Recruitment > Candidates.<br>2. Type 'Ananya' in Candidate Name field and select from autocomplete.<br>3. Click 'Search' button.
- **Expected Result:** Results table displays record for 'Ananya Iyer' with associated vacancy, date of application, and status.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_REC_011: Search Candidate by Job Vacancy Filter
- **Requirement ID:** `REQ_REC_004` | **Scenario ID:** `TS_REC_006` | **Module:** Recruitment
- **Priority:** **Medium** | **Test Type:** Functional
- **Objective:** Verify that filtering by a specific Vacancy dropdown retrieves only candidates associated with that vacancy.
- **Preconditions:** 1. User is on Recruitment > Candidates page.
- **Test Data:** `Vacancy: Select active vacancy`
- **Execution Steps:**  
  1. Select active vacancy from Job Vacancy dropdown.<br>2. Click 'Search' button.
- **Expected Result:** Table filters to show only candidates mapped to the selected vacancy.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_REC_012: Shortlist Candidate via Recruitment Workflow Action
- **Requirement ID:** `REQ_REC_005` | **Scenario ID:** `TS_REC_007` | **Module:** Recruitment
- **Priority:** **High** | **Test Type:** Business Rule / Workflow
- **Objective:** Verify candidate status progression from 'Application Initiated' to 'Shortlisted'.
- **Preconditions:** 1. An active candidate in 'Application Initiated' status is opened.
- **Test Data:** `Notes: Candidate shortlisted for initial screening`
- **Execution Steps:**  
  1. Open candidate details for 'Ananya Iyer'.<br>2. Click 'Shortlist' action button.<br>3. Enter screening note in Notes textarea.<br>4. Click 'Save' button.
- **Expected Result:** Status badge changes to 'Shortlisted'. Next workflow actions ('Schedule Interview', 'Reject') become available.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
### TC_REC_013: Cancel Add Candidate Form Entry and Discard Details
- **Requirement ID:** `REQ_REC_006` | **Scenario ID:** `TS_REC_008` | **Module:** Recruitment
- **Priority:** **Low** | **Test Type:** UI / Navigation
- **Objective:** Verify that clicking Cancel on Add Candidate form discards inputs and returns to Candidates list.
- **Preconditions:** 1. User is on Add Candidate form with data entered.
- **Test Data:** `First: TempCandidate, Last: CancelTest`
- **Execution Steps:**  
  1. Fill in candidate names.<br>2. Click 'Cancel' button.<br>3. Search for 'TempCandidate' in Candidates list.
- **Expected Result:** Navigates back to Candidates list page. 'TempCandidate' is not present in the candidates list.
- **Actual Result:** *Not Executed*
- **Status:** `Not Executed` | **Defect ID:** `-`

---
