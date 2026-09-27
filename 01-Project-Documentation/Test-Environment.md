# Test Environment Specifications

**Project:** OrangeHRM – Manual Testing Project  
**Author:** Pranali (QA Engineer Fresher)  
**Testing Methodology:** Manual UI / Black-Box Testing  

---

## 1. Overview
The test environment represents the hardware, operating system, browser configurations, network settings, and application platform utilized to execute the manual test suite. Documenting the environment ensures test reproducibility and accurate defect isolation.

---

## 2. Hardware Environment
- **Device Type:** Laptop / Workstation PC
- **Processor:** Intel Core i5 / AMD Ryzen 5 or equivalent (x64 architecture)
- **RAM:** 8 GB or 16 GB DDR4
- **Storage:** Solid State Drive (SSD)
- **Display Resolution:** 1920 x 1080 (Full HD)
- **Display Scaling:** 100% (Standard Windows scale setting)

---

## 3. Software & Operating System
- **Operating System:** Microsoft Windows 11 Home / Pro (64-bit)
- **System Locale / Keyboard:** English (United States / India)
- **Time Zone:** IST (UTC+05:30)

---

## 4. Web Browsers Under Test

| Browser Name | Engine | Tested Version | Role / Scope |
| :--- | :--- | :--- | :--- |
| **Google Chrome** | Chromium / Blink | Latest Stable (v128.0+) | **Primary Browser:** Complete test execution of all 56 test cases. |
| **Microsoft Edge** | Chromium / Blink | Latest Stable (v128.0+) | **Secondary Browser:** Smoke suite & cross-browser UI compatibility checks. |

*Browser Configuration Rules:*
- Browser zoom level fixed at 100%.
- Ad-blockers, third-party translation extensions, and developer extension suites disabled during testing to avoid script interference.
- Cache and cookies cleared prior to executing authentication and session boundary tests.

---

## 5. Application Details

| Parameter | Configuration Value |
| :--- | :--- |
| **Application Name** | OrangeHRM Open Source (Official Public Sandbox) |
| **Release Version** | OrangeHRM 5.x |
| **Target URL** | `https://opensource-demo.orangehrmlive.com/web/index.php/auth/login` |
| **Protocol** | HTTPS (TLS Encrypted) |
| **Default Credentials** | **Username:** `Admin` \| **Password:** `admin123` |
| **User Role** | System Administrator (Full UI privilege within the demo instance) |

---

## 6. Test Documentation Tools

| Tool | Purpose | Usage in Project |
| :--- | :--- | :--- |
| **Microsoft Excel (.xlsx)** | Test Design & Tracking | Managing Test Scenarios, Test Cases, Test Data, Execution Sheets, Defect Reports, and RTM. |
| **Markdown (.md)** | Documentation & Reporting | Test Plan, Scope, Environment, Techniques, Execution Summary, Defect Summary, Interview Notes, and GitHub README. |
| **Git & GitHub** | Version Control & Portfolio Hosting | Maintaining repository structure, version history, and public portfolio presentation (`https://github.com/PranaliO`). |
| **Snipping Tool / Windows Screenshot** | Defect & Test Evidence Capture | Capturing UI defects, validation prompts, and record confirmations. |
