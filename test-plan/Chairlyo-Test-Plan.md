# Chairlyo Test Plan

**Application:** Chairlyo CRM  
**Prepared By:** Anish Lamichhane, Nasmita Rayamajhi  
**Submitted:** 25 August 2026

---

## 1. Introduction

This document defines the test plan for the Chairlyo CRM application. It outlines the testing objectives, scope, testing types, test environment, roles and responsibilities, test schedule, risks and mitigation, entry criteria, exit criteria, defect management process, and testing deliverables.

---

## 2. Test Objectives

The primary objectives of the test cycle are to:

1. Verify that major application features function correctly and align with the intended user experience.
2. Validate that the system correctly implements defined business rules and end-to-end workflows.
3. Verify secure and reliable login behavior for each user type — Super Admin, Branch Admin, and Staff.
4. Verify that permissions and feature access are correctly restricted based on each user's assigned role.
5. Verify that each branch is isolated from others and can only view, create, or modify data belonging to itself.
6. Validate end-to-end functionality for managing customer and staff records, including creation, updates, and removal.
7. Verify that branch-level performance metrics such as revenue, sessions, and customers display accurate and up-to-date information.
8. Verify that form fields, mandatory inputs, and error/warning messages behave correctly under valid and invalid input conditions.
9. Verify that backend API endpoints return correct responses, status codes, and data where the application relies on them.
10. Verify that data displayed on the UI matches the corresponding records in the backend database, with no mismatches or data loss.
11. Verify consistent look, feel, and functionality across supported browsers.
12. Re-test previously reported defects after fixes are deployed and confirm that no new issues have been introduced.
13. Detect slowness, timeouts, or degraded responsiveness during typical expected usage.

---

# 3. Test Scope

## 3.1 Admin Panel

### In Scope

- Login and authentication (Admin/Super Admin)
- Branch management:
  - Branch listing
  - Adding branches
  - Editing branches
  - Activating/deactivating branches
- Analytics Overview dashboard
- Payment Reports
- Expense Reports
- Product Report
- Staff Performance Report
- Customer Report
- Appointment Report
- Service Report
- Wallet Report
- Navigation across Organization and Analytics sections
- Search, filter, sort, and pagination on branch listings and reports
- User roles and permissions
- Form validation
- Data accuracy between reports and underlying branch/transaction records

### Out of Scope

- Branch panel operational functionalities such as:
  - Waiting
  - Sessions
  - Live Studio
  - Billing
  - Studio Drawer
  - Product Sale
- Day-to-day branch-level operational workflows

---

## 3.2 Branch Panel

### In Scope

- Login and authentication for Branch/Staff users
- Branch-level dashboard
- Waiting / customer queue handling
- Sessions and service session tracking
- Live Studio monitoring
- Billing and payment recording
- Studio Drawer and cash/drawer management
- Product Sale
- Management:
  - Staff
  - Customer
  - Service
- Catalog:
  - Services
  - Products
- Benefits and loyalty-related features
- Navigation across branch modules
- Search, filter, sort, and pagination where applicable
- Form validation
- Data accuracy
- User workflows and functionality

### Out of Scope

- Admin panel functionality
- Organization → Branches
- Analytics and Reports
- Admin-only multi-branch oversight
- Configuration of user roles and permissions

---

# 4. Test Approach

The following testing types will be used during the Chairlyo testing process.

| Testing Type | Purpose |
|---|---|
| Functional Testing | Verify that application features work according to requirements and test customer, staff, branch, and other management functions. |
| UI Testing | Verify buttons, forms, menus, tables, labels, icons, page layouts, and behavior across screen sizes. |
| Authentication Testing | Test login, logout, password validation, authentication mechanisms, and access for different user types. |
| Authorization / RBAC Testing | Verify that users can access only the features and data permitted for their roles. |
| Branch-Level Data Access Testing | Verify that each branch can view and manage only its permitted data. |
| Input Validation Testing | Test required fields, invalid inputs, incorrect formats, boundary values, duplicate data, and validation messages. |
| API Testing | Verify API requests, responses, methods, status codes, authentication, response data, and error handling. |
| Database Testing | Verify data storage, retrieval, updates, deletions, relationships, and consistency. |
| Regression Testing | Re-test existing functionality after changes or bug fixes. |
| Smoke Testing | Perform basic testing after a new build/deployment to verify major features. |
| Sanity Testing | Perform focused testing after minor changes or bug fixes. |
| Performance Testing | Verify response time, stability, and behavior under different loads. |

---

# 5. Test Environment

| Parameter | Details |
|---|---|
| Application | Chairlyo |
| Environment | QA / Staging |
| Application URL | `https://qa02.stage.chairlyo.com/` |
| Browser | Google Chrome |
| Operating System | Windows 10/11 |
| Device | Laptop |
| Bug Tracking | Jira |
| API Testing | Postman |
| Database Tool | DBeaver |
| UI Automation | Cypress |
| Performance Testing | Apache JMeter |

> **Note:** Test credentials, API keys, database credentials, and other secrets are not stored in this repository.

---

# 6. Roles and Responsibilities

| Role | Person | Responsibility |
|---|---|---|
| QA Tester | Anish Lamichhane | Prepare test cases, test login, branches, appointments, access control, record results, report bugs, and retest fixes. |
| QA Tester | Nasmita Rayamajhi | Prepare test cases, test products, billing, inventory, reports, and dashboards, record results, report bugs, and retest fixes. |
| Developer | Development Team | Investigate reported defects, fix issues, and provide updated builds for retesting. |
| Project Supervisor / Instructor | Assigned Reviewer | Clarify requirements, review progress, and approve the final submission. |
| QA Testers | Anish Lamichhane & Nasmita Rayamajhi | Review defects together, test shared features such as navigation and filters, and prepare the final test summary. |

---

# 7. Test Schedule

| Testing Activity | Duration |
|---|---:|
| Test Planning | 2 Days |
| Test Scenario Preparation | 2 Days |
| Test Case Preparation | 3 Days |
| Functional Testing | 5 Days |
| API Testing | 2 Days |
| Database Testing | 2 Days |
| Automation Testing | 3 Days |
| Performance Testing | 2 Days |
| Regression Testing | 1 Day |

---

# 8. Entry Criteria

Testing will start when the following conditions are met:

- Chairlyo staging website is available and accessible.
- Required test accounts and login credentials are provided.
- Important modules are deployed and ready for testing.
- Required test data is available or can be created.
- Test plan and test cases are prepared.
- The team has access to a browser and a place to record test results and defects.
- Known blocker issues are communicated to the QA team.

---

# 9. Exit Criteria

Testing will be considered complete when:

- All planned test cases have been executed.
- Results are recorded as Pass, Fail, Blocked, or Not Tested.
- Critical and high-severity defects are fixed, accepted, or clearly reported.
- Fixed defects have been retested.
- Required regression testing has been completed.
- No unreported blocker defect remains.
- A test summary report has been prepared.
- Remaining risks and untested areas are clearly documented.

---

# 10. Defect Management

When a defect is found, the QA tester will first confirm that the issue can be reproduced. The tester will then record the defect in the bug report or tracking system.

Each defect report should include:

- Defect ID
- Defect title
- Module or feature name
- Preconditions
- Steps to reproduce
- Expected result
- Actual result
- Screenshot or other evidence
- Severity
- Priority
- Current status
- Tester name

### Defect Lifecycle

```text
New
 ↓
Assigned
 ↓
In Progress
 ↓
Fixed
 ↓
Retest
 ↓
Closed
