 
# Faculty Workload Intelligence
### Requirements Engineering, SQL-Based Data Validation & Power BI Analytics

[![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)](https://www.microsoft.com/en-us/sql-server)
[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Business Analysis](https://img.shields.io/badge/Business-Analysis-0052CC?style=for-the-badge)](#business-analysis)
[![Data Analytics](https://img.shields.io/badge/Data-Analytics-008272?style=for-the-badge)](#analytics-and-reporting)
[![Data Validation](https://img.shields.io/badge/Data-Validation-6A5ACD?style=for-the-badge)](#sql-data-validation)
[![UAT](https://img.shields.io/badge/UAT-Plan%20Available-orange?style=for-the-badge)](docs/UAT_Plan.md)
[![GitHub last commit](https://img.shields.io/github/last-commit/Prathmesh717/faculty-workload-intelligence)](https://github.com/Prathmesh717/faculty-workload-intelligence/commits/main)
[![GitHub repo size](https://img.shields.io/github/repo-size/Prathmesh717/faculty-workload-intelligence)](https://github.com/Prathmesh717/faculty-workload-intelligence)
[![GitHub issues](https://img.shields.io/github/issues/Prathmesh717/faculty-workload-intelligence)](https://github.com/Prathmesh717/faculty-workload-intelligence/issues)

---

## Project Overview

**Faculty Workload Intelligence** is a data-driven faculty workload management and analytics solution designed to support academic resource planning, faculty allocation, workload validation, and institutional decision-making.

The project brings together business requirements documentation, relational data management, SQL-based validation, issue tracking, and Power BI reporting within a structured analytics workflow.

It focuses on transforming faculty, course, availability, and section-assignment data into meaningful operational insights while identifying potential data-quality and workload-allocation issues.

The solution demonstrates how business analysis, SQL, data validation, and business intelligence can work together to make academic workload information more transparent, structured, and actionable.

## Business Problem

Academic workload management involves coordinating multiple interconnected data elements, including:

- Faculty information and department assignments.
- Course information and academic departments.
- Faculty availability and scheduling constraints.
- Course sections and faculty assignments.
- Workload distribution and allocation issues.

When these elements are maintained or reviewed independently, identifying inconsistencies and understanding workload distribution can become difficult.

This project explores a structured approach to addressing these challenges through documented business requirements, centralized data handling, SQL validation, and interactive analytics.

## Project Objectives

| ID | Objective |
|---|---|
| BO-01 | Organize faculty, course, availability, and section-assignment information. |
| BO-02 | Establish structured business and functional requirements. |
| BO-03 | Validate workload-related data using SQL rules. |
| BO-04 | Identify potential assignment and data-quality issues. |
| BO-05 | Maintain an issue log for identified validation exceptions. |
| BO-06 | Develop interactive dashboards for workload analysis. |
| BO-07 | Support faculty-, course-, and department-level reporting. |
| BO-08 | Define UAT scenarios and acceptance criteria for functional verification. |

## Key Capabilities

### 1. Business Analysis and Requirements Engineering

- Business Requirements Document (BRD).
- Business objectives and stakeholder identification.
- As-Is and To-Be process understanding.
- Functional and non-functional requirements.
- Business rules and data requirements.
- Requirements traceability.
- Acceptance criteria.

### 2. SQL Data Management

- Relational database design.
- Structured data storage.
- Faculty and course data management.
- Faculty availability management.
- Section-assignment data management.
- SQL queries for operational analysis.

### 3. SQL Data Validation

The validation framework addresses potential exceptions such as:

- Faculty workload overload.
- Faculty availability conflicts.
- Department mismatches.
- Duplicate section assignments.
- Unassigned faculty.
- Potential scheduling inconsistencies.

Validation results are intended to support investigation and correction rather than automatically establish that every flagged record is an actual operational conflict.

### 4. Issue Logging

A structured issue log supports the recording and categorization of identified exceptions.

| Issue Category | Purpose |
|---|---|
| Time Overlap | Identify potential scheduling overlaps. |
| Department Mismatch | Identify assignments requiring department validation. |
| Overload | Flag potential workload-limit violations. |
| Duplicate Section | Identify possible duplicate assignments. |
| Unassigned Faculty | Identify sections without an assigned faculty member. |

### 5. Power BI Analytics and Reporting

The Power BI report includes three dashboard pages:

- **Overview Dashboard:** High-level workload and allocation insights.
- **Faculty Profile:** Faculty-level workload and assignment analysis.
- **Course Profile:** Course-level allocation and assignment analysis.

The dashboards are designed to help users explore workload information and identify records requiring further review.

## Technology Stack

| Technology | Purpose |
|---|---|
| Microsoft SQL Server | Relational database and SQL-based data processing |
| SQL | Data querying, validation, and issue identification |
| Microsoft Power BI | Interactive dashboards and reporting |
| CSV | Structured source datasets |
| Business Analysis | Requirements gathering and documentation |
| UAT | Test planning and acceptance criteria |
| Git & GitHub | Version control and project documentation |

## Solution Workflow

```text
Source Data (CSV)
       |
       v
Data Ingestion
       |
       v
Microsoft SQL Server
       |
       v
SQL Data Validation
       |
       v
Issue Identification & Logging
       |
       v
Validated / Reviewed Data
       |
       v
Power BI Reporting
       |
       v
Faculty & Course-Level Insights
```

*The workflow represents the intended solution process. Actual execution and validation of every stage should be verified against the implementation.*

## Data Overview

The source datasets cover four major business entities:

| Dataset | Description |
|---|---|
| `campus_faculty.csv` | Faculty information |
| `campus_courses.csv` | Course information |
| `campus_faculty_availability.csv` | Faculty availability records |
| `campus_sections_assignments.csv` | Course section and faculty assignment records |

The source dataset contains the following reported record counts:

| Entity | Records |
|---|---:|
| Faculty | 281 |
| Courses | 66 |
| Faculty Availability | 949 |
| Section Assignments | 1,010 |

*These are source dataset counts, not independently verified counts from a completed database import.*

## Dashboard Preview

The Power BI report is organized into three main analytical views.

### Overview Dashboard

![Overview Dashboard](screenshots/1.Overview_Dashboard.png)

### Faculty Profile

![Faculty Profile](screenshots/2.Faculty_Profile.png)

### Course Profile

![Course Profile](screenshots/3.Course_Profile.png)

> If a screenshot does not render, check the actual filename and capitalization inside the `screenshots/` directory.

## Repository Structure

```text
faculty-workload-intelligence/
│
├── data/
│   ├── raw/
│   │   ├── campus_faculty.csv
│   │   ├── campus_courses.csv
│   │   ├── campus_faculty_availability.csv
│   │   └── campus_sections_assignments.csv
│   │
│   └── sql/
│       ├── 02_validations.sql
│       └── 03_issue_log.sql
│
├── docs/
│   ├── BRD.md
│   ├── UAT_Plan.md
│   ├── erd/
│   ├── issue_log/
│   └── process_maps/
│
├── reports/
│   └── [Power BI report, if included]
│
├── screenshots/
│   ├── 1.Overview_Dashboard.png
│   ├── 2.Faculty_Profile.png
│   ├── 3.Course_Profile.png
│   └── UAT_Testing.png
│
├── readme.md
└── LICENSE
```

*This is the intended documentation layout. Confirm the actual repository contents before treating every illustrative path as an existing file.*

## Business Analysis Documentation

The project includes documentation to demonstrate the requirements and testing approach.

| Document | Description |
|---|---|
| [Business Requirements Document](docs/BRD.md) | Business objectives, scope, requirements, business rules, and acceptance criteria |
| [UAT Plan](docs/UAT_Plan.md) | UAT approach, scenarios, expected results, and execution records |
| [Entity Relationship Diagram](docs/erd/) | Database entity and relationship reference |
| [Process Maps](docs/process_maps/) | Current-state and future-state process references |

## UAT and Quality Assurance

A structured User Acceptance Testing plan has been prepared to define how the proposed business requirements can be verified.

The plan includes:

- UAT objectives and scope.
- Test scenarios and expected results.
- Test priorities.
- Execution status tracking.
- Defect identification and management.
- Evidence references.
- Entry and exit criteria.

**Current testing status:** UAT scenarios are documented in the plan. Execution results should be updated only after the corresponding tests have actually been performed.

## Running the Project Locally

### Prerequisites

- Docker Desktop for macOS.
- Microsoft SQL Server 2022 Developer Edition container.
- SQL Server command-line tools (`sqlcmd`).
- DBeaver Community Edition (optional).

### 1. Clone the repository

```bash
git clone https://github.com/Prathmesh717/faculty-workload-intelligence.git
cd faculty-workload-intelligence
```

### 2. Start SQL Server

If Docker Desktop is running and the SQL Server container has already been created:

```bash
docker start faculty-sql
```

### 3. Connect to SQL Server

```bash
docker exec -it faculty-sql /opt/mssql-tools18/bin/sqlcmd \
-S localhost -U sa -C
```

Enter your SQL Server password when prompted.

### 4. Create the database

```sql
CREATE DATABASE FacultyManagement;
GO

USE FacultyManagement;
GO
```

### 5. Import the datasets

Create the corresponding tables and import the CSV datasets into SQL Server.

| CSV File | Target Table |
|---|---|
| `campus_faculty.csv` | `campus_faculty` |
| `campus_courses.csv` | `campus_courses` |
| `campus_faculty_availability.csv` | `campus_faculty_availability` |
| `campus_sections_assignments.csv` | `campus_sections_assignments` |

Ensure that column names, data types, primary keys, and foreign keys match the SQL scripts before importing.

### 6. Execute SQL validation scripts

Review the scripts and their dependencies before execution.

```sql
:r data/sql/02_validations.sql
:r data/sql/03_issue_log.sql
```

The commands above are illustrative `sqlcmd` script directives; execute them from a working directory where the script paths are accessible, or use the appropriate full paths.

### 7. Explore the dashboards

Open the available Power BI report in Power BI Desktop.

**macOS note:** Power BI Desktop is a Windows application. A compatible Windows environment or remote Windows machine is required to edit and refresh `.pbix` reports.

## Project Limitations and Considerations

- Workload and scheduling flags require business-rule validation before being treated as confirmed conflicts.
- Date-range overlap alone does not establish an actual day-and-time scheduling conflict.
- Issue logging should be checked for duplicate records when validation scripts are rerun.
- Data-quality exceptions should be reviewed before downstream reporting.
- Dashboard refresh and database integration should be verified in the target environment.
- UAT execution and external stakeholder approval are not claimed unless supported by execution evidence.

## Future Enhancements

- Implement idempotent issue logging.
- Improve validation logic for actual day-and-time scheduling conflicts.
- Add automated data-quality checks.
- Introduce workload trend analysis.
- Add department-level comparative reporting.
- Implement scheduled data refresh.
- Strengthen role-based access and auditability.
- Complete UAT execution with documented evidence and defect closure.

## Skills Demonstrated

- Business Requirements Documentation (BRD)
- Requirements Gathering and Analysis
- Functional and Non-Functional Requirements
- SQL Server and SQL Querying
- Relational Database Concepts
- Data Validation and Quality Checks
- Issue Logging and Defect Management
- User Acceptance Testing (UAT)
- Power BI Dashboard Design
- Data Analysis and Business Reporting
- Git and GitHub

## Project Developer

**Prathmesh Aghor**

Computer Engineering Graduate | Business Analysis | SQL | Power BI | Data Analytics

- GitHub: [Prathmesh717](https://github.com/Prathmesh717)

## License

See the repository's [LICENSE](LICENSE) file for the applicable license terms.

---

**Faculty Workload Intelligence**  
*Connecting business requirements, structured data validation, and actionable academic workload analytics.*
