---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
mgc teams create --body '{\
   "template@odata.bind":"https://graph.microsoft.com/v1.0/teamsTemplates('standard')",\
   "group@odata.bind":"https://graph.microsoft.com/v1.0/groups('dbd8de4f-5d47-48da-87f1-594bed003375')",\
   "channels":[\
      {\
         "displayName":"Class Announcements 📢",\
         "isFavoriteByDefault":true\
      },\
      {\
         "displayName":"Homework 🏋️",\
         "isFavoriteByDefault":true\
      }\
   ],\
   "memberSettings":{\
      "allowCreateUpdateChannels":false,\
      "allowDeleteChannels":false,\
      "allowAddRemoveApps":false,\
      "allowCreateUpdateRemoveTabs":false,\
      "allowCreateUpdateRemoveConnectors":false\
   },\
   "installedApps":[\
      {\
         "teamsApp@odata.bind":"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.vsts')"\
      },\
      {\
         "teamsApp@odata.bind":"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('1542629c-01b3-4a6d-8f76-1938b779e48d')"\
      }\
   ]\
}\
'

```