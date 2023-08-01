---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

mgc policies token-lifetime-policies patch --token-lifetime-policy-id {tokenLifetimePolicy-id} --body '{\
  "definition": [\
    "definition-value"\
  ],\
  "displayName": "displayName-value",\
  "isOrganizationDefault": true\
=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc policies token-lifetime-policies patch --token-lifetime-policy-id {tokenLifetimePolicy-id} --body '{\
    "definition": [\
        "{\"TokenLifetimePolicy\":{\"Version\":1,\"AccessTokenLifetime\":\"5:30:00\"}}"\
    ],\
    "displayName": "Contoso token lifetime policy",\
    "isOrganizationDefault": true\
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
}\
'

```