
__ORM__ : Object-relational mapping - serves as a layere of abstraction between object oriented programming paradigms and relational database systems.

Document models suit one-to-many relationships in data model better than relational model. 

In many-to-many and many-to-one , both relational and document model uses a reference to the data called as foreign keys in relational and document reference in document model. Using relational dbs are advantageous as they support joins.

##### Use case of Document model
- Schema flexibility
- Better performance due to locality
- Hetergenous data

##### Use case of Relational model
- Support for joins
- many-to-one and many-to-many relationships is easier to represent

SQL like languages are _declarative_ whereas languages like C are _imperative_. In Declarative langauges, we just specify what we need rather than how to do it. 

Imperative : Declarative :: DOM : HTML/CSS 

#### Graph-Like Data Models
- Typically used for complex many-to-many relational data model.

##### Property Graphs
- Both vertices and edges are similar to tables in relational dbs.

![[property-graphs.png]]

##### Cypher Query Language
Insertion

![[cypher-insertion.png]]

Query ^dd6cdc

![[cypher-query.png]]

##### Triple Stores and SPARQL
Information is stored in terms of (subject, predicate, object). 
Subject ---> Object , _predicate_ is the info on the edge.

![[triple-stores.png]]

Same [[2 Data Models and Query Languages#^dd6cdc]] in sparkQL

![[sparql.png]]

