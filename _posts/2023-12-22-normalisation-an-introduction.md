---
layout: post
title:  "Normalisation: An Introduction"
date:   2023-12-22
categories: SQL
tags: 
  - Normalisation
---
I've been sat thinking about what my first _real_ post should be.  Then it hits me. I've described myself as a Database Developer and the one thing that all relational databases need regardless of manufacturer or technology is **NORMLISATION.**

Now this is one of those topics that is going to need a lot of diagrams to help the explanation so apologies in advance if you're on your phone :)

I am acutely aware, there is a lot of opinion on how far you need to go. So I'm going to write a mini series.  First up what, why etc.  Then onto the actual forms and examples of using them. I'll split these into beginner (up to 3NF), then extend on that further with intermediate (up to DKNF) and if anyone is still interested past that I will do an advanced which I expect most people won't look at. :)

# WHAT?
Normalisation is an iterative design process used to organise data to reduce redundancy and improve integrity of a data system.  There are several stages referred to as **Normal Forms** and each builds on the work of their predecessor.

# WHY?
The result of Normalisation reduces the size required to store data and helps keep the accuracy of data to a higher standard. It also allows the database to be more flexible to future requirements or scope creep :)

# HOW?
By removing repeated data it reduces the number of alterations required and the difficulty in making those alterations.  This is often referred to as anomalies associated with data insertion, deletion, and updating.  Basically errors introduced as a result of trying to make changes to the data in the system.

The process involves splitting often large tables of data into several smaller ones and creating relationships between those tables.  These relationships define how the data in the two tables can be used.

# WHO & WHEN?
British computer scientist [Edgar F. Codd](https://en.wikipedia.org/wiki/Edgar_F._Codd) first described the process as part of his theory called the [Relational Model](https://en.wikipedia.org/wiki/Relational_model) in 1969.

# The Normal Forms
As previously explained the process of Normalising data is an iterative one. Each step builds on the work done in the previous step.  These steps are called Normal Forms and data is only in a Normal Form if it satisfies the criteria for the current Normal Form **AND ALL** the previous ones.

So what are the Normal Forms?  I have listed them below in the order they should be completed.

| Order | Name | Shortened Name |
|---|---|---|
| 0 | UnNormalised Form | UNF |
| 1 | First Normal Form | 1NF |
| 2 | Second Normal Form | 2NF |
| 3 | Third Normal Form | 3NF |
| 4 | Elementary Key Normal Form | EKNF |
| 5 | Boyce-Codd Normal Form | BCNF |
| 6 | Fourth Normal Form | 4NF |
| 7 | Essential Tuple Normal Form | ETNF |
| 8 | Fifth Normal Form | 5NF |
| 9 | Domain Key Normal Form | DKNF |
| 10 | Sixth Normal Form | 6NF |

# Data Relationship Types
When looking at splitting large tables into smaller ones and creating relationships between those new tables it is important to understand the different data relationships available.
## One-to-One
A one to one relationship refers to 1 row in Table A being linked to 1 (and only 1) row, or no rows in Table B and vice versa. Imagine a company with a table of employees and a table of company mobile phones.  Each employee is only assigned 1 mobile phone.  Each mobile phone can only be assigned to 1 employee.

## One-to-Many
A one to many relationship refers to 1 row in Table A being linked to many rows in Table B and many rows in Table B linked to 1 row in table A.  Imagine a company with a table of customers and a table of sales invoices.  Each customer can have many sales invoices but each sales invoice can only be for one customer.

## Many-to-Many
A many to many relationship refers to many rows in Table A being linked to many rows in Table B and vice versa.  Imagine a college with a table of students and a table of classes.  Each class will have many students taking it and each student will take many classes.  In this relationship it is common practice to use an extra "Linking" table to store the relationship information.  More on this later.

# Keys
Keys are used to enforce data relationships between different tables. A key is a column or group of columns that uniquely identifies each row in a table. There are several different keys, but I will only list the important ones as far as understanding data relationships.  They are Primary, Foreign and Composite.

| Key Name | Description |
|---|---|
| Primary Key | One or more columns that uniquely identifies each row in a table. |
| Foreign Key| One or more columns that store a copy of the Primary Key of a parent table.  Values in the Foreign Key must match exactly the values in the Primary Key, or be null.
| Composite Key | If a key uses 2 or more columns to enforce uniqueness then it can be referred to as a Composite Key. Composite keys are used when a single column cannot uniquely identify each row and so additional columns are required. |

In my next few posts I will explain the Normal Forms in more detail and work through normalising an example data set.  I will start very simply and go as far as Third Normal Form or 3NF.  This is often where small projects stop the normalisation process as going any further would over complicate a simple solution.  I will then progress to Domain Key Normal Form or DKNF. This is often the point at which large systems for corporations stop.  Then just to be complete I will do a final post about Sixth Normal Form, 6NF.
