# Database-Design-Trello-Kanban-Board-App-
Trello is a work management tool that allows you to organise your work in boards and lists. It has many features such as comments, adding files, labels, and moving cards between columns.

#### Design app: **lucid.app**
- [Database design link](https://lucid.app/lucidchart/63b4da6d-1315-4f2a-8085-49d7ce76c221/edit?page=0_0&invitationId=inv_d2070272-2755-43b8-b6db-05b659ff1329#)
- [Youtube tutorial](https://www.youtube.com/watch?v=7Ck8wSoKJXI)
- [trello]https://trello.com/b/3Psoj9XS/first-board
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
- create a join table called "board_member" - many to many relationship
- create a table called" comment" 
- the relation between "card" and "comment" is **one to many**, one card can have many comments
- the relation between "site_user" and "comment" is **one to many**, one user can have many comments

---

##### 6. A checklist can be added to a card
- create a table called "checklist_item "
- the relation between "card" and "checklist_item" is **one to many**, one card can have many checklist items
---


##### 7. Users can be added as members to a card to see updates
- use can add other users or add themselves to a specific card
- **Many to Many** relationship between "site_user" and "card" - many users can have many cards 
- create a join table called "card_member" - many to many relationship
---


##### 8. Any activity on a card should be tracked 
- create a table called "card_activity " - store the history of the card
- the relation between "card" and "card_activity" is **one to many**, one card can have many card activities
- the relation between "site_user" and "card_activity" is **one to many**, one user can have many card activities

---
##### 9. A card can be archived so it is no longer visible on the board(UI)
- add a new column called "is_active" to "card" table to check if the card is archived or not 

---
##### 10. A user can add labels to a card, edit label names and colours, and create labels
- create a table called "core-label" default values -- not related to any tables 
- create a record for each board called "board_label"
- the relation between "board" and "board_label" is **one to many**, one board can have many board labels
- create a join table called "card_label"
- the relation between "board_label" and "card_label" is **many to many**, many cards can have many card labels

##### 11. A card can have a due date and a reminder date and time
- add new columns in to "card" table -called "due_date"(just date) and "reminder_date"( data and time)
---

##### 12. A user can attach files and pictures to a card 
- create a table called "card_attachement"
- the relation between "card" and "card_attachement" is **one to many**, one card can have many card attachments
---

