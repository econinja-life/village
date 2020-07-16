## Resources
- *Items*: Individual things made up of __concrete factors__ and __variable factors__
- *Concrete Factors*: The pieces of the _stored_ pieces of the equation
  - *Components*: Things that are used to build `items` (ingredients, resources, etc)
  - *Processes*: The building process of something, including average energy
  - *Waste*: Is the item biodegradable?
  - *Producer*: Any data about the eco responsibility of the producer, distributor, etc
- *Variable Factors*: Resources that store information about variables such as quantity, weight, etc that are used in the equation
- *Formula*: The steps involved in calculating the overall score/report for an item.
- *ReportsStubbedRepository*: Complex queries that create a findable report with all item and scoring information (cachable)
- *Sources*: Identifying information used by data conversion and manager (other apis, screen grabbers, etc)
- *Articles*: Some static comment (tips, articles, posts, how-tos, videos, etc)
- *Tags*: Taxonomies for
  - *item-tags* (blue, green, food, etc) <no categories for items>
  - *component-tags*
  - *article-tags*
- *Actors*: Entities that DO things to the system
- *Users*: Live, registered users
- *Entities*: Automated or third-party systems that act upon the api
- *Streams*: Event and notification streams
- *Events*: Events and notifications that make up streams

## And in table form
A basic table of the different resources and data types served and handled by the api.
```
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
| Code  | Single Name   | Description           | Relation(s)               | Attributes                | W   R  | HTTP     URL                              |
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
    Primarily Graph Data
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
| T     | `Tag`         | Blue, fish, etc       | =(C) / (P,C,Pr,Pd,A)=     | label, slug, etc          | 01, 10 | G<P>(D)  /tags                   |
| C     | `TagCategroy` | System code for tax   | (T) =                     | label, slug, etc          | 01, 10 | G(PD)    /tag-categories         |
| P     | `Product`     | The main product      |* =(C,P,Pr,Pd)=*           | desc,                     | 03  10 | G(PD)    /products               |
| C     | `Component`   | Ingredients, etc      | =(P)                      | scores, factors           | 03  10 | G(PD)    /components             |
| Pr    | `Process`     | How its made          | =(P)                      | scores, factors           | 03  10 | G(PD)    /processes              |
| Pd    | `Producer`    | Who makes it          | =(P)                      | scores, factors           | 03  10 | G(PD)    /producers              |
| A     | `Article`     | Static-ish data       | =(U,T)                    | <semi-structured>         | 05, 10 | G<PD>    /articles               |
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
    Primarily Document (Non-Relational or Cached) Data
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
| R/AR  | `Report`      | A scored report       | =(P,C,Pr,Pd)              | <Many nested>             | 05  10 | GP(D)    /reports</aggregated>   |
| U     | `User`        | Any actor (entity)    | (R,P,A)=                  | info, type                | 03, 10 | GPD      /users                  |
| R     | `Role`        | Multiple Permissions  | =(U) / (P)=               | labels                    | 01, 10 | (GPD)    /roles                  |
| P     | -`Permission` | A single permission   | =(U,R)                    | labels                    | 01, 10 | (GPD)    /permissions            |
| S     | `Source`      | A source of data      |                           | <semi-structured>         | 03, 05 | (GPD)    /data/sources           |
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
    Primarily Event Data (could be document or elastisearch)
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
| S     | `Stream`      | Collections of A      | =(U) / (A)=               | type                      | 10, 05 | G(PD)    /streams                |
| A     | `Activity`    | A single action       | =(U,S)                    | actor, dates, what        | 10, 05 | G(PD)    /activities             |
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
```