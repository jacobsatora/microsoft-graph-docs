---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
mgc teams channels messages patch --team-id {team-id} --channel-id {channel-id} --chat-message-id {chatMessage-id} --body '{\
  "policyViolation": {\
    "policyTip": {\
      "generalText" : "This item has been blocked by the administrator.",\
      "complianceUrl" : "https://contoso.com/dlp-policy-page",\
      "matchedConditionDescriptions" : ["Credit Card Number"]\
    },\
    "verdictDetails" : "AllowOverrideWithoutJustification,AllowFalsePositiveOverride",\
    "dlpAction" : "BlockAccess"\
  }\
}\
'

```