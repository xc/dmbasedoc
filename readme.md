DMBase
=============

DMBase is a Digimaker(CMS) lightweight wrapper for projects to creating&maintaining a professional website easier/quicker. It focus more on templating&code readbility with less coding.

Example: http://dmbase.dev.digimaker.no


Benefits
===========
- Multi sites - Multiple sites can be hosted in one digimaker instance(so different sites can share settings - eg. layout, css, uploaded images, and also code is more controlable/updatable in git ).

- Template override - make it easier to write template based on content and site(eg. article/menuitem attributes, subnode, content extension value). (for instance, error message can be customzied based on error code and site, instead of a standard .net 500 technical error)

- Common api and feature. eg. metadata output, google site search, print version, SEO(for instance canical link) etc. And with time, more features will be added and will be easy to use.

- Nice error page(overridable to different site) and error report to administrator. 

- Debug info so the administrator can quickly know the rendering process and performance benchmark.

Improvements on Digimaker
--------------------
- Nice url using mvc pattern instead of http handler(easier to understand&extend), remvoving Norwegian characters so url copy and paste looks better.
- Handle picture in template/json(eg. define small, medium size) instead of settings in web.config
- Article view can have different templates based on location/metadata/content extension values
- Menuitem view invoking article view, article view invoking article view easier with override(comparing site builder).
- Easier content/content extension fetching api

Update/deploy to project
----------------------

Develop/extend dmbase
-------------------



API Reference 
===========================
1) Content model(TBD)

2) JS(TDB)

3) PartialRender(TBD)



Structure
-----

 ### 1. Stylesheet
- core.css - global style(eg h1, h2, a) and predefined core class(eg. .hide, .error, table.list )
- content.css - content-related style(eg. .title{}, .description{}, .full .title{}, .blockitem .title{} )
- \<proejectname\>-mobile.css - responsive style
- \<projectname\>.css - project related css


### 2. Javascript
- Scripts/dmbase.js - a base js for our project

### 3. Tempaltes
- views/shared - shared template
- view/<projectname> - project specific templates


### 5. Configurations
 - site.json: (TBD)
 - override.json (TBD)














