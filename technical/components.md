There are two major pieces to the proposed system. This is done to give us flexibility in the future.

### Open Source
The *Open* portions revolve around the *core data* (reports, items, components, factors, formulae, etc) and basic oAuth authentications. These provide a research-friendly data api. 

*  `econinja/api` - The core, open api and lumen framework, with service provider hooks (for samurai)
  *  `shared`/`core` - The pieces shared by both `console` and `http`, including all repos, resources, conversions, etc
*  `firetail/core` - Shared utilities for all Firetail projects
*  `firetail/testing` - Shared testing utilities for all Firetail projects
*  `firetail/spider` - Open source, repository based, composable Data Abstraction Layer, specifically for graph and document data
*  ??`econinja/client` - A basic client to interact with the open api (and hooks for the full app)??

### Closed Source
The *Closed* portions are those pieces that help turn that open data exchange into a user-friendly and effective expeirence. This includes user profiles, saved collections, gamification, enhanced streams, and the front-end app itself (or at least part of it).

*  `firetail/samurai` - All the awesome extensions to make the Firetail App work (gamification, users, bits, etc)