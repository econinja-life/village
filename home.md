# EcoNinja
Strives to place data-driven tools in the hands of individuals and organizations to help them live and operate in a more ecologically sustainable way.

# Overview
This page is the starting point for all your adventures.

This wiki is the primary knowledge share for all the associated **EcoNinja** products, projects, and work. This is the central location. Individual projects may have more specialized documentation in their wikis, but should link to and from this one.

For now, this also includes any organization and business material. That will likely split off eventually.

The Wiki is divided into a few basic parts:
1. This overview
  - General Terms used throughout
2. [Product Information](product/home): user stories, features, milestones
2. [Business](business/home): financial information, business plans, partnerships, etc
3. [Technical](technical/home): guides for developers, code styles, overviews

## Product and Workflow Terms
### Basic Terms
- **Products**: The top level of the hierarchy, those things that are used and seen by people. (Not to be confused with the Resource Type, `Product`)
- **Supporting Pieces**: Top level pieces that are meant to support the various products
  - see [technical/components](technical/components) for a some of the individual projects
- **Projects**: The individual libraries or git repositories and associated issues and wikis. 
  - See [technical/components](technical/components) for a list of individual projects
- **Sections**: The main divisions (from a user and story perspective) of the samurai app (Learn, Share, Do, Me)


*NOTE*: **Products** and **Supporting Pieces** have associated labels for issues, todos, and merge requests. Associated labels are in `red`


### Products:
  - **Open Application (EcoNinja)**: The open-for-all data / research application (api and cli)
     - **Api**: The Open, Restful API and Api Framework (oath). `API`, `API-AUTH`
     - **Cli**: The task management and conversion wrangling through the command-line. `CLI`
     - **Conversion**: The queues, workers, spider-repositories, and processes involved in populating from data sources. `DATA`
  - **Samurai**: The closed source app and supporting api enhancements (Learn, Share, Do, Me)
    - **Samurai Api**: The backend for the Samurai project. `SAM-API`
    - **Samurai App**: The front end (maybe multiple) for the app. `SAM-UX`

### Supporting Pieces
  - **Firetail Libraries**: Anything that is technical relating to the shared firetail libraries specifically. `FT-*`, `FT-SPIDER`
  - **Web**: Marketing website, documentation, etc, `WEB`
  - **Administration**: All marketing, branding, and business. `ADMIN`
  - **Research**: Anything pertaining to research and partnerships. `RESEARCH`
  - **Operations**: Infrastructure and software for devops (docker, etc). `OPS`

### Sections
From the user's point of view, this is how we group together the various features of the app itself.

#### Data
Access the RESTful API to interact with the raw data for research or app building.

#### Learn
Tips, tricks, articles, and such. Ways to learn about all the stuff econinja supports.

#### Share
Interact with others, promote, and socialize.

#### Do
Get reports, write senators, find volunteer opportunities, play games, and earn badges.

#### Me
Personalized dashboards and content for each of the above.