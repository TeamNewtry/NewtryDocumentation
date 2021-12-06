# Newtry - Software Architecture Document

- [Newtry - Software Architecture Document](#Newtry---software-architecture-document)
  - [1. Introduction](#1-introduction)
    - [1.1 Purpose](#11-purpose)
    - [1.2 Scope](#12-scope)
    - [1.3 Definitions, Acronyms and Abbreviations](#13-definitions--acronyms-and-abbreviations)
    - [1.4 References](#14-references)
    - [1.5 Overview](#15-overview)
  - [2. Architectural Representation](#2-architectural-representation)
  - [3. Architectural Goals and Constraints](#3-architectural-goals-and-constraints)
  - [4. Use-Case View](#4-use-case-view)
    - [4.1 Use-Case Realizations](#41-use-case-realizations)
  - [5. Logical View](#5-logical-view)
  - [6. Process View](#6-process-view)
  - [7. Deployment View](#7-deployment-view)
  - [8. Implementation View](#8-implementation-view)
  - [9. Data View](#9-data-view)
  - [10. Size and Performance](#10-size-and-performance)
  - [11. Quality](#11-quality)

## 1. Introduction

### 1.1 Purpose

This document provides an overview of our software architecture. With several architectural views it depicts different aspects of the system. It is intended to capture and convey the significant architectural decisions which have been made for the system.

### 1.2 Scope

This document describes the architecture of the PiXS project.

### 1.3 Definitions, Acronyms and Abbreviations

| Abbrevation | Explanation                                      |
| ----------- | ------------------------------------------------ |
| SRS         | Software Requirements Specification              |
| MVC         | Model View Controller                            |
| FLUX        | extended MVC software architecture from Facebook |
| UC          | Use Case                                         |
| n/a         | not applicable                                   |
| UCD         | Use Case Diagram                                 |
| webapp      | Web Application                                  |
| API         | Application Programming Interface                |
| UI          | User Interface                                   |

### 1.4 References

| Title                                                                                                                                                   | Date       | Publishing organization |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ----------------------- | --- |
| [Blog](https://newtry.ionae.de/)                                                                                                                        | 06.12.2021 |  Newtry                 |
| [GitHub](hhttps://github.com/TeamNewtry)                                                                                                                | 06.12.2021 |  Newtry                 |
| [UC searchbar](https://github.com/TeamNewtry/NewtryDocumentation/blob/main/use_cases/UC1_Searchbar.md)                                                  | 06.12.2021 |  Newtry                 |
| [UC show ingredients](https://github.com/TeamNewtry/NewtryDocumentation/blob/main/use_cases/UC2_Ingredients.md)                                         | 06.12.2021 |  Newtry                 |
| [UC show nutritional values](https://github.com/TeamNewtry/NewtryDocumentation/blob/main/use_cases/UC3_Nutrition.md)                                    | 06.12.2021 |  Newtry                 |
| [UC scan barcode](https://github.com/TeamNewtry/NewtryDocumentation/blob/main/use_cases/UC4_Scanner.md)                                                 | 06.12.2021 |  Newtry                 |
| [FLUX](https://github.com/facebook/flux)                                                                                                                | 06.12.2021 |  Facebook               |     |
| [React Native](https://reactnative.dev/)                                                                                                                | 06.12.2021 |  Facebook               |
| [Firebase](https://firebase.google.com/?gclid=CjwKCAiAhreNBhAYEiwAFGGKPE-SiiK9_HLwhicpHbivI4lqpKCmBZorTRwvp3Sm37jP4ZmqNTbdRhoC0ScQAvD_BwE&gclsrc=aw.ds) | 06.12.2021 |  Google                 |

### 1.5 Overview

This document contains the architectural representation, goals and constraints as well as the logical, deployment, implementation and data views.

## 2. Architectural Representation

This project uses the FLUX architecture for backend and frontend. FLUX is an architecture designed by Facebook for creating SPAs. In some ways, it is an extension to the MVC architecture pattern.
As shown in the picture below, it consists of 5 major parts.

1. **Action Creator**:
   The action creater is responsible for creating actions (well obviously). An action is an object with property and data. An example for an action could be entering a product in the searchbar.

2. **Store**:
   The Store contains the application's state and logic. It's FLUX's equivalant to a common MVC's model.

3. **Dispatcher**:
   The dispatcher is responsible for processing registered actions and callbacks. It could be seen as the "heart" of the application,

4. **View**:
   The view contains everything the user sees, so it's basically the UI. The only job of the view is to listen to changes from the stores and to re-render themselves if needed. We're using React Native to help us build those views.

5. **Web API Utils**:
   The Web API Utils are basically just a cloud functions wrapper. The only job is to provide predefined backend functions. It is the interface to the backend.

![Flux architecture](https://miro.medium.com/max/700/0*mM7vdDIBZehgir2Z. "FLUX architecture")

## 3. Architectural Goals and Constraints

Our architecture's goal is to be as flexible as possible. One aspect which helps us reaching this goal is a clear seperation into front-and backend with some "glue" inbetween.
In our case or tech stack takes away a lot of the work you would usually have to put in into the architecture. Our frontend framework React Native helps us to build well designed and scalable applications. But the MVP for sure is Firebase. Firebase provides everything you need in order to communicate with your backend. It already includes things like authentication management and cloud functions which takes away a lot of effort you'd have to put into the backend.
![Firebase architecture](https://d2908q01vomqb2.cloudfront.net/cb4e5208b4cd87268b208e49452ed6e89a68e0b8/2021/04/29/How-to-migrate-from-firebase-to-amplify-1.png "Firebase architecture")
The picture above shows an exemplary firebase architecture. In our case the mobile clients are the smartphones running our React Native application. All the other features are alreay implemented by firebase. You just have to adjust them to your application and your good to go.

## 4. Use-Case View

Below, you can see our UCD.
![Use case diagram](https://raw.githubusercontent.com/TeamNewtry/NewtryDocumentation/main/resources/Overall_Use_Case_Diagram.drawio.svg)

### 4.1 Use-Case Realizations

All the features of the 1st semesters scope are realized as different views in our React Native app. The communication with the backend only has to be very minimal as the scope for the 1st semesters only includes showing information about a product.
For further information of how each use case is defined, please refer to our [SRS](https://github.com/TeamNewtry/NewtryDocumentation/blob/main/README.md).

## 5. Logical View

![Architecture](https://raw.githubusercontent.com/TeamNewtry/NewtryDocumentation/main/resources/Class_Diagram_Architecture.drawio.svg "Architecture")
The picture of above shows our implementation of the FLUX architecture descibed in [Architectural Representation](#2-architectural-representation).

## 6. Process View

n/a

## 7. Deployment View

todo

## 8. Implementation View

n/a

## 9. Data View

Our scope for the first semester only needs a very simple database structure which consists of ID and name in order to find a product. The information which is related to a product will looks similar to [Open food facts](https://wiki.openfoodfacts.org/API_Fields "Open food facts"). Our scope for the second semester needs some additional data about the users which is why will join the "user table" with our current table in the future.

## 10. Size and Performance

n/a

## 11. Quality

n/a
