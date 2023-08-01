---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
mgc identity conditional-access policies create --body '{\
    "displayName": "Access to EXO requires MFA",\
    "state": "enabled",\
    "conditions": {\
        "clientAppTypes": [\
            "mobileAppsAndDesktopClients",\
            "browser"\
        ],\
        "applications": {\
            "includeApplications": [\
                "00000002-0000-0ff1-ce00-000000000000"\
            ]\
        },\
        "users": {\
            "includeGroups": ["ba8e7ded-8b0f-4836-ba06-8ff1ecc5c8ba"]\
        },\
        "locations": {\
            "includeLocations": [\
                "All"\
            ],\
            "excludeLocations": [\
                "AllTrusted"\
            ]\
        }\
    },\
    "grantControls": {\
        "operator": "OR",\
        "builtInControls": [\
            "mfa"\
        ]\
    }\
}\
'

```