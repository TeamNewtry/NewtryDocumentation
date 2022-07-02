# Newtry - Software Architecture Document

- [Newtry - Software Architecture Document](#Newtry---software-architecture-document)
  - [1. Introduction](#1-introduction)
    - [1.1 Purpose](#11-purpose)
    - [1.2 Scope](#12-scope)
    - [1.3 Definitions, Acronyms and Abbreviations](#13-definitions-acronyms-and-abbreviations)
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

This document provides an overview of our software architecture. With several architectural views, it depicts different aspects of the system. It is intended to capture and convey the significant architectural decisions which have been made for the system.

### 1.2 Scope

This document describes the architecture of the Newtry project.

### 1.3 Definitions, Acronyms and Abbreviations

| Abbrevation | Explanation                                      |
| ----------- | ------------------------------------------------ |
| API         | Application Programming Interface                |
| APK         | Android Package Kit 	                           |
| MVC         | Model View Controller                            |
| n/a         | not applicable                                   |
| SRS         | Software Requirements Specification              |
| UC          | Use Case                                         |
| UCD         | Use Case Diagram                                 |
| UI          | User Interface                                   |

### 1.4 References

| Title                                                                                                                                                   | Date       | Publishing organization |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ----------------------- |
| [Blog](https://newtry.ionae.de/)                                                                                                                        | 06.12.2021 |  Newtry                 |
| [GitHub](https://github.com/TeamNewtry)                                                                                                                 | 06.12.2021 |  Newtry                 |
| [UC searchbar](https://github.com/TeamNewtry/NewtryDocumentation/blob/main/use_cases/UC1_Searchbar.md)                                                  | 06.12.2021 |  Newtry                 |
| [UC show ingredients](https://github.com/TeamNewtry/NewtryDocumentation/blob/main/use_cases/UC2_Ingredients.md)                                         | 06.12.2021 |  Newtry                 |
| [UC show nutritional values](https://github.com/TeamNewtry/NewtryDocumentation/blob/main/use_cases/UC3_Nutrition.md)                                    | 06.12.2021 |  Newtry                 |
| [UC scan barcode](https://github.com/TeamNewtry/NewtryDocumentation/blob/main/use_cases/UC4_Scanner.md)                                                 | 06.12.2021 |  Newtry                 |
| [Flux](https://github.com/facebook/flux)                                                                                                                | 06.12.2021 |  Facebook               |
| [React Native](https://reactnative.dev/)                                                                                                                | 06.12.2021 |  Facebook               |
| [Firebase](https://firebase.google.com/?gclid=CjwKCAiAhreNBhAYEiwAFGGKPE-SiiK9_HLwhicpHbivI4lqpKCmBZorTRwvp3Sm37jP4ZmqNTbdRhoC0ScQAvD_BwE&gclsrc=aw.ds) | 06.12.2021 |  Google                 |

### 1.5 Overview

This document contains the architectural representation, goals and constraints as well as the logical, deployment, implementation and data views.

## 2. Architectural Representation

This project uses the Flux architecture for backend and frontend. Flux is an architecture designed by Facebook for creating SPAs. In some ways, it is an adaptation to the MVC architecture.
As shown in the picture below, it consists of 4 major parts, which are connected in a cyclic manner.

1. **View**:
   The View contains everything the user actually sees, so it resembles the UI. The purpose of the View is to listen to changes from the Stores and to re-render themselves if needed. In our case this component is realized by React Native.

2. **Action Creator**:
   The Action Creator, as the name suggests, is responsible for creating actions. An action is an object with a type property and data. An example for an action could be entering a product in the searchbar.

3. **Dispatcher**:
   The Dispatcher is responsible for processing registered actions and callbacks. It acts as sort of a router for delivering actions to the Stores.

4. **Store**:
   The Stores contain the application's state and logic. It's somewhat comparable to the model part of the MVC architecture, although it resembles a domain rather than a single object and contains logic for updating the View. 

5. **Web API Utils (Separate from Flux)**:
   The Web API Utils are an interface for accessing the backend. In our case, it resembles a simple cloud functions wrapper.

![Flux architecture](https://miro.medium.com/max/700/0*mM7vdDIBZehgir2Z. "Flux architecture")

## 3. Architectural Goals and Constraints

Our architecture's goal is to be as flexible as possible. One aspect which facilitates achieving this goal, is a clear separation into front- and backend with some "glue" in-between.
In our case, the tech stack removes a lot of the work you would usually have to put into architecturing. Our frontend framework React Native eases building well-designed and scalable applications across multiple platforms with a single codebase.
Firebase on the other hand, takes care of many tedious backend tasks. It already includes tools like authentication management, databases and cloud functions, which completely eradicate thoughts about deploying the backend by offering "serverless" deployment. It also features widespread community support and SDKs for integrating it into almost every well-known framework.
![Firebase architecture](https://d2908q01vomqb2.cloudfront.net/cb4e5208b4cd87268b208e49452ed6e89a68e0b8/2021/04/29/How-to-migrate-from-firebase-to-amplify-1.png "Firebase architecture")
The picture above shows an exemplary Firebase architecture. In our case, the mobile clients are the smartphones running our React Native application. All the other features are already implemented by Firebase. Most of them require only a little configuration effort and a few lines of code to integrate them into your application.

## 4. Use-Case View

Below, you can see our UCD.

![Use case diagram](https://raw.githubusercontent.com/TeamNewtry/NewtryDocumentation/main/resources/Overall_Use_Case_Diagram.drawio.svg)

### 4.1 Use-Case Realizations

All the features of the first semester's scope are realized as different views in our React Native app, despite the nutritional values & ingredients being different sections in the same view. The communication with the backend is very minimal as the scope for the first semester only includes searching for and showing information about products.
The second semester on the other hand is responsible for implementing the rating and comment feature, climate rating, as well as authentication. The first of which are contained in the product's detail page and the latter being implementable in the settings view. 
For further information about how each use case is defined, please refer to our [SRS](https://github.com/TeamNewtry/NewtryDocumentation/blob/main/README.md).

## 5. Logical View

![Architecture](https://raw.githubusercontent.com/TeamNewtry/NewtryDocumentation/main/resources/Class_Diagram_Architecture.drawio.svg "Architecture")
The picture above represents our implementation of the Flux architecture described in [Architectural Representation](#2-architectural-representation).
State, Dispatcher as well as UI haven't been filled with further details, as these are realized by React Native.

## 6. Process View

n/a

## 7. Deployment View

![Deployment](https://raw.githubusercontent.com/TeamNewtry/NewtryDocumentation/main/resources/Deployment.drawio.svg "Deployment")

As you can see in the picture above, deploying a React Native app is quite easy. The first step is the same for Android as well as iOS: let React Native create a bundle for the respective platform. Afterwards, the applications can be built the typical Android/iOS way. For Android you would build an APK with Gradle (for a release variant you'd create a signing key and configure Gradle accordingly beforehand). For iOS you'd most likely be using XCode's in-built UI features. All of the previously mentioned steps can be accomplished by a simple command (besides building the final IPA for iOS).

## 8. Implementation View

n/a

## 9. Data View

Our scope for the first semester only requires a very simple database 
structure, which consists of a _product's ID and name_ in order to be able to 
search for a product. The information which is related to a product will be 
directly fetched from [Open Food Facts](https://world.openfoodfacts.org/) to 
ensure most recent information. As information on their platform is stored 
in a NoSQL-database, it's impossible to offer a relational database scheme 
uniform for each product. Besides that, they offer a [specification](https://wiki.openfoodfacts.org/API_Fields) for most of the fields found in 
a product's API data. Our scope for the second semester requires some 
additional data about the products, i.e. the ratings and comments.
These will be _linked to the product via the product ID and contain the integer value of the rating, as well as the comment_.

With this approach, we can dynamically join information from both sources (database and live data from Open Food Facts),
are able to reduce redundancy and maximize consistency.

## 10. Size and Performance

The debug-build APK has a size of 74.2MB. This can be reduced by approximately 10% by creating a release build. Furthermore, by creating an app bundle for release in the Google Play Store, the size may be reduced further significantly.
The performance of the app hasn't been measured precisely, but using the app feels very smooth, even on low-end devices.

## 11. Quality

To control the quality of our application, we use DeepScan and Codacy to create some metrics on issues, code smells and complexity. Our dashboard for Deepscan can be found [here](https://deepscan.io/dashboard/#view=project&tid=17820&pid=21155&bid=599182&prid=&subview=overview) and for Codacy [here](https://app.codacy.com/gh/TeamNewtry/Newtry/dashboard). For more information on our metrics, see [this](https://newtry.ionae.de/?p=344) blogpost. We have also used the HOC design pattern and FLUX architecture to further improve our code quality.
