---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
mgc identity b2x-user-flows create --body '{\
    "id": "UserFlowWithAPIConnector",\
    "userFlowType": "signUpOrSignIn",\
    "userFlowTypeVersion": 1,\
    "apiConnectorConfiguration":{\
        "postFederationSignup":{\
            "@odata.id": "https://graph.microsoft.com/v1/identity/apiConnectors/{id}"\
        },\
        "postAttributeCollection":{\
            "@odata.id": "https://graph.microsoft.com/v1/identity/apiConnectors/{id}"\
        }\
    }\
}\
'

```