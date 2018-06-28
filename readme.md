DMBase
=============

DMBase is a Digimaker(CMS) wrapper for projects to creating&maintaining a professional website easier/quicker. Shared features can be easilier maintained in different projects.

Example: http://dmbase.dev.digimaker.no

There are some benefits using DMBase:
- Multi sites - so multiple sites can be hosted in one digimaker instance(so different sites can share settings - eg. layout, css, uploaded images, and also code is more controlable/updatable in git ).

- Template override - make it easier to write template based on content(eg. article/menuitem attributes, subnode, content extension value).

- Easily invoke shared feature. Shared feature can be invoked in below ways:
  1) C#/js api. eg. get content extension value, get tree structure from menuitem.
  2) cshtml partical render. eg. output an article(how is article outputed be up to the overrided templated)
  3) Remote api(json). eg. get children of a menuitem
  4) existing feature(eg. google site search, rss, etc). eg. output pdf will be done in /pdf/<article id>.

- Professional error report. 

- Debug info so the administrator can quickly know the rendering process and performance.


1) How to use
1.1) update/deploy to server
script


2) How to develop/extend





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














