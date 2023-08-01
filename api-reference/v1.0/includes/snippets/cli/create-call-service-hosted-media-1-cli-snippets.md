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
  "targets": [\
    {\
      "@odata.type": "#microsoft.graph.invitationParticipantInfo",\
      "identity": {\
        "@odata.type": "#microsoft.graph.identitySet",\
        "user": {\
          "@odata.type": "#microsoft.graph.identity",\
          "displayName": "John",\
          "id": "112f7296-5fa4-42ca-bae8-6a692b15d4b8"\
        }\
      }\
    }\
  ],\
  "requestedModalities": [\
    "audio"\
  ],\
  "callOptions": {\
    "@odata.type": "#microsoft.graph.outgoingCallOptions",\
    "isContentSharingNotificationEnabled": true\
  },\
  "mediaConfig": {\
    "@odata.type": "#microsoft.graph.serviceHostedMediaConfig"\
  }\
}\
'

```