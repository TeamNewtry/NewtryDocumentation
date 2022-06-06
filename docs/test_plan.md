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


|                       | Description                                                                                                                                                                          |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Technique Objective    | Test wether the UI generated by the application is correct                                                                                                                           |
|Technique              | Write JEST (JavaScript) files with test single components. [Further Information](https://jestjs.io/docs/tutorial-react-native)                                                       |
|Oracles                | Expect the UI to be rendered as expected. Test execution logs are added to the [test coverage report](https://github.com/TeamNewtry/Newtry/blob/main/coverage/lcov-report/index.html) |
|Required Tools         | JEST                                                                                                                                                                                 |
|Success Criteria       | All tests pass. Most important components are covered                                                                                                                                |
|Special Considerations | Mock firebase, react and other dependencies                                                                                                                                          |

#### 5.2.5 Performance Profiling


|                       | Description                                                         |
|-----------------------|---------------------------------------------------------------------|
|Technique Objective    |   [Exercise behaviors for designated functional transactions or business functions under the following conditions to observe and log target behavior and application performance data:; normal anticipated workload; anticipated worst-case workload]  |
|Technique              |   [Use Test Procedures developed for Function or Business Cycle Testing.; Modify data files to increase the number of transactions or the scripts to increase the number of iterations that occur in each transaction.; Scripts should be run on one machine (best case is to benchmark single user, single transaction) and should be repeated with multiple clients (virtual or actual, see Special Considerations below).]  |
|Oracles                |    [Outline one or more strategies that can be used by the technique to accurately observe the outcomes of the test. The oracle combines elements of both the method by which the observation can be made and the characteristics of specific outcome that indicate probable success or failure. Ideally, oracles will be self-verifying, allowing automated tests to make an initial assessment of test pass or failure, however, be careful to mitigate the risks inherent in automated results determination.]   |
|Required Tools         |   [The technique requires the following tools:; Test Script Automation Tool; an application performance profiling tool, such as Rational Quantify; installation-monitoring tools (registry, hard disk, CPU, memory, and so on; resourse-constraining tools; for example, Canned Heat]  |
|Success Criteria       |  [The technique supports testing:; Single Transaction or single user: Successful emulation of the transaction scripts without any failures due to test implementation problems.; Multiple transactions or multiple users: Successful emulation of the workload without any failures due to test implementation problems.]   |
|Special Considerations |  [Comprehensive performance testing includes having a background workload on the server.; There are several methods that can be used to perform this, including:; "Drive transactions" directly to the server, usually in the form of Structured Query Language (SQL) calls.; Create "virtual" user load to simulate many clients, usually several hundred. Remote Terminal Emulation tools are used to accomplish this load. This technique can also be used to load the network with "traffic".; Use multiple physical clients, each running test scripts, to place a load on the system.; Performance testing should be performed on a dedicated machine or at a dedicated time. This permits full control and accurate measurement.; The databases used for Performance Testing should be either actual size or scaled equally.]   |

#### 5.2.6 Load Testing

[Load testing is a performance test that subjects the target-of-test to varying
workloads to measure and evaluate the performance behaviors and abilities of the
target-of-test to continue to function properly under these different workloads.
The goal of load testing is to determine and ensure that the system functions
properly beyond the expected maximum workload. Additionally, load testing
evaluates the performance characteristics, such as response times, transaction
rates, and other time-sensitive issues.

[Note: Transactions in the following table refer to "logical business transactions". These transactions are defined as specific functions that an end user of the system is expected to perform using the application, such as add or modify a given contract.]

|                       | Description                                                         |
|-----------------------|---------------------------------------------------------------------|
|Technique Objective    |  [Exercise designated transactions or business cases under varying workload conditions to observe and log target behavior and system performance data.] |
|Technique              |  [Use Transaction Test Scripts developed for Function or Business Cycle Testing as a basis, but remember to remove unnecessary interactions and delays.; Modify data files to increase the number of transactions or the tests to increase the number of times each transaction occurs.; Workloads should include—for example, daily, weekly, and monthly—peak loads.; Workloads should represent both average as well as peak loads.; Workloads should represent both instantaneous and sustained peaks.; The workloads should be executed under different Test Environment Configurations.]   |
|Oracles                |  [Outline one or more strategies that can be used by the technique to accurately observe the outcomes of the test. The oracle combines elements of both the method by which the observation can be made and the characteristics of specific outcome that indicate probable success or failure. Ideally, oracles will be self-verifying, allowing automated tests to make an initial assessment of test pass or failure, however, be careful to mitigate the risks inherent in automated results determination.]   |
|Required Tools         |   [The technique requires the following tools:; Test Script Automation Tool; Transaction load scheduling and control tool; installation-monitoring tools (registry, hard disk, CPU, memory, and so on); resource-constraining tools; for example, Canned Heat; data-generation tools]  |
|Success Criteria       |  [The technique supports the testing of Workload Emulation, which is the successful emulation of the workload without any failures due to test implementation problems.]   |
|Special Considerations |  [Load testing should be performed on a dedicated machine or at a dedicated time. This permits full control and accurate measurement.; The databases used for load testing should be either actual size or scaled equally.]   |

#### 5.2.7 Stress Testing

[Stress testing is a type of performance test implemented and executed to
understand how a system fails due to conditions at the boundary, or outside of,
the expected tolerances. This typically involves low resources or competition
for resources. Low resource conditions reveal how the target-of-test fails that
is not apparent under normal conditions. Other defects might result from
competition for shared resources, like database locks or network bandwidth,
although some of these tests are usually addressed under functional and load
testing.

[Note: References to transactions in the following table refer to logical business transactions.]

|                       | Description                                                         |
|-----------------------|---------------------------------------------------------------------|
|Technique Objective    |   [Exercise the target-of-test functions under the following stress conditions to observe and log target behavior that identifies and documents the conditions under which the system fails to continue functioning properly:; little or no memory available on the server (RAM and persistent storage space); maximum actual or physically capable number of clients connected or simulated; multiple users performing the same transactions against the same data or accounts; "overload" transaction volume or mix (see Performance Profiling above)]  |
|Technique              |   [Use tests developed for Performance Profiling or Load Testing.; To test limited resources, tests should be run on a single machine, and RAM and persistent storage space on the server should be reduced or limited.; For remaining stress tests, multiple clients should be used, either running the same tests or complementary tests to produce the worst-case transaction volume or mix.]  |
|Oracles                |  [Outline one or more strategies that can be used by the technique to accurately observe the outcomes of the test. The oracle combines elements of both the method by which the observation can be made and the characteristics of specific outcome that indicate probable success or failure. Ideally, oracles will be self-verifying, allowing automated tests to make an initial assessment of test pass or failure, however, be careful to mitigate the risks inherent in automated results determination.]   |
|Required Tools         |  [The technique requires the following tools:; Test Script Automation Tool; Transaction load scheduling and control tool; installation-monitoring tools (registry, hard disk, CPU, memory, and so on; resource-constraining tools; for example, Canned Heat; data-generation tools]   |
|Success Criteria       |  [The technique supports the testing of Stress Emulation. The system can be emulated successfully in one or more conditions defined as stress conditions, and an observation of the resulting system state, during and after the condition has been emulated, can be captured.]   |
|Special Considerations |  [Stressing the network may require network tools to load the network with messages or packets.; The persistent storage used for the system should temporarily be reduced to restrict the available space for the database to grow.; Synchronize the simultaneous clients accessing of the same records or data accounts.]   |

#### 5.2.8 Volume Testing

[Volume testing subjects the target-of-test to large amounts of data to determine if limits are reached that cause the software to fail. Volume testing also identifies the continuous maximum load or volume the target-of-test can handle for a given period. For example, if the target-of-test is processing a set of database records to generate a report, a Volume Test would use a large test database, and would check that the software behaved normally and produced the correct report.]

|                       | Description                                                         |
|-----------------------|---------------------------------------------------------------------|
|Technique Objective    |  [Stressing the network may require network tools to load the network with messages or packets.; The persistent storage used for the system should temporarily be reduced to restrict the available space for the database to grow.; Synchronize the simultaneous clients accessing of the same records or data accounts.]   |
|Technique              |  [Use tests developed for Performance Profiling or Load Testing.; Multiple clients should be used, either running the same tests or complementary tests to produce the worst-case transaction volume or mix (see Stress Testing) for an extended period.; Maximum database size is created (actual, scaled, or filled with representative data), and multiple clients are used to run queries and report transactions simultaneously for extended periods.]]   |
|Oracles                |   [Outline one or more strategies that can be used by the technique to accurately observe the outcomes of the test. The oracle combines elements of both the method by which the observation can be made and the characteristics of specific outcome that indicate probable success or failure. Ideally, oracles will be self-verifying, allowing automated tests to make an initial assessment of test pass or failure, however, be careful to mitigate the risks inherent in automated results determination.]  |
|Required Tools         |   [The technique requires the following tools:; Test Script Automation Tool; Transaction load scheduling and control tool; installation-monitoring tools (registry, hard disk, CPU, memory, and so on; resource-constraining tools; for example, Canned Heat; data-generation tools]  |
|Success Criteria       |    [The technique supports the testing of Volume Emulation. Large quantities of users, data, transactions, or other aspects of the system use under volume can be successfully emulated and an observation of the system state changes over the duration of the volume test can be captured.]   |
|Special Considerations |  [What period of time would be considered an acceptable time for high volume conditions, as noted above?]   |

#### 5.2.9 Security and Access Control Testing

[Security and Access Control Testing focuses on two key areas of security:; Application-level security, including access to the Data or Business Functions; System-level Security, including logging into or remotely accessing to the system; Based on the security you want, application-level security ensures that actors are restricted to specific functions or use cases, or they are limited in the data that is available to them. For example, everyone may be permitted to enter data and create new accounts, but only managers can delete them. If there is security at the data level, testing ensures that "user type one" can see all customer information, including financial data, however, "user type two" only sees the demographic data for the same client.; System-level security ensures that only those users granted access to the system are capable of accessing the applications and only through the appropriate gateways.]

|                       | Description                                                         |
|-----------------------|---------------------------------------------------------------------|
|Technique Objective    |  [Exercise the target-of-test under the following conditions to observe and log target behavior:; Application-level Security: an actor can access only those functions or data for which their user type is provided permissions.; System-level Security: only those actors with access to the system and applications are permitted to access them].   |
|Technique              |  [Application-level Security: Identify and list each user type and the functions or data for which each type has permissions.; Create tests for each user type and verify each permission by creating transactions specific to each user type.; Modify user type and rerun tests for same users. In each case, verify those additional functions or data are correctly available or denied.; System-level Access: See Special Considerations below.]   |
|Oracles                |  [Outline one or more strategies that can be used by the technique to accurately observe the outcomes of the test. The oracle combines elements of both the method by which the observation can be made and the characteristics of specific outcome that indicate probable success or failure. Ideally, oracles will be self-verifying, allowing automated tests to make an initial assessment of test pass or failure, however, be careful to mitigate the risks inherent in automated results determination.] |
|Required Tools         |  [The technique requires the following tools:; Test Script Automation Tool; "Hacker" security breach and probing tools; OS Security Administration tools]   |
|Success Criteria       |  [The technique supports the testing of the appropriate functions or data affected by security settings can be tested for each known actor type.]   |
|Special Considerations |  [Access to the system must be reviewed or discussed with the appropriate network or systems administrator. This testing may not be required as it may be a function of network or systems administration.]   |

#### 5.2.10 Failover and Recovery Testing

[Failover and recovery testing ensures that the target-of-test can successfully
failover and recover from a variety of hardware, software, or network
malfunctions with undue loss of data or data integrity.

[For those systems that must be kept running, failover testing ensures that when a failover condition occurs, the alternate or backup systems properly "take over" for the failed system without any loss of data or transactions.; Recovery testing is an antagonistic test process in which the application or system is exposed to extreme conditions, or simulated conditions, to cause a failure, such as device Input/Output (I/O) failures, or invalid database pointers and keys. Recovery processes are invoked, and the application or system is monitored and inspected to verify proper application, or system, and data recovery has been achieved.]

|                       | Description                                                         |
|-----------------------|---------------------------------------------------------------------|
|Technique Objective    |  [Simulate the failure conditions and exercise the recovery processes (manual and automated) to restore the database, applications, and system to a desired, known state. The following types of conditions are included in the testing to observe and log behavior after recovery:; power interruption to the client; power interruption to the server; communication interruption via network servers; interruption, communication, or power loss to DASD (Dynamic Access Storage Devices) and DASD controllers; incomplete cycles (data filter processes interrupted, data synchronization processes interrupted); invalid database pointers or keys; invalid or corrupted data elements in database]  |
|Technique              |  [The tests already created for Function and Business Cycle testing can be used as a basis for creating a series of transactions to support failover and recovery testing, primarily to define the tests to be run to test that recovery was successful.; Power interruption to the client: power down the PC.; Power interruption to the server: simulate or initiate power down procedures for the server.; Interruption via network servers: simulate or initiate communication loss with the network (physically disconnect communication wires or power down network servers or routers).; Interruption, communication, or power loss to DASD and DASD controllers: simulate or physically eliminate communication with one or more DASDs or DASD controllers.; Once the above conditions or simulated conditions are achieved, additional transactions should be executed and upon reaching this second test point state, recovery procedures should be invoked.; Testing for incomplete cycles utilizes the same technique as described above except that the database processes themselves should be aborted or prematurely terminated.; Testing for the following conditions requires that a known database state be achieved. Several database fields, pointers, and keys should be corrupted manually and directly within the database (via database tools). Additional transactions should be executed using the tests from Application Function and Business Cycle Testing and full cycles executed.]   |
|Oracles                |  [Outline one or more strategies that can be used by the technique to accurately observe the outcomes of the test. The oracle combines elements of both the method by which the observation can be made and the characteristics of specific outcome that indicate probable success or failure. Ideally, oracles will be self-verifying, allowing automated tests to make an initial assessment of test pass or failure, however, be careful to mitigate the risks inherent in automated results determination.]  |
|Required Tools         |  [The technique requires the following tools:; base configuration imager and restorer; installation-monitoring tools (registry, hard disk, CPU, memory, and so on; backup and recovery tools]  |
|Success Criteria       |  [The technique supports the testing of:; One of more simulated disasters involving one or more combinations of the application, database, and system.; One or more simulated recoveries involving one or more combinations of the application, database, and system to a known desired state.  ] |
|Special Considerations |  [Recovery testing is highly intrusive. Procedures to disconnect cabling (simulating power or communication loss) may not be desirable or feasible. Alternative methods, such as diagnostic software tools may be required.; Resources from the Systems (or Computer Operations), Database, and Networking groups are required.; These tests should be run after hours or on an isolated machine.]  |

#### 5.2.11 Configuration Testing

[Configuration testing verifies the operation of the target-of-test on different software and hardware configurations. In most production environments, the particular hardware specifications for the client workstations, network connections, and database servers vary. Client workstations may have different software loaded (for example, applications, drivers, and so on) and, at any one time, many different combinations may be active using different resources.]

|                       | Description                                                         |
|-----------------------|---------------------------------------------------------------------|
|Technique Objective    |   [Exercise the target-of-test on the required hardware and software configurations to observe and log target behavior under different configurations and identify changes in configuration state.]  |
|Technique              |   [Use Function Test scripts.; Open and close various non-target-of-test related software, such as the Microsoft Excel and Word applications, either as part of the test or prior to the start of the test.; Execute selected transactions to simulate actors interacting with the target-of-test and the non-target-of-test software.; Repeat the above process, minimizing the available conventional memory on the client workstation.]  |
|Oracles                |   [Outline one or more strategies that can be used by the technique to accurately observe the outcomes of the test. The oracle combines elements of both the method by which the observation can be made and the characteristics of specific outcome that indicate probable success or failure. Ideally, oracles will be self-verifying, allowing automated tests to make an initial assessment of test pass or failure, however, be careful to mitigate the risks inherent in automated results determination.]  |
|Required Tools         |   [The technique requires the following tools:; base configuration imager and restorer; installation-monitoring tools (registry, hard disk, CPU, memory, and so on ] |
|Success Criteria       |   [The technique supports the testing of one or more combinations of the target test items running in expected, supported deployment environments.]  |
|Special Considerations |   [What non-target-of-test software is needed, is available, and is accessible on the desktop?; What applications are typically used?; What data are the applications running; for example, a large spreadsheet opened in Excel or a 100-page document in Word?; The entire systems' netware, network servers, databases, and so on, also need to be documented as part of this test.]  |

#### 5.2.12 Installation Testing

[Installation testing has two purposes. The first is to ensure that the software can be installed under different conditions (such as a new installation, an upgrade, and a complete or custom installation) under normal and abnormal conditions. Abnormal conditions include insufficient disk space, lack of privilege to create directories, and so on. The second purpose is to verify that, once installed, the software operates correctly. This usually means running a number of tests that were developed for Function Testing.]

|                       | Description                                                         |
|-----------------------|---------------------------------------------------------------------|
|Technique Objective    |   [Exercise the installation of the target-of-test onto each required hardware configuration under the following conditions to observe and log installation behavior and configuration state changes:; new installation: a new machine, never installed previously with Project Name; update: a machine previously installed Project Name, same version; update: a machine previously installed Project Name, older version]  |
|Technique              |   [Develop automated or manual scripts to validate the condition of the target machine.; new: never installed; same or older version already installed; Launch or perform installation..; Using a predetermined subset of Function Test scripts, run the transactions.]  |
|Oracles                |   [Outline one or more strategies that can be used by the technique to accurately observe the outcomes of the test. The oracle combines elements of both the method by which the observation can be made and the characteristics of specific outcome that indicate probable success or failure. Ideally, oracles will be self-verifying, allowing automated tests to make an initial assessment of test pass or failure, however, be careful to mitigate the risks inherent in automated results determination.]  |
|Required Tools         |   [The technique requires the following tools:; base configuration imager and restorer; installation-monitoring tools (registry, hard disk, CPU, memory, and so on ] |
|Success Criteria       |   [The technique supports the testing of the installation of the developed product in one or more installation configurations.]  |
|Special Considerations |   [What transactions should be selected to comprise a confidence test that application has been successfully installed and no major software components are missing?]  |

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
