# Do2Day
## Overview
Do2Day is a TODO application built using a CI/CD pipeline.

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
| **Notes:**                  | <ul><li>Some of the team has used Trello before, however GitHub Project Boards offers a more transparent kanban board feature and is integrated in the GitHub ecosystem</li></ul> |

#### Blank Architectural Decision Template
|                             |                                                                             |
| --------------------------- | --------------------------------------------------------------------------- |
| **Issue:**         		  |	 |
| **Decision:**       		  |	 |
| **Status:**         		  |  |
| **Group:**          		  |  |
| **Assumptions:**            | <ul><li></li></ul> |
| **Constraints:**            |  |
| **Positions:**              | <ul><li></li></ul> |
| **Argument:**               |  |
| **Implications:**           |  |
| **Related Decisions:**      |  |
| **Related Requirements:**   |  |
| **Related Artifacts:**      |  |
| **Notes:**                  | <ul><li></li></ul> |

