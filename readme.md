DMBase
=============

DMBase is a Digimaker(CMS) wrapper for projects to creating&maintaining a professional website easier/quicker. Shared features can be easilier maintained in different projects.

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
1) Content model

2) JS

3) PartialRender












How to use dmgit to keep dmbase code synced?
-----
1) go to project root
2) `git clone <dmbase repo> .dmbase`
3) `git --git-dir/.dmbase/.git pull`
4) use `./dmgit` like git or see below:(run below or put into .bash_profile so dmgit can be used globally)
`alias dmgit='git --git-dir=.dmbase/.git'`
5) Config dmgit exclude file(not using .gitignore but using .dmignore)
`dmgit config core.excludesfile=.dmignore` or add `excludesfile=.dmignore` to `.dmbase/.git/config`


Structure
-----

 ### 1. Stylesheet
- core.css - global style(eg h1, h2, a) and predefined core class(eg. .hide, .error, table.list )
- content.css - content-related style(eg. .title{}, .description{}, .full .title{}, .blockitem .title{} )
- mobile.css - responsive style
- (in project repo)<projectname>.css - project related css


### 2. Javascript
- scripts/dmbase.js - a base js for our project
- (in project repo)scripts/<projectname>.css - project related script

### 3. Tempaltes
- views/standard - standard template
- views/dmbase - default dmbase example templates
- view/<projectname> - project specific templates

### 4. Classes
Generic classes is put under App_Code/DMBase. Import classes:
(TBD)

### 5. Configurations
 - site.json: (TBD)
 - override.json (TBD)














