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

* ### Subject
    - **id** : number, primary key, auto increment.
    - **name** : string, unique.
    - **desc** : string, unique.

* ### Standard_Sections
    - **id** : number, primary key, auto increment.
    - **standard_id** : number, references(standard)->id, not null.
    - **section_id** : number, references(section)->id, not null.

* ### Standard_Subject
    - **id** : number, primary key, auto increment.
    - **standard_id** : number, references(standard)->id, not null.
    - **subject_id** : number, references(subject)->id, not null.

* ### Fee_Details
    - **id** : number, primary key, auto increment.
    - **standard_id** : number, references(standard)->id, not null.
    - **amount** : number.

* ### Role
    - **id** : number, primary key, auto increment.
    - **name** : string, unique.

* ### Ability
    - **id** : number, primary key, auto increment.
    - **name** : string, unique.

* ### Role_Ability
    - **id** : number, primary key, auto increment.
    - **role_id** : number, references(role)->id, not null.
    - **ability_id** : number, references(ability)->id, not null.

* ### User
    - **id** : number, primary key, auto increment.
    - **user_name** : string, unique.
    - **password** : string.
    - **role_id** : number, references(role)->id, not null.

* ### User_Abilitie
    - **id** : number, primary key, auto increment.
    - **user_id** : number, references(user)->id, not null.
    - **ability_id** : number, references(ability)->id, not null.

* ### Teacher
    - **id** : number, primary key, auto increment.
    - **user_id** : number, referances(user)->id, not null, unique.
    - **name** : string.
    - **contact_number** : number.
    - **contact_email** : string.
    - **designation** : string.

* ### Student
    - **id** : number, primary key, auto increment.
    - **user_id** : number, referances(user)->id, not null, unique.
    - **standard_id** : number, referances(standard)->id, not null.
    - **section_id** : number, referances(section)->id, not null.
    - **name** : string.
    - **contact_number** : number.
    - **contact_email** : string.
    - **address** : string.
    - **dob** : Date.
    - **father_name** : string.
    - **mother_name** : string.
    - **guardian_name** : string.
    - **father_contact_number** : number.
    - **mother_contact_number** : number.
    - **guardian_contact_number** : number.