---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
mgc users mailbox-settings patch --user-id {user-id} --body '{\
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#Me/mailboxSettings",\
    "automaticRepliesSetting": {\
        "status": "Scheduled",\
        "scheduledStartDateTime": {\
          "dateTime": "2016-03-20T18:00:00.0000000",\
          "timeZone": "UTC"\
        },\
        "scheduledEndDateTime": {\
          "dateTime": "2016-03-28T18:00:00.0000000",\
          "timeZone": "UTC"\
        }\
    }\
}\
'

```