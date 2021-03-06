# Newtry - Software Requirements Specification 

## Table of contents
- [Introduction](#1-introduction)
    - [Purpose](#11-purpose)
    - [Scope](#12-scope)
    - [Definitions, Acronyms and Abbreviations](#13-definitions-acronyms-and-abbreviations)
    - [References](#14-references)
    - [Overview](#15-overview)
- [Overall Description](#2-overall-description)
    - [Vision](#21-vision)
    - [Use Case Diagram](#22-use-case-diagram)
	- [Technology Stack](#23-technology-stack)
- [Specific Requirements](#3-specific-requirements)
    - [Functionality](#31-functionality)
    - [Usability](#32-usability)
    - [Reliability](#33-reliability)
    - [Performance](#34-performance)
    - [Supportability](#35-supportability)
    - [Design Constraints](#36-design-constraints)
    - [Online User Documentation and Help System Requirements](#37-online-user-documentation-and-help-system-requirements)
    - [Purchased Components](#38-purchased-components)
    - [Interfaces](#39-interfaces)
    - [Legal, Copyright And Other Notices](#310-legal-copyright-and-other-notices)
- [Implementation](#4-implementation)
    - [Class Diagram](#41-class-diagram) 
- [Supporting Information](#5-supporting-information)

## 1. Introduction

### 1.1 Purpose
This Software Requirements Specification (SRS) describes all specifications for the application "Newtry". It includes an overview about this project, its vision, detailed information about the planned features and boundary conditions of the development process.


### 1.2 Scope
The project is going to be realized as a React Native App.  
  
Actors of this app are registered or anonymous users.
  
Planned subsystems are: 
* In-App Barcode scanning:  
This feature is the essential part of the application. Scanning products leads to information about the product being shown on the screen. This information consists of ingredients, nutritional values and a climate score.
* Community feature:  
Registered users get the ability to rate and comment on products. 
* Website:  
On the website, anonymous and registered users are able to search for products via a search bar. Furthermore, there is information about the team behind Newtry.

### 1.3 Definitions, Acronyms and Abbreviations
| Abbrevation | Explanation                            |
| ----------- | -------------------------------------- |
| SRS         | Software Requirements Specification    |
| UC          | Use Case                               |
| n/a         | not applicable                         |
| tbd         | to be determined                       |
| UCD         | Use Case Diagram                       |
| FAQ         | Frequently asked Questions             |

### 1.4 References

| Title                                                                                                     | Date       | Publishing organization   |
| ----------------------------------------------------------------------------------------------------------|:----------:| ------------------------- |
| [Newtry Blog](https://newtry.ionae.de/?p=1)                                                               | 19.10.2021 | Newtry Team               |
| [GitHub](https://github.com/TeamNewTry)                                                                   | 19.10.2021 | Newtry Team               |
| [YouTrack](https://dhbw-karlsruhe.myjetbrains.com/youtrack/projects/77651022-e156-4357-a251-e794beb94fa5) | 19.10.2021 | Newtry Team               |
| [Cute Kittens](https://www.youtube.com/watch?v=dQw4w9WgXcQ)                                               | 19.10.2021 | Newtry Team               |


### 1.5 Overview
The following chapter provides an overview of this project, i.e. the vision and the Overall UCD. The third chapter (Requirements Specification) provides more details about the specific requirements in terms of functionality, usability and design parameters. Finally, there is a chapter with supporting information. 
    
## 2. Overall Description

### 2.1 Vision
Newtry helps you to check a product???s ingredients and nutritional values on-the-fly simply by scanning its barcode. This enables you to know every last detail of the food you???re eating in a convenient and enjoyable way.
But it???s not only about you, it???s about all of us! Newtry will help you to check a product???s climate impact. This way, you can contribute towards a better tomorrow just by taking your smartphone with you on a shopping spree! And just between the two of us ??? who doesn???t have it at hand while shopping, already?
We want to enhance the feeling of unity even further by implementing a community feature. This will allow users to share their opinion on a product after buying it. Users will be able to see what other people like or dislike about their products.

### 2.2 Use Case Diagram
![OUCD]

### 2.3 Technology Stack
The technologies used are:

Backend:
- Firebase
  - Authentication
  - Firestore Database
  - Functions

Frontend:
- React Native
- Firebase SDK

IDE:
- WebStorm
- Visual Studio Code

Project Management:
- YouTrack
- GitHub
- Discord

Deployment:
- GitHub Actions
- Codacy (used for metrics and automatic code analysis)
- DeepScan (used for metrics and automatic code analysis)

Testing:
- Jest

## 3. Specific Requirements

### 3.1 Functionality
This section explains the different use cases you could see in the UCD with their respective functionality.  
Until **December** we plan to implement:
- [Search products by search bar](../use_cases/UC1_Searchbar.md)
- [Show ingredients](../use_cases/UC2_Ingredients.md)
- [Show nutritional values](../use_cases/UC3_Nutrition.md)
- [Scan barcode](../use_cases/UC4_Scanner.md)

Until **June** we want to implement:
- 3.1.1 Show climate impact score
- 3.1.2 Registration & Login
- 3.1.3 Submit & show ratings
- 3.1.4 Write & show comments

#### 3.1.1 Show climate impact score
Additional information about a product, such as the climate impact score, should also be included when viewing a product's detail page. On which factors this score will depend may vary, as different aspects get more or less important to the community. For that reason, we can't specify a precise list of factors and are going to disclose more information in the app itself. This also enables us to expand this feature in the future.

#### 3.1.2 Registration & Login
The app will provide a possibility to register, login and logout. This is necessary for creating a thriving community (i.e. with less spam and bots). This also opens up ways to tailor the information you receive specifically to your needs.

#### 3.1.3 Submit & show ratings
To enhance the feeling of unity, products should be able to receive ratings. Therefore, a user will be able to see what others think of this product in general very quickly.

#### 3.1.4 Write & show comments
When rating products, users should also be able to give reason why they rated the product this way. This gives more in-depth insight into the community's opinion.

### 3.2 Usability
The app's foundation is an easy-to-use, no-explanation-needed interface which people at all age are able to use with joy.
With that in mind we focus on two pillars:

#### 3.2.1 Simplicity
The goal is that the user is able to install the app and use it right away: No explanation needed
This requires careful structural design.

#### 3.2.2 Familiarity
Building an interface that feels familiar to the user is extremely important. This not only speeds up the time required to get used to the workflow of the app, but aids the user at intuitively finding his way around the app.

### 3.3 Reliability

#### 3.3.1 Availability
These days an availability of 95% is expected by default. To achieve this, a resilient system has to be built. Depending on the amount of users and their behavior, different scalability and elasticity techniques have to be used, such as load balancers and clustering. Most of this will automatically be covered by Firebase.

#### 3.3.2 Defect Rate
As information about products (general and community-based) are the foundation of our app, data loss is intolerable and must be prevented at all cost.

### 3.4 Performance

#### 3.4.1 Capacity
The system should be able to manage thousands of requests per minute, most of them retrieving information, as most of the users will likely be using the app just to retrieve, not contribute information. Scalability and elasticity are key components here as well.

#### 3.4.2 Storage
As all data will be hosted on a centralized server/cluster, it needs to be able to store this amount of information. Depending on how large the userbase gets, the amount of data ranges from a few megabytes to gigabytes. Again, scalability and elasticity are key components here.

#### 3.4.3 App performance / Response time
While shopping, users expect a flawlessly working app with low response times. Therefore, content should be distributed globally via according edge servers near the end user. This guarantees low response times. The app has to be implemented efficiently as well to prevent freezes and minimize loading times.

### 3.5 Supportability

#### 3.5.1 Coding Standards
A clean code base drastically speeds up the development process of any project. Using modern techniques ensures general reliability, maximum readability and an easy & quickly expandable/adaptable codebase. This requires standards to be enforced by every member of the team. Typical standards include:
- Git conventions (commit messages, branch naming, overall workflow)
- Architectural conventions (MVC, MVVM...)
- Language conventions (naming, formatting, architecture...)

#### 3.5.2 Testing Strategy
Full test coverage prevents bugs from sneaking into the app in the first place, but also from reoccuring. This again drastically speeds up the overall development process, but requires strict enforcement of every member of the team. Keyphrase here is test driven development (TDD).

### 3.6 Design Constraints
The modern and easy-to-use approach of the app is resembled in the UI just as in the app architecture. Therefore, we will separate the different functionalities to follow a more modular development approach. This allows for more parallelization and working on a more narrow scope.

Because we are programming an app that's intended to be used on all mobile devices, we chose React Native and therefore JavaScript. React Native is not only responsible for the "view" part, as of version 0.58, state handling has become very handy using functional components. This will work hand-in-hand with the Firebase SDK to access and manage the actual data in the backend.
The supported platforms will be based on the [minimum requirements of React Native](https://github.com/facebook/react-native#-requirements):
- Android 5.0
- iOS 11.0

### 3.7 Online User Documentation and Help System Requirements
The app usage will focus on intuitive and simple design. No further documentation will be required. For further assistance, contact data will be provided.

### 3.8 Purchased Components
For now, the app will be completely free to use. This may change in the future.

### 3.9 Interfaces

#### 3.9.1 User Interfaces
The user interface is an intuitive mobile application with four screens:
- **Homescreen** with welcome text and search bar.
- **Scanner view** with camera view
- **Settings** with login option and language settings
- **Product page** with all information about a product

#### 3.9.2 Hardware Interfaces
No special hardware is required. All that is needed is a smartphone, which should have a working camera and an Internet connection.

#### 3.9.3 Software Interfaces
The app will be runnable on Android 5 and higher. iOS won't be featured at the moment.

#### 3.9.4 Communication Interfaces
The server and hardware will communicate using HTTPS. 

### 3.10 Legal, Copyright, and Other Notices
Copyright (c) 2021 Newtry
This project and related files (such as logos and code in other repos) can not be copied and/or distributed without the express permission of Newtry.
We do not take responsibilty for any incorrect data or errors in the application.

## 4. Implementation

### 4.1 Class Diagram
![CD]

## 5. Supporting Information
For any further information you can contact the Newtry Team or check our [NewtryBlog](https://newtry.ionae.de/). 
The Team Members are:
- Jona Kuhn
- Oliver Schirmer
- Jakob Braun
- Norman Reimer

<!-- Picture-Link definitions: -->
[OUCD]: ../resources/Overall_Use_Case_Diagram.drawio.svg "Overall Use Case Diagram"
[CD]: ../resources/Class_Diagram.drawio.svg "Class Diagram"
