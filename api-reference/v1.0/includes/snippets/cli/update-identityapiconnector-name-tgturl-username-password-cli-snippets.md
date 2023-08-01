---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
mgc identity api-connectors patch --identity-api-connector-id {identityApiConnector-id} --body '{\
  "displayName": "New Test API",\
  "targetUrl": "https://otherapi.com/api/endpoint",\
  "authenticationConfiguration": {\
    "@odata.type": "microsoft.graph.basicAuthentication",\
    "username":"<NEW_USERNAME>", \
    "password":"<NEW_PASSWORD>"\
  }\
}\
'

```