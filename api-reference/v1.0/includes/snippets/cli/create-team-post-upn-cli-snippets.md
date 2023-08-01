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
   "displayName":"My Sample Team",\
   "description":"My Sample Team’s Description",\
   "members":[\
      {\
         "@odata.type":"#microsoft.graph.aadUserConversationMember",\
         "roles":[\
            "owner"\
         ],\
         "user@odata.bind":"https://graph.microsoft.com/v1.0/users('jacob@contoso.com')"\
      }\
   ]\
}\
'

```