site.json
===============
Common Settings
------------------

- Host: host name of the site. This is useful when multisites using different domains/sub domains. Multiple domain can be separated by ;

- Url: relative url of the site(eg. eng, which is under xxx.com/eng). Multiple url can be separated by ;

- TemplateFolder: template folder of the sites.

- RootMenuitemId: the menuitem to get menu

- DefaultPageMenuitemId: the frontpage menuitem. It can be the same as <RootMenuitemId> or under it.

- DateTimeFormat: Time format. Example - "dd.MM.yyyy H:mm",

- TemplateDebug: enable or disable template debug, use this together with <DebugIp>. 

- DebugIp: who can see the debug information. eg. [ "::1", "127.0.0.1", "31.45.36.135" ]

Feature Specific Settings
-------------------
SectionMenuitemId: if you have header/bottom content(footer using article content)
