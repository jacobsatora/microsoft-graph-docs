---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
mgc teams channels create --team-id {team-id} --body '{\
  "displayName": "My First Shared Channel",\
  "description": "This is my first shared channel",\
  "membershipType": "shared",\
  "members": [\
    {\
      "@odata.type": "#microsoft.graph.aadUserConversationMember",\
      "user@odata.bind": "https://graph.microsoft.com/v1.0/users('7640023f-fe43-573f-9ff4-84a9efe4acd6')",\
      "roles": [\
        "owner"\
      ]\
    }\
  ]\
}\
'

```