# BUSINESS REQUIREMENTS DOCUMENT (BRD)

## Faculty Workload Intelligence – Requirements, SQL & UAT Delivery

| Document Information    | Details                                             |
| ----------------------- | --------------------------------------------------- |
| Project Name            | Faculty Workload Intelligence                       |
| Document Type           | Business Requirements Document (BRD)                |
| Version                 | 1.1                                                 |
| Status                  | Portfolio Project – Draft                           |
| Prepared By             | Prathmesh Aghor                                     |
| Project Domain          | Higher Education / Academic Administration          |
| Primary Focus           | Faculty Workload Scheduling and Resource Allocation |
| Supporting Technologies | SQL Server, Microsoft Power BI                      |

---

# 1. Executive Summary

Educational institutions manage multiple academic activities, including faculty allocation, course assignments, teaching schedules, faculty availability, and workload distribution.

Managing these activities using disconnected records and manual processes can create inconsistencies, reduce operational visibility, and make it difficult for academic administrators to identify workload imbalances.

The **Faculty Workload Intelligence** project aims to demonstrate a structured approach to faculty workload analysis and academic resource allocation.

The proposed solution uses structured datasets, SQL-based data validation, issue tracking, and Power BI dashboards to help administrators examine faculty assignments, workload distribution, and potential scheduling inconsistencies.

This project also demonstrates business analysis practices, including requirements documentation, process mapping, data analysis, validation planning, and business intelligence reporting.

# 2. Business Background

Faculty workload management is an important administrative activity in higher education institutions.

Academic administrators need visibility into:

- Faculty members and their departments.
- Courses and their associated teaching hours.
- Faculty availability across different days and time slots.
- Section assignments and scheduled teaching hours.
- Faculty workload limits.
- Potential assignment and scheduling inconsistencies.

Without structured validation and reporting, administrators may face challenges identifying faculty overload, unassigned sections, duplicate assignments, and department mismatches.

The project addresses these challenges through a data-driven workload intelligence approach.

# 3. Business Problem Statement

The absence of a centralized and structured workload analysis process can make it difficult to maintain accurate faculty assignment information and monitor teaching workloads.

Potential business problems include:

1. Limited visibility into individual faculty workloads.
2. Difficulty identifying assignments that exceed workload limits.
3. Inconsistent faculty and course department information.
4. Duplicate or incomplete section assignments.
5. Limited visibility into unassigned teaching sections.
6. Difficulty examining faculty availability and scheduling information.
7. Lack of consolidated reporting for academic workload analysis.

A structured solution is required to organize workload information, identify potential data inconsistencies, and provide meaningful reporting for academic decision-making.

# 4. Business Objectives

The primary objectives are:

| ID    | Business Objective                                           |
| ----- | ------------------------------------------------------------ |
| BO-01 | Improve visibility into faculty workload distribution.       |
| BO-02 | Identify potential faculty workload overloads.               |
| BO-03 | Detect inconsistencies in faculty and course assignments.    |
| BO-04 | Identify duplicate and unassigned section records.           |
| BO-05 | Organize data quality exceptions through issue tracking.     |
| BO-06 | Provide interactive dashboards for workload monitoring.      |
| BO-07 | Support informed academic resource allocation decisions.     |
| BO-08 | Establish structured documentation and validation practices. |

# 5. Project Scope

## 5.1 In Scope

The project includes:

- Analysis of faculty, course, availability, and section assignment datasets.
- Documentation of business requirements.
- As-Is and To-Be process mapping.
- Entity Relationship Diagram (ERD) preparation.
- SQL Server-based data validation.
- Identification of potential workload and assignment exceptions.
- Issue log creation and analysis.
- Power BI dashboard development.
- Faculty-level workload reporting.
- Course-level workload reporting.
- Validation and testing considerations.

## 5.2 Out of Scope

The following capabilities are outside the defined project scope:

- Integration with a live university ERP or student information system.
- Automated timetable generation and optimization.
- Real-time synchronization with institutional databases.
- Automated faculty notifications.
- Production deployment.
- Institutional user authentication and role-based access.
- Payroll and faculty compensation calculations.
- Actual institutional approval or adoption.
- Automated resolution of detected scheduling conflicts.

# 6. Stakeholder Analysis

The following stakeholder roles represent the intended users and participants in the proposed business process. They are not claims of actual stakeholder interviews or institutional approvals.

| Stakeholder            | Responsibility                                 | Interest                                      |
| ---------------------- | ---------------------------------------------- | --------------------------------------------- |
| Academic Administrator | Oversees academic workload allocation          | Workload visibility and assignment accuracy   |
| Department Head        | Reviews department-level faculty assignments   | Faculty utilization and workload distribution |
| Faculty Member         | Provides availability and teaching information | Accurate workload and assignment records      |
| Scheduling Coordinator | Coordinates course and section assignments     | Assignment consistency                        |
| Business Analyst       | Documents requirements and analyzes processes  | Requirement clarity and traceability          |
| Data Analyst           | Examines datasets and validation results       | Data quality and reporting                    |
| Management             | Reviews academic resource allocation           | Operational insights and decision support     |

# 7. Current State – As-Is Process

The current-state process represents a scenario in which faculty information, course information, availability, and teaching assignments are maintained across separate records or administrative files.

### As-Is Process

1. Faculty information is maintained in faculty records.
2. Course information is maintained separately.
3. Faculty availability is recorded.
4. Academic sections are assigned to faculty members.
5. Administrators review assignment information.
6. Workload inconsistencies may be identified during manual review.
7. Reports are prepared for administrative analysis.

### Current-State Challenges

- Information may be distributed across multiple datasets.
- Manual review can make exception identification difficult.
- Workload inconsistencies may not be immediately visible.
- Duplicate or incomplete assignments can affect reporting.
- Consolidated workload analysis may require additional effort.

# 8. Proposed State – To-Be Process

The proposed process introduces structured data organization, SQL validation, exception tracking, and interactive reporting.

### To-Be Process

1. Load faculty, course, availability, and section assignment data.
2. Organize source information into structured database tables.
3. Execute SQL-based data validation checks.
4. Identify potential workload and assignment exceptions.
5. Record detected exceptions in an issue log.
6. Analyze validated workload information.
7. Present relevant metrics through Power BI dashboards.
8. Enable administrators to review workload distribution and investigate exceptions.

### Expected Improvements

- Improved visibility into workload information.
- Structured identification of data quality issues.
- Centralized exception reporting.
- Better access to faculty and course-level insights.
- More informed academic resource allocation.

# 9. Functional Requirements

Functional requirements describe what the proposed solution should support.

## 9.1 Faculty Data Management

| Requirement ID | Requirement                                                                 | Priority |
| -------------- | --------------------------------------------------------------------------- | -------- |
| FR-01          | The solution shall maintain faculty identification information.             | High     |
| FR-02          | The solution shall capture faculty department and designation information.  | High     |
| FR-03          | The solution shall maintain faculty employment type and campus information. | Medium   |
| FR-04          | The solution shall capture maximum workload hours per week.                 | High     |

## 9.2 Course Data Management

| Requirement ID | Requirement                                                   | Priority |
| -------------- | ------------------------------------------------------------- | -------- |
| FR-05          | The solution shall maintain course codes and course names.    | High     |
| FR-06          | The solution shall capture course department information.     | High     |
| FR-07          | The solution shall maintain course credits and contact hours. | High     |
| FR-08          | The solution shall capture academic term and delivery mode.   | Medium   |

## 9.3 Faculty Availability

| Requirement ID | Requirement                                                          | Priority |
| -------------- | -------------------------------------------------------------------- | -------- |
| FR-09          | The solution shall maintain faculty availability by day.             | High     |
| FR-10          | The solution shall capture availability start and end times.         | High     |
| FR-11          | The solution shall support analysis of faculty availability records. | Medium   |

## 9.4 Section Assignment Management

| Requirement ID | Requirement                                                                | Priority |
| -------------- | -------------------------------------------------------------------------- | -------- |
| FR-12          | The solution shall maintain section identification information.            | High     |
| FR-13          | The solution shall associate sections with courses.                        | High     |
| FR-14          | The solution shall associate sections with faculty members where assigned. | High     |
| FR-15          | The solution shall capture scheduled teaching hours per week.              | High     |
| FR-16          | The solution shall maintain section term and campus information.           | Medium   |
| FR-17          | The solution shall maintain assignment start and end dates.                | Medium   |

## 9.5 Data Validation and Exception Management

| Requirement ID | Requirement                                                                                                         | Priority |
| -------------- | ------------------------------------------------------------------------------------------------------------------- | -------- |
| FR-18          | The solution shall identify potential faculty workload overloads.                                                   | High     |
| FR-19          | The solution shall identify sections without faculty assignments.                                                   | High     |
| FR-20          | The solution shall identify potential faculty-course department mismatches.                                         | High     |
| FR-21          | The solution shall identify duplicate section assignments.                                                          | High     |
| FR-22          | The solution shall examine scheduling-related inconsistencies.                                                      | Medium   |
| FR-23          | The solution shall record identified exceptions in an issue log.                                                    | High     |
| FR-24          | The issue log shall capture rule name, severity, table name, record reference, details, and status where available. | High     |

## 9.6 Reporting and Dashboard Requirements

| Requirement ID | Requirement                                                                        | Priority |
| -------------- | ---------------------------------------------------------------------------------- | -------- |
| FR-25          | The solution shall provide an overview of faculty workload.                        | High     |
| FR-26          | The dashboard shall provide faculty-level workload information.                    | High     |
| FR-27          | The dashboard shall provide course-level workload information.                     | High     |
| FR-28          | The dashboard shall support analysis by department and academic term.              | Medium   |
| FR-29          | The dashboard shall highlight relevant workload and assignment exceptions.         | High     |
| FR-30          | The dashboard shall present information using appropriate KPIs and visualizations. | High     |

# 10. Non-Functional Requirements

| Requirement ID | Category        | Requirement                                                                                     |
| -------------- | --------------- | ----------------------------------------------------------------------------------------------- |
| NFR-01         | Usability       | Dashboard information should be understandable to academic administrators.                      |
| NFR-02         | Data Integrity  | Data validation should identify relevant inconsistencies in the source records.                 |
| NFR-03         | Maintainability | SQL scripts and documentation should be organized for easier maintenance.                       |
| NFR-04         | Performance     | Dashboard queries should execute within an acceptable time for the intended dataset.            |
| NFR-05         | Reliability     | Validation results should be reproducible when executed against the same source data and rules. |
| NFR-06         | Scalability     | The data structure should allow additional faculty, course, and assignment records.             |
| NFR-07         | Traceability    | Requirements should be identifiable through unique requirement IDs.                             |
| NFR-08         | Documentation   | Business rules, data definitions, and validation logic should be documented.                    |

*Note: These are proposed requirements. Performance thresholds, security standards, and formal service-level targets have not been established.*

# 11. Business Rules

The following business rules define the intended validation logic.

| Rule ID | Business Rule                                                                                          | Expected Validation                                     |
| ------- | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------- |
| BR-01   | Faculty workload should not exceed the defined maximum weekly workload.                                | Compare assigned hours against maximum workload hours.  |
| BR-02   | Every section should have an assigned faculty member unless explicitly permitted to remain unassigned. | Identify missing faculty assignments.                   |
| BR-03   | Faculty and course departments should be consistent where department alignment is required.            | Compare faculty department and course department.       |
| BR-04   | A section should not have duplicate assignment records.                                                | Identify repeated section assignments.                  |
| BR-05   | Assignment dates should be valid.                                                                      | Examine start and end date consistency.                 |
| BR-06   | Faculty availability should be considered when evaluating scheduling compatibility.                    | Compare assignment schedules with availability records. |
| BR-07   | Scheduled teaching hours should be valid and non-negative.                                             | Validate scheduled hour values.                         |
| BR-08   | Course contact hours should be consistent with the relevant course information.                        | Compare assignment and course records where applicable. |

*The final interpretation of these rules should be confirmed against institutional scheduling policies. A validation flag does not automatically establish a real scheduling violation.*

# 12. Data Requirements

The proposed solution uses four primary datasets.

| Dataset              | Key Fields                                                                                  | Business Purpose                                |
| -------------------- | ------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| Faculty              | FacultyID, FullName, Department, Rank, EmployeeType, Campus, MaxLoadHoursPerWeek            | Stores faculty information and workload limits. |
| Courses              | CourseCode, CourseName, Department, Credits, ContactHoursPerWeek, Term, DeliveryMode        | Stores course information.                      |
| Faculty Availability | FacultyID, Day, AvailableStart, AvailableEnd                                                | Stores faculty availability.                    |
| Section Assignments  | SectionID, CourseCode, FacultyID, ScheduledHoursPerWeek, MeetingPattern, StartDate, EndDate | Stores section assignment information.          |

## 12.1 Data Relationships

The proposed data model includes:

- Faculty to faculty availability.
- Faculty to section assignments.
- Courses to section assignments.
- Section assignments to academic terms and scheduling information.

A faculty member may have multiple availability records and multiple section assignments. A course may be associated with multiple sections.

# 13. Key Performance Indicators (KPIs)

The dashboards are intended to support the following indicators.

| KPI                       | Description                                                                   |
| ------------------------- | ----------------------------------------------------------------------------- |
| Total Faculty             | Number of faculty records represented in the dataset.                         |
| Total Courses             | Number of course records represented in the dataset.                          |
| Total Sections            | Number of section assignment records.                                         |
| Total Scheduled Hours     | Sum of scheduled teaching hours.                                              |
| Faculty Workload          | Scheduled hours associated with each faculty member.                          |
| Faculty Overload Count    | Number of faculty members flagged for exceeding their defined workload limit. |
| Unassigned Section Count  | Number of sections without an assigned faculty member.                        |
| Department Mismatch Count | Number of records flagged for department inconsistency.                       |
| Duplicate Section Count   | Number of records flagged as duplicate assignments.                           |

KPI definitions, aggregation rules, and treatment of duplicate or invalid records should be documented before formal business acceptance.

# 14. Dashboard Requirements

## 14.1 Overview Dashboard

The overview dashboard should provide a consolidated view of workload information.

Expected components:

- Faculty count.
- Course count.
- Section count.
- Total scheduled hours.
- Workload distribution by department.
- Workload analysis by academic term.
- Faculty workload comparisons.
- Relevant exception indicators.

## 14.2 Faculty Profile Dashboard

The faculty profile dashboard should provide an individual faculty-level view.

Expected components:

- Faculty identification and department.
- Maximum workload hours.
- Assigned teaching hours.
- Course and section assignments.
- Workload distribution.
- Potential overload indicators.

## 14.3 Course Profile Dashboard

The course profile dashboard should provide a course-level view.

Expected components:

- Course code and course name.
- Department and academic term.
- Course credits and contact hours.
- Number of associated sections.
- Faculty assignment distribution.
- Scheduled teaching hours.

# 15. Assumptions and Dependencies

## 15.1 Assumptions

- The supplied datasets represent the academic workload scenario.
- Faculty and course identifiers are intended to support record matching.
- Maximum workload hours are available for relevant faculty records.
- Scheduled teaching hours represent weekly teaching workload.
- The supplied issue log represents validation exceptions.
- Dashboard reporting depends on the availability and quality of source data.

## 15.2 Dependencies

- Availability of faculty, course, and section assignment datasets.
- SQL Server database environment.
- Correctly configured database tables and data types.
- Availability of SQL validation scripts.
- Power BI report and its data-source configuration.
- Consistent field definitions across datasets.

# 16. Risks and Mitigation

| Risk ID | Risk                                   | Potential Impact               | Suggested Mitigation                                       |
| ------- | -------------------------------------- | ------------------------------ | ---------------------------------------------------------- |
| R-01    | Missing or incomplete source data      | Inaccurate workload reporting  | Perform completeness checks.                               |
| R-02    | Duplicate assignment records           | Inflated workload calculations | Implement duplicate detection.                             |
| R-03    | Incorrect faculty-course relationships | Incorrect department analysis  | Validate identifier relationships.                         |
| R-04    | Incorrect workload limits              | False overload indicators      | Confirm workload rules with the relevant authority.        |
| R-05    | Inconsistent date and time formats     | Validation errors              | Standardize data types and formats.                        |
| R-06    | Repeated validation execution          | Duplicate issue-log entries    | Design repeatable and idempotent validation procedures.    |
| R-07    | Incorrect dashboard calculations       | Misleading business insights   | Reconcile dashboard metrics against source queries.        |
| R-08    | Incomplete testing evidence            | Unverified requirements        | Maintain a structured UAT test register and execution log. |

# 17. Acceptance Criteria

The following criteria define the expected conditions for considering the proposed solution requirements satisfied.

| ID    | Acceptance Criteria                                                                                     |
| ----- | ------------------------------------------------------------------------------------------------------- |
| AC-01 | Faculty records can be represented with the required identification and workload fields.                |
| AC-02 | Course records contain the required course information.                                                 |
| AC-03 | Faculty availability records can be associated with faculty identifiers.                                |
| AC-04 | Section assignments can be associated with course and faculty records where assigned.                   |
| AC-05 | SQL validation identifies records that violate the defined validation rules.                            |
| AC-06 | Validation exceptions contain sufficient information for investigation.                                 |
| AC-07 | The overview dashboard presents consolidated workload indicators.                                       |
| AC-08 | The faculty dashboard supports individual workload analysis.                                            |
| AC-09 | The course dashboard supports course-level assignment analysis.                                         |
| AC-10 | Dashboard totals can be reconciled with the corresponding source data and documented calculation rules. |
| AC-11 | Requirements and supporting documentation are available for review.                                     |

Formal acceptance requires execution and recording of the relevant test cases. The criteria above do not represent completed UAT sign-off.

# 18. User Acceptance Testing (UAT) Considerations

UAT should assess whether the implemented solution meets the documented business requirements.

Suggested test scenarios:

| Test ID | Test Scenario                       | Expected Result                                               |
| ------- | ----------------------------------- | ------------------------------------------------------------- |
| UAT-01  | Review faculty records              | Faculty details are displayed correctly.                      |
| UAT-02  | Review course records               | Course information is displayed correctly.                    |
| UAT-03  | Review faculty availability         | Availability records are associated with the correct faculty. |
| UAT-04  | Review section assignments          | Assignment information is displayed correctly.                |
| UAT-05  | Test faculty overload validation    | Faculty exceeding the defined limit are flagged.              |
| UAT-06  | Test unassigned section validation  | Sections without faculty assignments are identified.          |
| UAT-07  | Test department mismatch validation | Inconsistent department records are flagged.                  |
| UAT-08  | Test duplicate section validation   | Duplicate assignments are identified.                         |
| UAT-09  | Review issue log                    | Exception details are available for investigation.            |
| UAT-10  | Review overview dashboard           | Summary workload indicators are displayed.                    |
| UAT-11  | Review faculty profile              | Faculty-level metrics and assignments are displayed.          |
| UAT-12  | Review course profile               | Course-level metrics and assignments are displayed.           |
| UAT-13  | Reconcile dashboard totals          | Dashboard figures agree with the defined source calculations. |
| UAT-14  | Review department filters           | Relevant department-level information is displayed.           |
| UAT-15  | Review term filters                 | Relevant academic-term information is displayed.              |

Detailed UAT test cases, expected results, actual results, and pass/fail records are maintained in `docs/UAT_Plan.md`.

*The scenarios listed above describe proposed UAT coverage. Test execution and pass/fail status should be recorded in the UAT Plan; this BRD does not represent completed UAT sign-off.*

# 19. Requirements Traceability Matrix

The traceability matrix connects business objectives to functional requirements, UAT scenarios, and supporting evidence.

| Business Objective                                                 | Functional Requirements | UAT Test ID                            | Evidence                                                   |
| ------------------------------------------------------------------ | ----------------------- | -------------------------------------- | ---------------------------------------------------------- |
| BO-01: Improve workload visibility                                 | FR-25, FR-26, FR-27     | UAT-10, UAT-11, UAT-12                 | Power BI dashboards                                        |
| BO-02: Identify workload overloads                                 | FR-18                   | UAT-05                                 | SQL validation output and issue log                        |
| BO-03: Detect assignment inconsistencies                           | FR-20, FR-22            | UAT-07                                 | SQL validation results                                     |
| BO-04: Identify duplicate and unassigned sections                  | FR-19, FR-21            | UAT-06, UAT-08                         | SQL validation output and issue log                        |
| BO-05: Centralize data quality exceptions                          | FR-23, FR-24            | UAT-09                                 | Issue log                                                  |
| BO-06: Provide interactive workload reporting                      | FR-25 to FR-30          | UAT-10, UAT-11, UAT-12, UAT-14, UAT-15 | Power BI dashboards                                        |
| BO-07: Support academic resource allocation decisions              | FR-25 to FR-30          | UAT-10, UAT-11, UAT-12, UAT-13         | Dashboard reports and reconciled KPI results               |
| BO-08: Establish structured documentation and validation practices | NFR-07, NFR-08          | UAT-13 and documentation review        | BRD, process maps, ERD, SQL scripts, and UAT documentation |

*Traceability identifies the intended relationship between requirements and test scenarios. Evidence availability and test execution status must be confirmed separately.*

# 20. Expected Business Outcomes

The proposed solution is intended to demonstrate the following outcomes:

1. A structured view of faculty workload information.
2. Improved visibility into teaching assignments and workload distribution.
3. Identification of potential data quality and assignment exceptions.
4. Centralized documentation of validation issues.
5. Interactive reporting for faculty and course-level analysis.
6. Better traceability between business objectives, requirements, validation rules, and dashboard outputs.

These are expected benefits of the proposed approach, not independently measured institutional improvements.

# 21. Future Enhancements

Potential future enhancements include:

- Automated timetable generation.
- Advanced scheduling conflict detection using day and time intervals.
- Faculty workload optimization.
- Role-based access for academic administrators.
- Integration with university ERP systems.
- Automated notifications for workload exceptions.
- Historical workload trend analysis.
- More detailed UAT execution and audit reporting.
- Automated data refresh and monitoring.

# 22. Glossary

| Term             | Definition                                                         |
| ---------------- | ------------------------------------------------------------------ |
| BRD              | Business Requirements Document                                     |
| UAT              | User Acceptance Testing                                            |
| KPI              | Key Performance Indicator                                          |
| ERD              | Entity Relationship Diagram                                        |
| As-Is            | Representation of the current business process                     |
| To-Be            | Representation of the proposed future business process             |
| Faculty Workload | Teaching hours or assignments allocated to a faculty member        |
| Section          | An individual offering or class instance of a course               |
| Data Quality     | The accuracy, completeness, consistency, and validity of data      |
| Exception        | A record identified by a validation rule for further investigation |

# 23. Document Approval

This document is prepared as part of a portfolio project and is intended to demonstrate business analysis and requirements documentation practices.

For this portfolio demonstration, the Author Prathmesh Aghor performed the roles of Business Analyst and QA Reviewer. External academic stakeholder review and formal institutional approval have not been obtained.

| Role                                            | Name             | Status       |
| ----------------------------------------------- | ---------------- | ------------ |
| Project Author / Business Analyst / QA Reviewer | Prathmesh Aghor  | Prepared     |
| Business Owner                                  | To be determined | Not approved |
| Academic Administrator                          | To be determined | Not approved |
| External Technical Reviewer                     | To be determined | Not approved |

---

**End of Document**
