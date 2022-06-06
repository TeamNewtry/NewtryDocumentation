# Test Plan Template

## Table of contents

- [1. Introduction](#1-introduction)
    * [1.1 Purpose](#11-purpose)
    * [1.2 Scope](#12-scope)
    * [1.3 Intended Audience](#13-intended-audience)
    * [1.4 Document Terminology and Acronyms](#14-document-terminology-and-acronyms)
    * [1.5  References](#15--references)
    * [1.6 Document Structure](#16-document-structure)
- [2. Evaluation Mission and Test Motivation](#2-evaluation-mission-and-test-motivation)
    * [2.1 Background](#21-background)
    * [2.2 Evaluation Mission](#22-evaluation-mission)
    * [2.3 Test Motivators](#23-test-motivators)
- [3. Target Test Items](#3-target-test-items)
- [4. Outline of Planned Tests](#4-outline-of-planned-tests)
    * [4.1 Outline of Test Inclusions](#41-outline-of-test-inclusions)
    * [4.2 Outline of Other Candidates for Potential Inclusion](#42-outline-of-other-candidates-for-potential-inclusion)
    * [4.3 Outline of Test Exclusions](#43-outline-of-test-exclusions)
- [5. Test Approach](#5-test-approach)
    * [5.1 Initial Test-Idea Catalogs and Other Reference Sources](#51-initial-test-idea-catalogs-and-other-reference-sources)
    * [5.2 Testing Techniques and Types](#52-testing-techniques-and-types)
        + [5.2.1 Data and Database Integrity Testing](#521-data-and-database-integrity-testing)
        + [5.2.2 Functional Testing](#522-functional-testing)
        + [5.2.3 Business Cycle Testing](#523-business-cycle-testing)
        + [5.2.4 User Interface Testing](#524-user-interface-testing)
        + [5.2.5 Performance Profiling](#525-performance-profiling)
        + [5.2.6 Load Testing](#526-load-testing)
        + [5.2.7 Stress Testing](#527-stress-testing)
        + [5.2.8 Volume Testing](#528-volume-testing)
        + [5.2.9 Security and Access Control Testing](#529-security-and-access-control-testing)
        + [5.2.10 Failover and Recovery Testing](#5210-failover-and-recovery-testing)
        + [5.2.11 Configuration Testing](#5211-configuration-testing)
        + [5.2.12 Installation Testing](#5212-installation-testing)
- [6. Entry and Exit Criteria](#6-entry-and-exit-criteria)
    * [6.1 Test Plan](#61-test-plan)
        + [6.1.1 Test Plan Entry Criteria](#611-test-plan-entry-criteria)
        + [6.1.2 Test Plan Exit Criteria](#612-test-plan-exit-criteria)
        + [6.1.3 Suspension and Resumption Criteria](#613-suspension-and-resumption-criteria)
    * [6.2 Test Cycles](#62-test-cycles)
        - [6.2.1 Test Cycle Entry Criteria](#621-test-cycle-entry-criteria)
        - [6.2.2 Test Cycle Exit Criteria](#622-test-cycle-exit-criteria)
        - [6.2.3 Test Cycle Abnormal Termination](#623-test-cycle-abnormal-termination)
- [7. Deliverables](#7-deliverables)
- [7.1 Test Evaluation Summaries](#71-test-evaluation-summaries)
- [7.2 Reporting on Test Coverage](#72-reporting-on-test-coverage)
- [7.3 Perceived Quality Reports](#73-perceived-quality-reports)
- [7.4 Incident Logs and Change Requests](#74-incident-logs-and-change-requests)
- [7.5 Smoke Test Suite and Supporting Test Scripts](#75-smoke-test-suite-and-supporting-test-scripts)
- [7.6      Additional Work Products](#76------additional-work-products)
    * [7.6.1     Detailed Test Results](#761-----detailed-test-results)
    * [7.6.2     Additional Automated Functional Test Scripts](#762-----additional-automated-functional-test-scripts)
    * [7.6.3     Test Guidelines](#763-----test-guidelines)
    * [7.6.4     Traceability Matrices](#764-----traceability-matrices)
- [8. Testing Workflow](#8-testing-workflow)
- [9. Environmental Needs](#9-environmental-needs)
    * [9.1 Base System Hardware](#91-base-system-hardware)
    * [9.2 Base Software Elements in the Test Environment](#92-base-software-elements-in-the-test-environment)
    * [9.3 Productivity and Support Tools](#93-productivity-and-support-tools)
    * [9.4 Test Environment Configurations](#94-test-environment-configurations)
- [10. Responsibilities, Staffing, and Training Needs](#10-responsibilities--staffing--and-training-needs)
    * [10.1 People and Roles](#101-people-and-roles)
    * [10.2 Staffing and Training Needs](#102-staffing-and-training-needs)
- [11. Iteration Milestones](#11-iteration-milestones)
- [12. Risks, Dependencies, Assumptions, and Constraints](#12-risks--dependencies--assumptions--and-constraints)
- [13. Management Process and Procedures](#13-management-process-and-procedures)

## 1. Introduction

### 1.1 Purpose

The purpose of the Iteration Test Plan is to gather all of the information
necessary to plan and control the test effort for a given iteration. It
describes the approach to testing the software. This Test Plan for Newtry
supports the following objectives:

- Identifies the items that should be targeted by the tests.
- Identifies the motivation for and ideas behind the test areas to be covered.
- Outlines the testing approach that will be used.
- Identifies the required resources and provides an estimate of the test
  efforts.

### 1.2 Scope

This document describes the procedure of testing in the Newtry project. For
Newtry following types of testing are planned:

- Unit tests
- Integration tests
- Exploratory testing

Test for security and performance will be avoided due to not publishing Newtry
in the near future. In addition, basic security is currently fundamentally
guaranteed by the technology used.

### 1.3 Intended Audience

This document is primarily addressed to the team members who are responsible for
testing. It provides an overview in the testing process for the team during
implementation.

### 1.4 Document Terminology and Acronyms

| Abbr | Abbreviation                        |
|------|-------------------------------------|
| API  | Application Programmable Interface  |
| CI   | Continuous Integration              |
| CD   | Continuous Delivery/Deployment      |
| n/a  | not applicable                      |
| SRS  | Software Requirements Specification |
| tbd  | to be determined                    |
| UI   | User Interface                      |
| VC   | Version Control                     |
| TDD  | Test Driven Development             |

### 1.5  References

| Title                                                                   | Date       | Publishing organization   |
| ------------------------------------------------------------------------|:----------:| ------------------------- |
| [Blog](https://newtry.ionae.de/)                                        |  04. 2022  | Newtry                    |  
| [GitHub Repository](https://github.com/TeamNewtry/Newtry)               |  04. 2022  | Newtry                    |
| [UC1 Searchbar](../use_cases/UC1_Searchbar.md)                          |  04. 2022  | Newtry                    |
| [UC2 Ingredients](../use_cases/UC2_Ingredients.md)                      |  04. 2022  | Newtry                    |
| [UC3 Nutrition](../use_cases/UC3_Nutrition.md)                          |  04. 2022  | Newtry                    |
| [UC4 Scanner](../use_cases/UC4_Scanner.md)                              |  04. 2022  | Newtry                    |
| [UC5 ClimateImpact](../use_cases/UC5_ClimateImpact.md)                  |  04. 2022  | Newtry                    |
| [UC6 ShowRating](../use_cases/UC6_ShowRating.md)                        |  04. 2022  | Newtry                    |
| [UC7 SubmitRating](../use_cases/UC7_SubmitRating.md)                    |  04. 2022  | Newtry                    |
| [UC8 ShowComments](../use_cases/UC8_ShowComments.md)                    |  04. 2022  | Newtry                    |
| [UC9 SubmitComments](../use_cases/UC9_SubmitComments.md)                |  04. 2022  | Newtry                    |
| [Test Plan](./test_plan.md)                                             |  04. 2022  | Newtry                    |
| [SRS](./SRS.md)                                                         |  04. 2022  | Newtry                    |
| [SAD](./SAD.md)                                                         |  04. 2022  | Newtry                    |

## 2. Evaluation Mission and Test Motivation

### 2.1 Background

Testing is an important part of every tech project. By testing with different
tools for different purposes you are able to detect bugs for being able to fix
them before publishing code. Thinking about what might happen when bugs are
published leads to attention for good code which leads to the testing aspect. To
ensure having a stable version of Newtry a few testing strategies should be
implemented.

### 2.2 Evaluation Mission

During testing phase, we want to find as many functionality-critical bugs as
possible to ensure that the software quality is good enough for being used.
Furthermore, we want to see how stable and resilient the software can be. In
addition, testing should detect a lot of minor bugs related to UI/UX as well.

### 2.3 Test Motivators

Main motivation of testing is finding bugs early so they don't become a big
problem later. Also important is quality, which means the software is well
implemented on the one hand and delivers what it is supposed to deliver on the
other hand. Last but not least, testing gives you peace of mind when adding new
features because testing verifies that everything works after modifying the
code.

## 3. Target Test Items

- React Native Frontend
- JavaScript Backend

## 4. Outline of Planned Tests

### 4.1 Outline of Test Inclusions

*Frontend: React Native*:

- UI testing of Components
- Unit testing
- Integration testing

*Backend: JavaScript*:

- Unit testing
- Integration testing
- Api testing

The tests will not be tested and therefore does not count into test coverage.

### 4.2 Outline of Other Candidates for Potential Inclusion

There is nothing to add.

### 4.3 Outline of Test Exclusions

Tests which are not taken into account:

- Performance tests
- Security tests
- Stress tests

## 5. Test Approach

### 5.1 Initial Test-Idea Catalogs and Other Reference Sources

n/a

### 5.2 Testing Techniques and Types

#### 5.2.1 Data and Database Integrity Testing


|                       | Description                                                                         |
|-----------------------|-------------------------------------------------------------------------------------|
|Technique Objective    | Test the database with API calls                                                    |
|Technique              | Invoke the database access methods with API calls                                   |
|Oracles                | Database returns the correct and expected data with their coressponding status codes |
|Required Tools         | Postman                                                                             |
|Success Criteria       | All requests pass as expected                                                       |
|Special Considerations | -                                                                                   |

#### 5.2.2 Functional Testing

n/a

#### 5.2.3 Business Cycle Testing

n/a

#### 5.2.4 User Interface Testing


|                       | Description                                                                                                                                                                           |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Technique Objective    | Test wether the UI generated by the application is correct                                                                                                                            |
|Technique              | Write JEST (JavaScript) files wich test single components. [Further Information](https://jestjs.io/docs/tutorial-react-native)                                                        |
|Oracles                | Expect the UI to be rendered as expected. Test execution logs are added to the [test coverage report](https://github.com/TeamNewtry/Newtry/blob/main/coverage/lcov-report/index.html) |
|Required Tools         | JEST                                                                                                                                                                                  |
|Success Criteria       | All tests pass. Most important components are covered                                                                                                                                 |
|Special Considerations | Mock firebase, react and other dependencies                                                                                                                                           |

#### 5.2.5 Performance Profiling

n/a

#### 5.2.6 Load Testing

n/a

#### 5.2.7 Stress Testing

n/a

#### 5.2.8 Volume Testing

n/a

#### 5.2.9 Security and Access Control Testing

n/a

#### 5.2.10 Failover and Recovery Testing

n/a

#### 5.2.11 Configuration Testing

n/a

#### 5.2.12 Installation Testing

n/a

## 6. Entry and Exit Criteria

### 6.1 Test Plan

#### 6.1.1 Test Plan Entry Criteria

When a code pipeline runs during deployment, the tests described above for
Frontend and Backend (except for exploratory tests) should be triggered
automatically.

#### 6.1.2 Test Plan Exit Criteria

The test plan should be finished when every test has passed.

#### 6.1.3 Suspension and Resumption Criteria

If there is a feature that isn't ready yet, but you want to check if the rest
works, a test can be suspended. However, this must be reinstated before
publication at the latest.

### 6.2 Test Cycles

##### 6.2.1 Test Cycle Entry Criteria

Api does not deliver data due to overload.

##### 6.2.2 Test Cycle Exit Criteria

Exit after getting the data.

##### 6.2.3 Test Cycle Abnormal Termination

Termination after too many attempts.

## 7. Deliverables

## 7.1 Test Evaluation Summaries

The tests create summaries independently. After the pipeline has passed, we are
able to inspect those summaries.

## 7.2 Reporting on Test Coverage

Coverage Reported by Jest:
![Coverage Report](https://github.com/TeamNewtry/NewtryDocumentation/blob/main/resources/coverage_report.PNG?raw=true)
[Latest Coverage Report](https://github.com/TeamNewtry/Newtry/blob/main/coverage/lcov-report/index.html)
## 7.3 Perceived Quality Reports

For code quality we use ES Lint.

## 7.4 Incident Logs and Change Requests

An agile process model is used throughout the project, including
a [Kanbanboard](https://dhbw-karlsruhe.myjetbrains.com/youtrack/agiles/108-118/current)
on which the tasks and bugs can be seen. For code changes github provides
Merge-Requests which can be created each time a feature branch needs to be
merged into the main branch.

## 8. Testing Workflow

1. Local testing
2. Exploratory testing
3. Commit and push trigger tests in the pipeline

## 9. Environmental Needs

This section presents the non-human resources required for the Test Plan.

### 9.1 Base System Hardware

The following table sets forth the system resources for the test effort
presented in this Test Plan.

| Resource                                                                | Quantity | Name and Type |
|-------------------------------------------------------------------------|----------|---------------|
| Firebase Server                                                         |     1     |      API Provider / Database         |
| OpenFoodFacts Server                                                         |     1     |      API Provider / Database         |
| GitHub CI/CD                                                         |          |      Testing, version control         |

### 9.2 Base Software Elements in the Test Environment

The following base software elements are required in the test environment for
this Test Plan

| Software Element Name |  Type and Other Notes                        |
|-----------------------|----------------------------------------------|
| Jest        | Test framework                            |
| React-native        | Framework                            |
| WebStorm        | Test Runner/ IDE                            |

### 9.3 Productivity and Support Tools

The following tools will be employed to support the test process for this Test
Plan.

| Tool Category or Type             | Tool Brand Name | Vendor or In-house | Version |
|-----------------------------------|-----------------|--------------------|---------|
| Test Management                   |         Jest        |      Meta             |     latest    |
| Test Coverage Monitor or Profiler |       Jest          |      Meta              |     latest    |
| Project Management                |       YouTrack          |   JetBrains                 |  latest       |
| DBMS tools                        |       Firebase          |   Google                 |  latest       |

### 9.4 Test Environment Configurations

n/a

## 10. Responsibilities, Staffing, and Training Needs

### 10.1 People and Roles

This table shows the staffing assumptions for the test effort.

| Human Resources                          |                                                                         |                                                                                                                                                                                                                                                                                   |
|------------------------------------------|-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Role                                     | Minimum Resources Recommended (number of full-time roles allocated)     | Specific Responsbilities or Comments                                                                                                                                                                                                                                              |
| Test Manager                             |                       1                                                  | Provides management oversight. Responsibilities include: planning and logistics agree mission identify motivators acquire appropriate resources present management reporting advocate the interests of test evaluate effectiveness of test effort                                 |
| Test Designer                            |                       2                                                  | Defines the technical approach to the implementation of the test effort. Responsibilities include: define test approace define test automation architecture verify test techniques define testability elements structure test implementation                                      |
| Tester                                   |                       4                                                  | Implements and executes the tests. Responsibilities include: implement tests and test suites execute test suites log results analyze and recover from test failures document incidents                                                                                            |
| Test System Administrator                |                       1                                                  | Ensurs test environment and assets are managed and maintained. Responsibilities include: administer test management system install and support access to, and recovery of, test environment configurations and test labs                                                          |
| Database Administrator, Database Manager |                       1                                                  | Ensures test data (database) environment and assets are managed andmaintained. Responsibilities include: support the administration of test data and test beds (database)                                                                                                         |
| Designer                                 |                       1                                                  | Identifies and defines the operations, attributes, and associations of the test classes. Responsibilities include: defines the test classes required to support testability requirements as defined by the test team                                                              |
| Implementer                              |                       4                                                  | Implements and unit tests the test classes and test packages. Responsibilities include: creates the test components required to support testability requirements as defined by the designer                                                                                       |

### 10.2 Staffing and Training Needs

n/a

## 11. Iteration Milestones

The test coverage should be at least 20%.

## 12. Risks, Dependencies, Assumptions, and Constraints

| Risk                                    | Mitigation Strategy                                           | Contingency (Risk is realized)                                                                              |
|-----------------------------------------|---------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| Code is not written in a testable way            | refactor code for better testability | publish new refactored code                                                                     |
| test runner is not able to execute tests            | mock react/firebase dependencies | fix test execution configuration                                                                 |
| UI tests fail         | UI updated? Yes: create new snapshot No: refactor code | publish refactored code                                                                 |

## 13. Management Process and Procedures

n/a
