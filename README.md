# NewtryDocumentation - Software Requirements Specification 

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
- [Supporting Information](#4-supporting-information)

## 1. Introduction

### 1.1 Purpose
This Software Requirements Specification (SRS) describes all specifications for the application "Newtry". It includes an overview about this project, its vision, detailed information about the planned features and boundary conditions of the development process.


### 1.2 Scope
The project is going to be realized as a React Native App.  
  
Actors of this App can be users or moderators.  
  
Planned Subsystems are: 
* Barcode scanning in App:  
The Barcode scanning is the essential part of the application. Scanning products leads to information about the product showing on the screen. These information consists of ingredients, nutritional values and a climate score.
* Community feature:  
Registerd users get the ability to rate and comment products. 
* Webiste:  
On the webiste anonymous and registered user are able to search products via search bar. Furthermore there are information about our team.

### 1.3 Definitions, Acronyms and Abbreviations
| Abbrevation | Explanation                            |
| ----------- | -------------------------------------- |
| SRS         | Software Requirements Specification    |
| UC          | Use Case                               |
| n/a         | not applicable                         |
| tbd         | to be determined                       |
| UCD         | overall Use Case Diagram               |
| FAQ         | Frequently asked Questions             |

### 1.4 References

| Title                                                              | Date       | Publishing organization   |
| -------------------------------------------------------------------|:----------:| ------------------------- |
| [Newtry Blog](https://newtry.ionae.de/?p=1)    | 19.10.2021 | Newtry Team    |
| [GitHub](https://github.com/TeamNewTry)              | 19.10.2021 | Newtry Team    |
| [YouTrack](https://dhbw-karlsruhe.myjetbrains.com/youtrack/projects/77651022-e156-4357-a251-e794beb94fa5) |19.10.2021| Newtry Team |
| [Cute Kittens](https://www.youtube.com/watch?v=dQw4w9WgXcQ) | 19.10.2021| Newtry Team |


### 1.5 Overview
The following chapter provides an overview of this project with vision and Overall Use Case Diagram. The third chapter (Requirements Specification) delivers more details about the specific requirements in terms of functionality, usability and design parameters. Finally there is a chapter with supporting information. 
    
## 2. Overall Description

### 2.1 Vision
Newtry helps you to check a product’s ingredients and nutritional values on the fly by simply scanning its barcode. This enables you to know every last detail of the food you’re eating in an easy and enjoyable way.
But it’s not only about you, it’s about all of us! Newtry will help you to check a product’s climate impact. This way you can contribute towards a better tomorrow just by taking your smartphone with you on a shopping spree! And just between us two – who doesn’t already have it at hand while shopping?
We want to enhance the feeling of unity even further by implementing a community feature in the future. This will add a function which will allow users to share their opinion on a product after buying it. Users will be able to see what other people like or dislike about their products. But for the scope of the Software Engineering class this project began seeing the light of the world, we’ll keep this feature as our special weapon a bit further down the line in the backlog.

### 2.2 Use Case Diagram

![OUCD]

### 2.3 Technology Stack
The technologies we use are:

Backend:
- Firebase

Frontend:
- React Native
- Redux and redux-saga
- Firebase SDK
- react-native-i18n

IDE:
- Visual Studio Code

Project Management:
- YouTrack
- GitHub
- Discord

Deployment:
- TODO

Testing:
- Jest

## 3. Specific Requirements

### 3.1 Functionality
This section will explain the different use cases you could see in the Use Case Diagram and their functionality.  
Until **December** we plan to implement:
- 3.1.1 Show ingredients
- 3.1.2 Show nutritional values
- 3.1.3 Scan barcode

Until **June** we want to implement:
- 3.1.4 Climate impact score
- 3.1.5 Registration & Login
- 3.1.6 Ratings
- 3.1.7 Comments

#### 3.1.1 Show ingredients
Ingredients give you an overview of what is actually inside of what you are buying. Therefore it is one of the fundamental features. The list of ingredients is expected to be as complete as possible and therefore *may* include ingredients that don't have to be listed on the product itself because of legal regulations.
Accessing the list of ingredients requires being able to find a specific product and access it's details. For this purpose a search bar which is able to find the product by its barcode number or product name has to be implemented. As both the search bar and ingredients task go hand in hand, the search bar is contained in this feature.

#### 3.1.2 Show nutritional values
This feature is closely related to the last one. Just as ingredients, the nutritional values of a product are fundamental when deciding on buying it. Nutrients listed here should not only be limited to what is shown on the product and thus *may* include additional nutritional values.

#### 3.1.3 Scan barcode
To ease the use of the app and make it more appealing to the user it should be possible to just scan the barcode of a product instead of having to use the search bar manually. All typical EAN/EAN-13 barcodes are expected to be supported.

#### 3.1.4 Climate impact score
Additional information about a product as the climate impact score should also be included. On which factors this score will depend may vary as different aspects get more or less important to the community. For that reason we don't specify a specific list of factors and are going to disclose more information in the app itself. This also leaves room to expand this feature in the future.

#### 3.1.5 Registration & Login
The app will provide a possibility to register, login and logout. This is necessary for creating a community. This also opens up ways to tailor the information you receive to your needs in the future.

#### 3.1.6 Ratings
To enhance the feeling of unity, products should be able to receive ratings. Therefore a user will be able to see what others think of this product in general very quickly.

#### 3.1.7 Comments
When rating products users should also be able to give reason why they rated the product this way. This gives more in-depth insight into the community's opinion.

### 3.2 Usability
The app's foundation is an easy-to-use, no-explanation-needed interface which people at all age are able to use with joy.
With that in mind we focus on two pillars:

#### 3.2.1 Simplicity
The goal is that the user is able to install the app and use it right away: No explanation needed
This requires careful structural design.

#### 3.2.2 Familiarity
Building an interface that feels familiar to the user is extremely important. This not only speeds up the time required to get used to the workflow of the app but aids the user in intuitively finding his way around the app.

### 3.3 Reliability

#### 3.3.1 Availability
These days an availability of 95% is standard. To achieve this a resilient system has to be built. Depending on the amount of users and their behavior, different scalability and elasticity techniques have to be used, such as load balancers and clustering.

#### 3.3.2 Defect Rate
As information about products (general and community-based) are the foundation of our app, data loss is intolerable and must be prevented at all cost.

### 3.4 Performance

#### 3.4.1 Capacity
The system should be able to manage thousands of requests per minute, most of them retrieving information as most of the users will most likely be using the app just to retrieve, not contribute information. Scalability and elasticity are key components here as well.

#### 3.4.2 Storage
As all data will be hosted on a centralized server/cluster this needs to be able to store this amount of information. Depending on how large the user base gets this ranges from a few megabytes to gigabytes. Again scalability and elasticity are key components here.

#### 3.4.3 App performance / Response time
While shopping users expect a flawlessly working app with low response times. Therefore content should be distributed globally via according edge servers near the end user. This guarantees low response times. The app has to be implemented efficiently as well to prevent freezes and minimize loading times.

### 3.5 Supportability

#### 3.5.1 Coding Standards
A clean code base speeds up the development process of any project dramatically. Using modern techniques ensures general reliability, maximum readability and an easy & quickly expandable/adaptable code base. This requires standards to be enforced by every member of the team. Typical standards include:
- Git conventions (commit messages, branch naming, overall workflow)
- Architectural conventions (MVC, MVVM...)
- Language conventions (naming, formatting, architecture...)

#### 3.5.2 Testing Strategy
Full test coverage prevents bugs from sneaking into the app in the first place, but also from reoccuring. This again drastically speeds up the overall development process, but requires strict enforcement of every member of the team. Keyphrase here is test driven development (TDD).

### 3.6 Design Constraints
The modern and easy to use approach of the app is resembled in the UI just as in the app architecture. Therefore we will separate the different functionalities to follow a more modular development approach. This allows for more parallelization and working on a more narrow scope.

Because we are programming an app that's inteded to be used on all mobile devices we chose React Native and therefore JavaScript. As React is only responsible for the "view" part, we'll be using Redux for state & data management. Redux on the other hand will be working with the Firebase SDK to access and manage the actual data in the backend.
The supported Platforms will be based on the [minimum requirements of React](https://github.com/facebook/react-native#-requirements):
- Android 5.0
- iOS 11.0

### 3.7 Online User Documentation and Help System Requirements
The app usage will focus on intuitive and simple design. No further documentation will be required. For further assistance contact data will be provided.

### 3.8 Purchased Components
For now the app will be completely free to use. This may change in the future.

### 3.9 Interfaces

#### 3.9.1 User Interfaces
The User interfaces that will be implented are:
- Dashboard - lists all session and makes it possible to filter sessions
- Session Page - shows detailed information about the session and makes it possible to connect session attendants for example via messaging system
- Login - this page is used to log in 
- Register - provides a registration form
- Overwiew of personal sessions - shows all the sessions a user participates in
- Friend List - friends can be added
- Profile - makes it possible to post information about yourself, might provide messaging feature, also shows additional information about users (for example: Language, country, favorite games, etc.)
- Settings - shows the settings

#### 3.9.2 Hardware Interfaces
(n/a)

#### 3.9.3 Software Interfaces
The app will be runnable on Android 4.4 and higher. iOS won't be featured at the moment.

#### 3.9.4 Communication Interfaces
The server and hardware will communicate using the http protocol. 

### 3.10 Legal, Copyright, and Other Notices
Copyright (c) 2021 Newtry
This project and related files (such as logos and code in other repos) can not be copied and/or distributed without the express permission of Newtry.
We do not take responsibilty for any incorrect data or errors in the application.

## 4. Supporting Information
For any further information you can contact the Newtry Team or check our [NewtryBlog](https://newtry.ionae.de/). 
The Team Members are:
- Jona Kuhn
- Oliver Schirmer
- Jakob Braun
- Norman Reimer

<!-- Picture-Link definitions: -->
[OUCD]: ./resources/Overall_Use_Case_Diagram.drawio.png "Overall Use Case Diagram"
