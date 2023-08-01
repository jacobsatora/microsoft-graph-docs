---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
mgc communications calls create --body '{\
  "@odata.type": "#microsoft.graph.call",\
  "callbackUri": "https://bot.contoso.com/callback",\
  "requestedModalities": [\
    "audio"\
  ],\
  "mediaConfig": {\
    "@odata.type": "#microsoft.graph.serviceHostedMediaConfig",\
    "preFetchMedia": [\
      {\
        "uri": "https://cdn.contoso.com/beep.wav",\
        "resourceId": "f8971b04-b53e-418c-9222-c82ce681a582"\
      },\
      {\
        "uri": "https://cdn.contoso.com/cool.wav",\
        "resourceId": "86dc814b-c172-4428-9112-60f8ecae1edb"\
      }\
    ]\
  },\
  "meetingInfo": {\
    "@odata.type": "#microsoft.graph.joinMeetingIdMeetingInfo",\
    "joinMeetingId": "1234567",\
    "passcode": null\
  },\
  "tenantId": "86dc81db-c112-4228-9222-63f3esaa1edb"\
}\
'

```