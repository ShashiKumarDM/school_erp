# School Database Design

## Tables

1. Standard
2. Section
3. Subject
4. Standard_Sections
5. Standard_Subject
6. Fee_Details
7. Role
8. Ability
9. Role_Ability
10. User
11. User_Ability
12. Teacher
13. Student
14. Student_Fee_details
15. Student_Payment_details
16. Notes
17. Online_class


## Table Attributes and Relations

>All tables will have created_at and updated_at attributes as Date Time type.

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

* ### User_Ability
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

* ### Student_Fee_details
    - **id** : number, primary key, auto increment.
    - **student_id** : number, referances(student)->id, not null.
    - **title** : string.
    - **amount** : number, not null.
    - **ballance** : number.

* ### Student_Payment_details
    - **id** : number, primary key, auto increment.
    - **student_fee_details_id** : number, referances(student_fee_details)->id, not null.
    - **Amount** : number, not null.
    - **payment_type** : string, not null.
    - **description** : string.

* ### Notes
    - **id** : number, primary key, auto increment.
    - **standard_id** : number, referances(standard)->id, not null.
    - **section_id** : number, referances(section)->id, not null.
    - **subject_id** : number, referances(subject)->id, not null.
    - **notes_file_link** : string, not null.
    - **video_link** : string, not null.

* ### Online_class
    - **id** : number, primary key, auto increment.
    - **standard_id** : number, referances(standard)->id, not null.
    - **section_id** : number, referances(section)->id, not null.
    - **subject_id** : number, referances(subject)->id, not null.
    - **class_date_time** : string, not null.
    - **class_link** : string, not null.
