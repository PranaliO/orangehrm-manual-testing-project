# Testing Scope and Objectives

**Project:** OrangeHRM – Manual Testing Project  
**Author:** Pranali (QA Engineer Fresher)  
**Testing Methodology:** Manual Black-Box Testing  

---

## 1. Project Purpose
The purpose of this portfolio project is to demonstrate end-to-end practical competence in **Manual Software Testing**. As a 2026 B.Tech Computer Science graduate preparing for QA/Test Engineer roles, this project serves as tangible evidence of understanding the Software Testing Life Cycle (STLC), test documentation, defect logging, and quality validation on an industry-standard web application.

---

## 2. Primary Testing Objectives

| # | Question / Objective | Target Verification |
| :- | :--- | :--- |
| **O-01** | Does authentication enforce security and session integrity? | Verify valid login, rejection of invalid credentials, password masking, logout redirection, and back-button session termination. |
| **O-02** | Are mandatory fields properly validated across modules? | Verify system triggers clear inline/banner warnings when required fields are omitted. |
| **O-03** | Can employees be created, searched, edited, and deleted reliably? | Verify PIM functionality: add employee, search by name/ID, profile persistence, edits, and permanent deletion with confirmation. |
| **O-04** | Are leave management workflows logically protected against invalid inputs? | Verify leave application with valid dates, rejection of invalid date combinations (e.g., end date before start date), comments, and leave list filtering. |
| **O-05** | Does the recruitment lifecycle handle candidate applications accurately? | Verify adding candidate details, email format validation, resume file attachment, vacancy association, candidate search, and candidate stage status updates. |
| **O-06** | Are defects documented according to industry standards? | Record all bugs with clear reproduction steps, expected vs. actual outcomes, environment details, severity, priority, and retesting notes. |
| **O-07** | Is complete bidirectional traceability maintained? | Build a complete Requirement Traceability Matrix (RTM) linking requirements to scenarios, test cases, and defects. |
| **O-08** | Can regression and retesting cycles be systematically planned? | Select focused smoke and regression suites from core cases to confirm system stability without test duplication. |

---

## 3. Explicit Boundaries

### In-Scope Modules:
1. **Login & Session Management**
2. **Employee Management (PIM)**
3. **Leave Management**
4. **Recruitment (Candidates)**

### Out-of-Scope Modules & Activities:
- Admin / User Management, Time / Timesheet tracking, Performance appraisal, Directory, Buzz, System Maintenance.
- Automated testing (no Selenium, Playwright, Cypress, Cucumber, or TestNG).
- API / Database testing via Postman / MySQL (testing is strictly black-box UI).
- Performance, Stress, Security penetration, and Multi-tenant load testing.
- Modifying administrative master settings or company payroll configurations.

---

## 4. Fresher Credibility Statement
This is a personal, independent portfolio project executed on the public OrangeHRM Open-Source demo platform. It reflects individual testing skills and adheres to realistic, non-exaggerated entry-level QA standards.
