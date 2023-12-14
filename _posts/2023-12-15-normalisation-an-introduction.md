---
layout: post
title:  "Normalisation: An Intro"
date:   2023-12-15
categories: SQL
tags: 
  - Normalisation
---
I've been sat thinking about what my first _real_ post should be.  Then it hits me. I've described myself as a Database Developer and the one thing that all relational databases need regardless of manufacturer or technology is **NORMLISATION.**

Now this is one of those topics that is going to need a lot of diagrams to help the explanation so apologies in advance if you're on your phone :)

I am acutely aware there is a lot of opinion on how far you need to go, so I'm going to write a mini series.  First up what, why etc.  Then onto the actual forms and examples of using them. I'll split these into beginner (up to 3NF), then extend on that further with intermediate (up to DKNF) and if anyone is still interested past that I will do an advanced which I expect most people won't look at. :)

# WHAT?
Normalisation is an iterative design process used to organise data to reduce redundancy and improve integrity of a data system.  There are several stages referred to as Normal Forms and each builds on the work of their predecessor.

# WHY?
The result of Normalisation reduces the size required to store data and helps keep the accuracy of data to a higher standard. It also allows the database to be more flexible to future requirements or scope creep :)

# HOW?
By removing repeated data it reduces the number of alterations required and the difficulty in making those alterations.  This is often referred to as undesirable characteristics associated with data insertion, deletion, and updating.  Basically errors introduced as a result of trying to make changes to the data in the system.

The process involves splitting often large tables of data into several smaller ones and creating relationships between those tables.  These relationships define how the data in the two tables can be used.

# WHO & WHEN?
British computer scientist [Edgar F. Codd](https://en.wikipedia.org/wiki/Edgar_F._Codd) first described the process as part of his theory called the [Relational Model](https://en.wikipedia.org/wiki/Relational_model) in 1969.

# The Details
OK now you have a very high level view of what it is and how it works lets start to look at the details.  As previously explained the process of Normalising data is an iterative one. Each step builds on the work done in the previous step.  These steps are called Normal Forms and data is only in a Normal Form if it satisfies the criteria for the current Normal Form **AND ALL** the previous ones.

So what are the Normal Forms?  I have listed them below in the order they should be completed.

| Order | Name | Shortened Name |
|---|---|---|
| 0 | UnNormalised Form | UNF |
| 1 | First Normal Form | 1NF |
| 2 | First Normal Form | 2NF |
| 3 | First Normal Form | 3NF |
| 4 | Elementary Key Normal Form | EKNF |
| 5 | Boyce-Codd Normal Form | BCNF |
| 6 | Fourth Normal Form | 4NF |
| 7 | Essential Tuple Normal Form | ETNF |
| 8 | Fifth Normal Form | 5NF |
| 9 | Domain Key Normal Form | DKNF |
| 10 | Sixth Normal Form | 6NF |

In my next few posts I will explain the Normal Forms in more detail and work through normalising an example data set.  I will start very gently and go as far as 3NF.  This is often where small projects stop the normalisation process as going any further would over complicate a simple solution.  I will then progress to DKNF. This is often the point at which large systems for corporations stop.  Then just to be complete I will do a final post about 6NF.
