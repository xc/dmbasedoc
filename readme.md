DMBase
=============

DMBase is a Digimaker(CMS) lightweight wrapper for projects to creating&maintaining a professional website easier/quicker. Shared features can be easilier maintained in different projects.

Example: http://dmbase.dev.digimaker.no


Benefits
===========
- Multi sites - so multiple sites can be hosted in one digimaker instance(so different sites can share settings - eg. layout, css, uploaded images, and also code is more controlable/updatable in git ).

- Template override - make it easier to write template based on content(eg. article/menuitem attributes, subnode, content extension value).

- Easily reuse and upgrade shared feature in c#/js/template invoke.

- Professional error report to administrator. 

- Debug info so the administrator can quickly know the rendering process and performance.


1) How to use
----------
1.1) update/deploy to server
script


2) How to develop/extend
---------------




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














