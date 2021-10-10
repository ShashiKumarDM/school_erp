# School Database Design

## Tables

1. Students
2. Teachers
3. Users
4. Standard
5. Section
6. Subjects
7. Fee_Details
8. Student_Fees_details
9. Payments
10. Notes
11. Live_Classes
12. Roles
13. Abilities
14. Role_Abilities


## Table Attributes and Relations

* ### Standard
    - **id** : number, primary key, auto increment.
    - **name** : string, unique.

* ### Section
    - **id** : number, primary key, auto increment.
    - **name** : string, unique.

* ### Standard_Sections
    - **id** : number, primary key, auto increment.
    - **standard_id** : number, references(standard)->id.
    - **section_id** : number, references(section)->id.

* ### Fee_Details
    - **id** : number, primary key, auto increment.
    - **standard_id** : number, references(standard)->id.
    - **amount** : number.

* ### Role
    - **id** : number, primary key, auto increment.
    - **name** : string, unique.

* ### Ability
    - **id** : number, primary key, auto increment.
    - **name** : string, unique.

* ### Role_Ability
    - **id** : number, primary key, auto increment.
    - **role_id** : number, references(role)->id.
    - **ability_id** : number, references(ability)->id.

* ### User
    - **id** : number, primary key, auto increment.
    - **user_name** : string, unique.
    - **password** : string.
    - **role_id** : number, references(role)->id.

* ### User_Abilitie
    - **id** : number, primary key, auto increment.
    - **user_id** : number, references(user)->id.
    - **ability_id** : number, references(ability)->id.
