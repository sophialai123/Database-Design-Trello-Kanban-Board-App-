# Database-Design-Trello-Kanban-Board-App-
Trello is a work management tool that allows you to organise your work in boards and lists. It has many features such as comments, adding files, labels, and moving cards between columns.

#### Design app: **lucid.app**
- [Database design link]((https://lucid.app/lucidchart/63b4da6d-1315-4f2a-8085-49d7ce76c221/edit?beaconFlowId=2ACA09CD33B64859&page=0_0&invitationId=inv_d2070272-2755-43b8-b6db-05b659ff1329#))

### Database requirements
##### 1. A user can sign up to our application 
- create a table name called "site_user"
---

##### 2. A user can create one board or more boards ( a board can be either public or private)
- private board only the user who added can use
- public board is available for all the users
- create a table name called "board"
- the relation between "site_user" and "board" is **one to many**, one user can have many boards
---


##### 3. A board can have multiple columns and they can be removed, renamed and deleted.
- create a table called "board_list"
- the relation between "board" and "board_list" is **one to many**, one board can have many board_list(columns)
---


##### 4. A user can add cards to a board_list on a board 
- create a table called "card"
- the relation between "board_list" and "card" is **one to many**, one board_list can have many cards
---


##### 5. Comments can be added to cards by users who can access the board
- **Many to Many** relationship between "site_user" and "board" - many users can have many boards --ONLY for private board
- create a join table called "board_member"
- create a table called" comment"
- the relation between "card" and "comment" is **one to many**, one card can have many comments
- the relation between "site_user" and "comment" is **one to many**, one user can have many comments

---

##### 1. A user can sign up to our application 
---


##### 1. A user can sign up to our application 
---


##### 1. A user can sign up to our application 
---
##### 1. A user can sign up to our application 
---


##### 1. A user can sign up to our application 
---


##### 1. A user can sign up to our application 
---

