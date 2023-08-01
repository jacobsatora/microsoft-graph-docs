---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
mgc identity conditional-access named-locations patch --named-location-id {namedLocation-id} --body '{\
    "@odata.type": "#microsoft.graph.ipNamedLocation",\
    "displayName": "Untrusted named location with only IPv4 address",\
    "isTrusted": false,\
    "ipRanges": [\
        {\
            "@odata.type": "#microsoft.graph.iPv4CidrRange",\
            "cidrAddress": "6.5.4.3/18"\
        }\
\
    ]\
}\
'

```