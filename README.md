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
|                             |                                                                             |
| --------------------------- | --------------------------------------------------------------------------- |
| **Issue:**         		  |	The project requires collaboration and constant development of an application, and therefore it must be possible to easily make and revert changes in the codebase. |
| **Decision:**       		  |	Use a version control system, namely Git, to track changes and versions of the codebase to enable backtracking. |
| **Status:**         		  | Decided |
| **Group:**          		  | Project Management |
| **Assumptions:**            | <ul><li>We cannot guarantee asynchronous development amongst the team</li></ul> |
| **Constraints:**            | None |
| **Positions:**              | Using SVN version control |
| **Argument:**               | Git version control is distributed, meaning that we can each have a local copy of the repository, make changes and commits and then push to the remote repository when we have a connection. This enables work to be done even when offline. In contrast, SVN is centralised, meaning commits cannot be made locally and require a connection. |
| **Implications:**           | The team will need to download Git onto their local machine to enable the creation and cloning of repositories. |
| **Related Decisions:**      | None |
| **Related Requirements:**   | None |
| **Related Artifacts:**      | None |
| **Notes:**                  | <ul><li>All of the team has some minor experience with SVN from 1st year programming module</li><li>Those who have experienced Git have found it much more user friendly and easy-to-use</li><li>Git is the most popular version control system and would be useful to have knowledge of going forward</li></ul>
 |


