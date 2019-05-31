---
layout: post
title: "Entity–Relationship Model"
tagline: "Introduction to ER Diagrams"
categories: Technology
author: "Isuri Amarasena"
---

![Entity–Relationship Model](https://github.com/aviorsys/aviorsys.github.io/raw/master/images/erd-template.png)

# Entity Relationship Diagrams

Entity Relationship Diagram (ER Diagram) represents the relationship between the entities within a system. 

Peter Chen is known as the father of ER modelling. His focus was on entities and relationships and he introduced a diagramming representation for database design.
His model was inspired by the data structure diagrams introduced by Charles Bachman. One of the early forms of ER diagrams, Bachman diagrams are named after him.

## ER Diagram Symbols and Notations


The three main basic elements of an ER diagram are the Entity, Attribute and Relationship. There are other elements in ER diagrams such as weak entity, multi valued attribute, derived attribute, weak relationship, and recursive relationship which are deriving from the main three elements. 

1. Entity - An entity is represented by a rectangle. It could be a place, person, object etc which is related to the system in consideration.  Eg. Pilot, Employee, Department etc

2. Weak Entity - A weak entity is an entity that depends on another entity. A weak entity cannot exist on its own. Eg. Employee dependent is a weak entity. Employee dependent (weak) entity cannot exists without the entity Employee. 


2. Attribute - An attribute is represented by an ellipse. Attributes are properties of an entity. 

Eg. Entity Employee can have properties such as Employee Number, Employee Name, Employee Age etc. 
 
- Multi Valued Attribute - Represented by a double ellipse. It is an attribute that has more than one value. Eg. Employee Contact Number is a multivalued attribute because an employee can have more than one contact number. 

- Derived Attribute - Derived attributes are attributes which are not maintained in the database but derived/obtained from other attributes. Eg. Age of an employee can be derived from the date of birth attribute. 

- Composite Attribute - A composite attribute is a combination of more than one attribute. 
Eg. Full Name attribute is a combination of First Name, Middle Name, Last Name attributes.

## Entity-Set and Keys

Key is an attribute or a combination of attributes that helps to identify an entity uniquely within an entity set. 

Super Key − A set of attributes (one or more) that collectively identifies an entity in an entity set.

Candidate Key − A minimal super key is called a candidate key. An entity set may have more than one candidate key. A candidate key is also a super key without redundancy keys. 

Primary Key − A primary key is one of the candidate keys chosen by the database designer to uniquely identify the entity set.

# Relationship

How entities associate with each other is represented by a relationship. Relationships are graphically displayed by diamond shapes and are labeled using verbs.

1. Recursive Relationship - If the same entity participates more than once in a relationship it is known as a recursive relationship. 

2. Cardinality - This defines the number of entities in one entity set, which can be associated with the number of entities of other set via relationship set. 

- One to One - One value of an entity is associated with one and only one value of another entity.

- One to Many - One value of an entity is associated with many values of another entity.

- Many to Many - Multiple values in an entity are associated with multiple values in another entity.

## ER Diagram Best Practices

- Provide a precise and appropriate name for each entity, attribute, and relationship in the diagram. Terms that are simple and familiar always beats vague, technical-sounding words. In naming entities, remember to use singular nouns. However, adjectives may be used to distinguish entities belonging to the same class (part-time employee and full-time employee, for example). Meanwhile attribute names must be meaningful, unique, system-independent, and easily understandable.

- Remove vague, redundant or unnecessary relationships between entities.

- Never connect a relationship to another relationship.

- Make effective use of colors. You can use colors to classify similar entities or to highlight key areas in your diagrams.

## References

<https://creately.com/blog/diagrams/er-diagrams-tutorial/>

<https://www.tutorialspoint.com/dbms/er_model_basic_concepts.htm>

<https://en.wikipedia.org/wiki/Entity%E2%80%93relationship_model>

<https://www.youtube.com/watch?v=CsGalH0QKbs>

<https://fmhelp.filemaker.com/help/17/fmp/en/index.html#page/FMP_Help%2Fmany-to-many-relationships.html%23>

<https://www.dragon1.com/watch/80556/singular-architecture-principle-details-diagram>

<embed src="https://drive.google.com/viewerng/viewer?embedded=true&url=https://github.com/aviorsys/aviorsys.github.io/raw/master/uploads/ER-Diagram.pdf" width="100%" height="500">







