---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
mgc groups threads reply post --group-id {group-id} --conversation-thread-id {conversationThread-id} --body '{\
  "post": {\
    "body": {\
      "contentType": "text",\
      "content": "I attached an event."\
    },\
    "attachments": [{\
      "@odata.type": "#microsoft.graph.itemAttachment",\
      "name": "Holiday event", \
      "item": {\
          "@odata.type": "microsoft.graph.event",\
          "subject": "Discuss gifts for children",\
          "body": {\
              "contentType": "HTML",\
              "content": "Let's look for funding!"\
          },\
          "start": {\
              "dateTime": "2019-12-02T18:00:00",\
              "timeZone": "Pacific Standard Time"\
          },\
          "end": {\
              "dateTime": "2019-12-02T19:00:00",\
              "timeZone": "Pacific Standard Time"\
          }\
      }\
    } ]\
  }\
}\
'

```