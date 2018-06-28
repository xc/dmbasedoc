DMBase
=============

DMBase is a Digimaker(CMS) lightweight wrapper for projects to creating&maintaining a professional website easier/quicker. It focus more on templating&code readbility with less coding.

Example: http://dmbase.dev.digimaker.no


Benefits
===========
- Use MVC+razor templating - better way of templating and routing, comparing to asp.net+sitebuilder web control+http handler

- Multi sites - Multiple sites can be hosted in one digimaker instance without redirection(so different sites can share settings, resources,  - eg. layout, css, templates, uploaded images, and also code is more controlable/updatable in git ).

- Template override - make it easier to write template based on content and site(eg. article/menuitem attributes, subnode, content extension value). (for instance, error message can be customzied based on error code and site, instead of a standard .net 500 technical error)

- Common api and feature. eg. metadata output, google site search, print version, SEO(for instance canical link) etc. And with time, more features will be added and will be easy to use.

- Nice error page(overridable to different site) and error report to administrator. 

- Debug info so the administrator can quickly know the rendering process and performance benchmark.

Improvements based on Digimaker
--------------------
- Nice url using mvc pattern instead of http handler(easier to understand&extend), removing Norwegian characters so url copy and paste looks better.
- [To be implemented]Handle picture in template/json(eg. define small, medium size) instead of settings in web.config
- One menuitem/article can have different templates based on location/metadata/content extension values
- Menuitem view can easily invoke article view, article view invoking article view easier with override(comparing site builder).
- Easier content/content extension fetching api. 2 ways: fetch content extension value from article, fetch article/menuitem based on content extension values

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




Features to be implemented
================
- Image alias(eg. small, mediam, frontpage) defined in site.json and used in template: eg. imagePath.ResizeImage( "small" ), so it uses the right size pictures.
- Override.json supports 2 level config, meaning to put Site to a uppler level: 
```
{
   "examplesite":
    {
    "Type": "article",
    "Viewmode": "full",
    "Extended_Layout": "3columns",
    "Path": "article/full-3column.cshtml"
    }
    ...,
    "common":
    {
    ...
    }
  }
```


- Content extension value override rule(override.json): 

Eg 1.Direct attribute:
```
{
    "Type": "article",
    "Viewmode": "full",
    "Extended_Layout": "3columns",
    "Site": "examplesite",
    "Path": "article/full-3column.cshtml"
  }
```

Eg 2. Articles under a 'section':
```
{
    "Type": "article",
    "Viewmode": "full",
    "Under_Extended_1_Section": "AboutUs",
    "Site": "examplesite",
    "Path": "article/full-3column.cshtml"
  }
```


Principles
==============
- Id can only exist in config file(eg. web.config/digimaker.config/site.json). Never put id into template or worse csfile
- Template file name/folder name can show the actual meaning. eg. article/full-agreement.cshtml means the agreement article in full mode




