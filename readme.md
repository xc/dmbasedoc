DMBase
=============

DMBase is a Digimaker(CMS) lightweight wrapper for projects to creating&maintaining a professional website easier/quicker. It focus more on templating&code readbility&reusability and coding less.

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

Set up new/Convert existing project to dmbase project
=============
1) Set up digimaker backend
2) Checkout dmbase example
3) Change digimkaer.config/ConnectionString to the right database connection
4) Change digimaker.config/IgnoreDigimakerWebHandler/Path|Host , add site host or path into so these path/host will use MVC way not http handler(old digimaker way)
5) site.json: config Host/Url, TemplatePath, RootMenuitemId, DefaultPageMenuitemId
6) override.json: rename examplesite to you site identifier(site.json's key)
7) Rename Views/ExampleSite to Views/\<TemplateFolder\>
8) Done. Visit host/path. 

More development will be on:
  - Configure override.json
  - Customize templates based on your need.

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
    "Path": "article/full.cshtml"
    }
    ...,
    "common":
    {
    ...
    }
  }
```


- Content extension value override rule(override.json): 

Eg 1.Direct attribute: if content extension attribute Layout is 3 columns, use full-3columns.cshtml
```
{
    "Type": "article",
    "Viewmode": "full",
    "Extended_Layout": "3columns",
    "Site": "examplesite",
    "Path": "article/full-3columns.cshtml"
  }
```

Eg 2. Articles under a 'section': all the articles under section AboutUs(first level menuitem's content extension attribute Section's value is AboutUs) will use full-aboutus.cshtml(eg. AboutUs/Compnay/History, AboutUs/Company/FinancialReport)
```
{
    "Type": "article",
    "Viewmode": "full",
    "Under_Extended_1_Section": "AboutUs",
    "Site": "examplesite",
    "Path": "article/full-aboutus.cshtml"
  }
```


Development Principles
==============

Readability
-------------
- ID can only exist in config file(eg. web.config/digimaker.config/site.json). Never put id into template or worse csfile. Use identifier in coding and mapping in config file or content instead.
- Template file name/folder name should try to show the actual meaning. eg. article/full-agreement.cshtml means the agreement article in full mode

Security&Stability
---------
- Never show technical message to end user.
- Try to log and report error

Reusability/Campatability
----------
- Try to make api/feature/template layout reuseable. Try to avoid writing duplicated code for same feature(eg. fetching content extension value), put api into dmbase first and optimize api to make it nicer.
- DMBase will be backward campatable. If there are 10 projects using dmbase for instance, after dmbase updating, old feature will not be broken, and some issues feature can even be improved automatically(eg. better error report).

