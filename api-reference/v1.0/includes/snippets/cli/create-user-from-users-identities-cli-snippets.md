---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
mgc users create --body '{\
  "displayName": "John Smith",\
  "identities": [\
    {\
      "signInType": "userName",\
      "issuer": "contoso.onmicrosoft.com",\
      "issuerAssignedId": "johnsmith"\
    },\
    {\
      "signInType": "emailAddress",\
      "issuer": "contoso.onmicrosoft.com",\
      "issuerAssignedId": "jsmith@yahoo.com"\
    },\
    {\
      "signInType": "federated",\
      "issuer": "facebook.com",\
      "issuerAssignedId": "5eecb0cd"\
    }\
  ],\
  "passwordProfile" : {\
    "password": "password-value",\
    "forceChangePasswordNextSignIn": false\
  },\
  "passwordPolicies": "DisablePasswordExpiration"\
}\
'

```