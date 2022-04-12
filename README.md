# Do2Day
## Overview
Our project was to build a TODO application and so we came up with Do2Day, a TODO app with a React frontend, node.js backend and a MongoDB database to store the TODOs persistently. In truth though, anybody could probably create something similar with a few Youtube tutorials. The main focus of our project wasn’t in the application itself but in the crafting of it. Our mentors, Mihai and Panpan at IBM showed us how important laying the foundations is in order to build substantial pieces of software.

We tried as much as possible to get to grips with practices found in modern day software engineering teams, and we made lots of mistakes along the way, but ultimately we really got a feel for what it takes to be a great software engineer as opposed to a good programmer.

From using a microservice architecture, making comprehensive sprint plans and documenting our architectural decisions, to setting up code reviews, building, testing and deploying our application and performing static analysis on the codebase, our project has been a great learning experience for us all and has really given us a good foundation for future software engineering projects.

## The Architecture
Originally, we had began with a monlithic architecture for our application in which we used a single repository for encorporating the frontend, backend and database. After some feedback from our mentors, Mihai and Panpan, we opted to change this approach to a microservice architecture in which we separated the frontend and backend completely into separate repositories, and instead made them interact via an API.

<img src="./Images/architecture.png" width="35%" height="35%" style="display: block; margin: 0 auto"/>

## The Application
The application consists of a simple React frontend, which is unit tested using Jest, a simple node.js backend, which is unit tested using Mocha and a MongoDB database. All of these components are completely distinct and interact via well-defined APIs.

<img src="./Images/application.png" width="35%" height="35%" style="display: block; margin: 0 auto"/>


## The CI/CD Pipeline
We built both the frontend and backend into container images, unit tested theme using Jest and Mocha respectively, pushed the container images to a container registry (Quay.io), deployed these container images to a Kubernetes cluster on OpenShift, and performed a variety of static analysis against the codebase.

It's fair to say, this is where the bulk of project was focused, and using GitHub Actions made this quite straightforward, enabling us to use custom actions and write our own workflows to suit our needs. We could define our workflow triggers on pull requests, pushes and a variety of other triggers and enabled the entire process to be sped up once properly configures.

<img src="./Images/deployment.png" width="35%" height="35%" style="display: block; margin: 0 auto"/>

<img src="./Images/workflows.png" width="35%" height="35%" style="display: block; margin: 0 auto"/>

<img src="./Images/codereview.png" width="35%" height="35%" style="display: block; margin: 0 auto"/>

## Architectural Decisions
Below are the architectural decisions we encountered over the course of the project, the solutions we
considered and the ultimate decision we made to solve the issue. These architectural decisions have
been created using the architecture decision description template published in
["Architecture Decisions: Demystifying Architecture" by Jeff Tyree and Art Akerman, Capital One Financial](https://www.utdallas.edu/~chung/SA/zz-Impreso-architecture_decisions-tyree-05.pdf). These templates are
active documents are will be updated as and when architectural decisions are made or changed over the
course of the project.

### Project Management
#### Version Control
|                             |                                                                             |
| --------------------------- | --------------------------------------------------------------------------- |
| **Issue:**         		  |	The project requires collaboration and constant development of an application, and therefore it must be possible to easily make and revert changes in the codebase. |
| **Decision:**       		  |	Use a version control system, namely Git, to track changes and versions of the codebase to enable backtracking. |
| **Status:**         		  | Decided |
| **Group:**          		  | Project Management |
| **Assumptions:**            | <ul><li>We cannot guarantee asynchronous development amongst the team</li></ul> |
| **Constraints:**            | None |
| **Positions:**              | <ul><li>Using SVN version control</li><ul> |
| **Argument:**               | Git version control is distributed, meaning that we can each have a local copy of the repository, make changes and commits and then push to the remote repository when we have a connection. This enables work to be done even when offline. In contrast, SVN is centralised, meaning commits cannot be made locally and require a connection. |
| **Implications:**           | The team will need to download Git onto their local machine to enable the creation and cloning of repositories. |
| **Related Decisions:**      | None |
| **Related Requirements:**   | None |
| **Related Artifacts:**      | None |
| **Related Principles:**     | None |
| **Notes:**                  | <ul><li>All of the team has some minor experience with SVN from 1st year programming module</li><li>Those who have experienced Git have found it much more user friendly and easy-to-use</li><li>Git is the most popular version control system and would be useful to have knowledge of going forward</li></ul> |

#### Backlog and Sprint Management
|                             |                                                                             |
| --------------------------- | --------------------------------------------------------------------------- |
| **Issue:**         		  |	The project requires a well-defined backlog to be maintained to ensure each team member is clear on what has been done, is being done and needs to be done at every stage. |
| **Decision:**       		  |	Use a Kanban board, namely GitHub Project Boards, to define the project backlog, assign tasks, and monitor the progress of the project. |
| **Status:**         		  | Decided |
| **Group:**          		  | Project Management |
| **Assumptions:**            | <ul><li>Managing the project backlog through scrum meetings alone is not viable</li></ul> |
| **Constraints:**            | None |
| **Positions:**              | <ul><li>Using Trello</li><ul> |
| **Argument:**               | As we will be using GitHub, using GitHub Project Boards offers a seamless integration of the kanban board with the remote repository. Using a separate kanban board tool such as Trello would have required someone to maintain the board regularly as opposed to having the board update dynamically as tasks are completed within the repository. |
| **Implications:**           | The team will need to learn how to make use of the Project Boards feature by creating cards, assigning them and updating their progress. |
| **Related Decisions:**      | None |
| **Related Requirements:**   | None |
| **Related Artifacts:**      | None |
| **Related Principles:**     | None |
| **Notes:**                  | <ul><li>Some of the team has used Trello before, however GitHub Project Boards offers a more transparent kanban board feature and is integrated in the GitHub ecosystem</li></ul> |

### CI/CD Pipeline
#### Workflow Automation
|                             |                                                                             |
| --------------------------- | --------------------------------------------------------------------------- |
| **Issue:**         		  |	The project requires the automation of software development workflows, namely automating the integration and deployment of the application. |
| **Decision:**       		  |	Use a platform, namely GitHub Actions, that enables the automation of the build, test and deployment pipeline |
| **Status:**         		  | Decided |
| **Group:**          		  | CI/CD Pipeline |
| **Assumptions:**            | None |
| **Constraints:**            | None |
| **Positions:**              | <ul><li>Using Jenkins</li></ul> |
| **Argument:**               | As we will be using GitHub, GitHub Actions offers an integrated platform with the GitHub ecosystem. The learning curve for GitHub Actions also seems smaller than that of Jenkins which is key in the short time of the project. |
| **Implications:**           | The team will need to become familiar with creating workflows using GitHub Actions and customising them to the project requirements. |
| **Related Decisions:**      | None |
| **Related Requirements:**   | None |
| **Related Artifacts:**      | None |
| **Related Principles:**     | None |
| **Notes:**                  | <ul><li>Very little knowledge of automation tools such as GitHub Actions or Jenkins amongst the team</li><li>Learning curve of GitHub actions seems relatively smaller than that of Jenkins</li></ul> |

#### Static Analysis
|                             |                                                                             |
| --------------------------- | --------------------------------------------------------------------------- |
| **Issue:**         		  |	 |
| **Decision:**       		  |	 |
| **Status:**         		  | Pending |
| **Group:**          		  | CI/CD Pipeline |
| **Assumptions:**            | <ul><li>The quality and security of code cannot be left solely to developers</li></ul> |
| **Constraints:**            | None |
| **Positions:**              | <ul><li>Using Sonarqube</li><li>Using pre-commit</li><li>Using synk</li></ul> |
| **Argument:**               |  |
| **Implications:**           |  |
| **Related Decisions:**      | None |
| **Related Requirements:**   | None |
| **Related Artifacts:**      | None |
| **Related Principles:**     | None |
| **Notes:**                  | <ul><li></li></ul> |

### Frontend
|                             |                                                                             |
| --------------------------- | --------------------------------------------------------------------------- |
| **Issue:**         		  |	The project will require a frontend UI for the application that is both functional and visually appealing. |
| **Decision:**       		  |	Use JavaScript and moreover use the React library to develop the application frontend |
| **Status:**         		  | Decided |
| **Group:**          		  | Frontend |
| **Assumptions:**            | None |
| **Constraints:**            | None |
| **Positions:**              | <ul><li>Using vanillia JavaScript</li><li>Using Vue.js</li></ul> |
| **Argument:**               | Using React removes many of the complexities of working vanilla JavaScript and greatly simplifies the development of the application. React is also more catered toward cross-platform as opposed to Vue.js and while this application will not be cross-platform for this project, given the nature of the application, it may be something to consider for future development. |
| **Implications:**           | The frontend team will need to familiarise itself with React and JavaScript in general. |
| **Related Decisions:**      | <ul><li>Choice of unit testing framework</li></ul> |
| **Related Requirements:**   | None |
| **Related Artifacts:**      | None |
| **Related Principles:**     | None |
| **Notes:**                  | <ul><li></li></ul> |

### Backend
#### Backend Framework
|                             |                                                                             |
| --------------------------- | --------------------------------------------------------------------------- |
| **Issue:**         		  |	The project require a backend framework to build the application |
| **Decision:**       		  |	Use Node.js |
| **Status:**         		  | Decided |
| **Group:**          		  | Backend |
| **Assumptions:**            | None |
| **Constraints:**            | None |
| **Positions:**              | <ul><li>Use Java</li></ul> |
| **Argument:**               | Using Node.js integrates well with our frontend React application and also makes integration with a database relatively straightforward. |
| **Implications:**           | The backend team will have to learn Node.js |
| **Related Decisions:**      | <ul><li>Choice of frontend</li><li>Choice of unit testing framework</li><li>Choice of database</li></ul> |
| **Related Requirements:**   | None |
| **Related Artifacts:**      | None |
| **Related Principles:**     | None |
| **Notes:**                  | <ul><li>The team has extensive knowledge of Java from college already</li><li>Using JavaScript and Node.js might be best for both learning and also for the purposes of the application</li><li>The JavaScript syntax is relatively similar to that of Java and so should be relatively familiar</li></ul> |

#### Unit Testing Framework
|                             |                                                                             |
| --------------------------- | --------------------------------------------------------------------------- |
| **Issue:**         		  |	The project will be completed over a number of months and as such it is essential that all additions can be verified to work as intended to prevent any unnecessary blockages. |
| **Decision:**       		  |	Use a JavaScript unit testing framework, namely Jest, to write unit tests for new functions and features. |
| **Status:**         		  | Decided |
| **Group:**          		  | Backend |
| **Assumptions:**            | <ul><li>Building a substantial application is not feasible if bugs cannot be easily found and rectified</li></ul> |
| **Constraints:**            | None |
| **Positions:**              | <ul><li>Using Mocha</li><li>Using Cypress</li><li>Using Webdriver</li></ul> |
| **Argument:**               | Jest was designed by Facebook developers to work with React and so it fits seamlessly with our React application. Jest is also relatively simple and requires no pre-configuration unlike Mocha. Jest is also specifically designed for unit testing as opposed to more comprehensive testing frameworks like Cypress and Webdriver which offer a variety of additional testing mechanisms which are not required for the purposes of this project. |
| **Implications:**           | The backend team will need to become familiar with the syntax and write Jest unit tests when developing new features and functions. |
| **Related Decisions:**      |  <ul><li>Choice of backend framework</li></ul> |
| **Related Requirements:**   | None |
| **Related Artifacts:**      | None |
| **Related Principles:**     | None |
| **Notes:**                  | <ul><li>The team all has some knowledge of unit testing and have all used JUnit to test Java applications</li><li>Using JavaScript itself is new to the majority of the team aso using a simple unit testing framework would be preferable</li><li>As we are using React, it seemed obvious to use Jest given how closely linked the two are</li></ul> |

#### Database
|                             |                                                                             |
| --------------------------- | --------------------------------------------------------------------------- |
| **Issue:**         		  |	The project requires that the application data be stored in a persistent database |
| **Decision:**       		  |	Use MongoDB to store and retrieve application data |
| **Status:**         		  | Pending |
| **Group:**          		  | Backend |
| **Assumptions:**            | <ul><li>The data must be easily accessible</li></ul> |
| **Constraints:**            | None |
| **Positions:**              | <ul><li>Using MySQL</li><li>Using SQLite</li><li>Using PostgreSQL</li></ul> |
| **Argument:**               |  |
| **Implications:**           | The backend team will need to become familiar with the MongoDB API for storage and retrieval of data, as well as configuring the database as required. |
| **Related Decisions:**      | None |
| **Related Requirements:**   | None |
| **Related Artifacts:**      | None |
| **Related Principles:**     | None |
| **Notes:**                  | <ul><li></li></ul> |

