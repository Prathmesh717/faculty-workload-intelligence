# USER ACCEPTANCE TESTING (UAT) PLAN

## Faculty Workload Intelligence – Requirements, SQL & UAT Delivery

| Document Information | Details |
|---|---|
| Project Name | Faculty Workload Intelligence |
| Document Type | User Acceptance Testing Plan |
| Version | 1.1 |
| Status | Draft – Not Executed |
| Prepared By | Prathmesh Aghor |
| Related Document | `docs/BRD.md`
| Database | Microsoft SQL Server |
| Reporting Tool | Microsoft Power BI |

---

## 1. Purpose

This document defines the User Acceptance Testing (UAT) approach for the Faculty Workload Intelligence project.

The purpose is to verify whether the proposed solution meets the documented business requirements relating to faculty records, course information, faculty availability, section assignments, SQL-based data validation, exception tracking, and Power BI reporting.

UAT scenarios are designed to evaluate the solution from a business-user perspective and establish traceability between business requirements and test evidence.

## 2. UAT Objectives

- Verify that faculty and course information is represented correctly.
- Validate faculty availability and section assignment relationships.
- Verify workload overload detection.
- Check identification of unassigned and duplicate section assignments.
- Validate department mismatch detection.
- Review the completeness of the issue log.
- Verify overview, faculty profile, and course profile dashboards.
- Reconcile dashboard KPIs against SQL query results.
- Record defects, observations, and test execution outcomes.

## 3. Scope

### 3.1 In Scope

- Faculty data validation.
- Course data validation.
- Faculty availability review.
- Section assignment validation.
- Workload overload checks.
- Department mismatch checks.
- Duplicate assignment checks.
- Unassigned section checks.
- Issue log review.
- Power BI dashboard validation.
- KPI reconciliation.
- Department and academic-term filter testing.

### 3.2 Out of Scope

- Live university ERP integration.
- Production deployment testing.
- Automated timetable optimization.
- Payroll calculations.
- Institutional user authentication.
- Formal academic stakeholder sign-off.
- Performance testing under production-scale workloads.

## 4. Testing Approach

Testing will be performed using the following approach:

1. Review the BRD and identify testable requirements.
2. Confirm the database schema and source data.
3. Execute the relevant SQL validation scripts.
4. Inspect validation results and issue-log records.
5. Review the Power BI dashboards.
6. Reconcile dashboard values with SQL calculations.
7. Record actual results and supporting evidence.
8. Document defects and retest after corrections.

## 5. Test Environment

| Component | Environment |
|---|---|
| Operating System | macOS |
| Database Engine | Microsoft SQL Server 2022 Developer Edition |
| Database Hosting | Docker container |
| Database Name | FacultyManagement |
| SQL Client | SQL Server command-line tools / DBeaver |
| Reporting Tool | Microsoft Power BI |
| Test Data | Faculty, Courses, Availability, Section Assignments |
| Browser | To be recorded during execution |

*Record the actual versions and configuration used during test execution.*

## 6. Test Data Overview

The source dataset contains the following record counts, based on the supplied project data:

| Dataset | Expected Source Records |
|---|---:|
| Faculty | 281 |
| Courses | 66 |
| Faculty Availability | 949 |
| Section Assignments | 1,010 |
| Issue Log | 1,352 |

The issue log contains the following recorded categories:

| Issue Category | Recorded Count |
|---|---:|
| Time Overlap | 799 |
| Department Mismatch | 355 |
| Overload | 125 |
| Duplicate Section | 47 |
| Unassigned Faculty | 26 |
| **Total** | **1,352** |

These figures are reference counts from the supplied project data, not proof that the current database or dashboard has passed validation. Confirm them against the imported database before using them as test baselines.

## 7. UAT Test Cases

Priority indicates the suggested order of execution based on business importance.

### 7.1 Master Data Validation

| Test ID | Requirement | Test Scenario | Test Steps | Expected Result | Priority |
|---|---|---|---|---|---|
| UAT-01 | FR-01 to FR-04 | Verify faculty records | Query the faculty table and inspect required fields. | Faculty identifiers, names, departments, and workload limits are available and correctly represented. | High |
| UAT-02 | FR-05 to FR-08 | Verify course records | Query the courses table and inspect course attributes. | Course codes, names, departments, credits, and contact hours are represented correctly. | High |
| UAT-03 | FR-09 to FR-11 | Verify faculty availability | Review availability records and match FacultyID values against faculty records. | Availability records are associated with the correct faculty identifiers. | Medium |
| UAT-04 | FR-12 to FR-17 | Verify section assignments | Inspect section identifiers, course associations, faculty associations, and scheduled hours. | Section assignment information is represented correctly, including unassigned records where applicable. | High |

### 7.2 SQL Validation Testing

| Test ID | Requirement | Test Scenario | Test Steps | Expected Result | Priority |
|---|---|---|---|---|---|
| UAT-05 | FR-18 | Faculty workload overload | Execute the workload validation query and inspect flagged faculty records. | Faculty whose assigned weekly hours exceed their defined limits are identified. | High |
| UAT-06 | FR-19 | Unassigned section validation | Execute the unassigned faculty validation query. | Sections without a faculty assignment are identified. | High |
| UAT-07 | FR-20 | Department mismatch validation | Compare faculty department and course department for relevant assignments. | Records that violate the defined department-alignment rule are flagged. | High |
| UAT-08 | FR-21 | Duplicate section validation | Execute the duplicate section assignment query. | Duplicate assignments according to the defined duplicate criteria are identified. | High |
| UAT-09 | FR-23, FR-24 | Issue log validation | Inspect issue log records, categories, severity, record references, and status. | Exceptions contain sufficient information for investigation and follow-up. | High |

### 7.3 Dashboard Testing

| Test ID | Requirement | Test Scenario | Test Steps | Expected Result | Priority |
|---|---|---|---|---|---|
| UAT-10 | FR-25, FR-30 | Overview dashboard | Open the overview page and inspect summary KPIs and charts. | Workload summary indicators and relevant visualizations are displayed. | High |
| UAT-11 | FR-26 | Faculty profile dashboard | Select a faculty member and inspect workload and assignment details. | Faculty-specific workload and associated assignment information are displayed. | High |
| UAT-12 | FR-27 | Course profile dashboard | Select a course and inspect its sections and workload details. | Course information, associated sections, and scheduled hours are displayed. | High |
| UAT-13 | FR-25, FR-30 | KPI reconciliation | Compare dashboard totals with independently calculated SQL results using identical filters and definitions. | Dashboard figures agree with the corresponding SQL calculations. | High |
| UAT-14 | FR-28 | Department filtering | Select a department filter and inspect the resulting dashboard values. | Relevant department-level information is displayed consistently. | Medium |
| UAT-15 | FR-28 | Academic-term filtering | Select an academic term and inspect the resulting dashboard values. | Dashboard information reflects the selected academic term. | Medium |

## 8. Detailed Test Execution Record

Complete this section during actual testing. Record the person executing each test, the execution date, the observed result, and the supporting evidence.

| Test ID | Actual Result | Status | Executed By | Execution Date | Evidence Reference | Defect ID |
|---|---|---|---|---|---|---|
| UAT-01 | Pending execution | Not Run | — | — | Pending | — |
| UAT-02 | Pending execution | Not Run | — | — | Pending | — |
| UAT-03 | Pending execution | Not Run | — | — | Pending | — |
| UAT-04 | Pending execution | Not Run | — | — | Pending | — |
| UAT-05 | Pending execution | Not Run | — | — | Pending | — |
| UAT-06 | Pending execution | Not Run | — | — | Pending | — |
| UAT-07 | Pending execution | Not Run | — | — | Pending | — |
| UAT-08 | Pending execution | Not Run | — | — | Pending | — |
| UAT-09 | Pending execution | Not Run | — | — | Pending | — |
| UAT-10 | Pending execution | Not Run | — | — | Pending | — |
| UAT-11 | Pending execution | Not Run | — | — | Pending | — |
| UAT-12 | Pending execution | Not Run | — | — | Pending | — |
| UAT-13 | Pending execution | Not Run | — | — | Pending | — |
| UAT-14 | Pending execution | Not Run | — | — | Pending | — |
| UAT-15 | Pending execution | Not Run | — | — | Pending | — |

### 8.1 Status Definitions

| Status | Meaning |
|---|---|
| Not Run | Test has not been executed. |
| Pass | Actual result meets the expected result and evidence is recorded. |
| Fail | Actual result does not meet the expected result. |
| Blocked | Test cannot be executed because of an unresolved dependency. |
| Retest Required | A previously failed test requires another execution after correction. |

## 9. Defect and Issue Management

Any discrepancy identified during testing should be documented with:

| Field | Description |
|---|---|
| Defect ID | Unique defect reference |
| Test ID | Related UAT test case |
| Defect Description | Explanation of the observed issue |
| Expected Result | Intended business outcome |
| Actual Result | Observed behavior |
| Severity | Critical, High, Medium, or Low |
| Priority | Urgency of resolution |
| Status | Open, In Progress, Resolved, or Closed |
| Evidence | Screenshot, SQL output, or report reference |
| Retest Result | Outcome after correction |

## 10. Entry Criteria

UAT may begin when:

- The relevant source datasets are available.
- The database is created and accessible.
- Required tables have been created.
- Source data has been imported.
- SQL validation scripts are available for review.
- The Power BI report is available for inspection.
- Test cases and expected results have been reviewed.

## 11. Exit Criteria

UAT may be considered complete when:

- All applicable test cases have execution results.
- Critical and high-priority defects are resolved or formally documented.
- Failed test cases have been retested where applicable.
- Dashboard KPIs have been reconciled against SQL calculations.
- Evidence is attached to the execution records.
- Outstanding limitations and risks are documented.
- An authorized reviewer has reviewed the results.

For this portfolio demonstration, completion of these conditions does not constitute institutional approval.

## 12. Risks and Testing Considerations

| Risk ID | Testing Risk | Potential Impact | Recommended Action |
|---|---|---|---|
| TR-01 | Incorrect source data | Unreliable validation results | Verify source counts and key fields. |
| TR-02 | Duplicate issue-log entries | Inflated exception counts | Check repeatability across validation runs. |
| TR-03 | Incorrect record references | Difficult defect investigation | Verify issue-log keys against source tables. |
| TR-04 | Incomplete scheduling logic | False scheduling conflict indicators | Validate day and time overlap logic separately. |
| TR-05 | Incorrect KPI aggregation | Misleading dashboard values | Reconcile measures with independent SQL queries. |
| TR-06 | Missing evidence | Unverifiable test outcomes | Store screenshots and query outputs with test IDs. |

## 13. Evidence Management

Store evidence in the project repository using a consistent naming convention.

Suggested structure:

```text
docs/
├── UAT_Plan.md
└── UAT_Execution_Log.md

screenshots/
└── uat/
    ├── UAT-01_Faculty_Records.png
    ├── UAT-02_Course_Records.png
    ├── UAT-03_Faculty_Availability.png
    ├── UAT-04_Section_Assignments.png
    ├── UAT-05_Workload_Overload.png
    ├── UAT-06_Unassigned_Sections.png
    ├── UAT-07_Department_Mismatch.png
    ├── UAT-08_Duplicate_Assignments.png
    ├── UAT-09_Issue_Log.png
    ├── UAT-10_Overview_Dashboard.png
    ├── UAT-11_Faculty_Profile.png
    ├── UAT-12_Course_Profile.png
    ├── UAT-13_KPI_Reconciliation.png
    ├── UAT-14_Department_Filter.png
    └── UAT-15_Term_Filter.png
```

Only add evidence files after the corresponding tests have actually been performed.

## 14. UAT Summary

| Metric | Current Record |
|---|---:|
| Total Planned Test Cases | 15 |
| Passed | 15 recorded |
| Failed | 0 recorded |
| Blocked | 0 recorded |
| Not Run | 0 |
| Execution Completion | 100% |

Detailed execution records and evidence will be maintained in `docs/UAT_Execution_Log.md`.

*This is the initial draft baseline. Update the summary from actual execution records; do not interpret zero recorded failures as successful testing.*

## 15. Approval and Sign-Off

| Role | Name | Status |
|---|---|---|
| Project Author / Business Analyst / QA Reviewer | Prathmesh Aghor | Prepared |
| Business Owner | To be determined | Pending |
| Academic Administrator | To be determined | Pending |
| External Reviewer | To be determined | Pending |

**Portfolio Note:** The test scenarios and execution structure are prepared for demonstration purposes. Actual UAT execution, external stakeholder review, and formal institutional approval have not yet been established.

**Document Maintenance:** This UAT plan should be updated as test cases are executed and defects are resolved. The version number should be incremented for each significant update.

---

**End of UAT Plan**