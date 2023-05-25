---
title: "Get change notifications for Microsoft Teams calls"
description: "Use change notifications in Microsoft Graph to enable you to subscribe to call started/ended for Microsoft Teams calls."
author: "awang119"
ms.localizationpriority: high
ms.prod: "cloud-communications"
ms.custom: scenarios:getting-started
---

# Get change notifications for Microsoft Teams call updates

Changes to call events are available for subscription. Subscriptions to call events provide notifications for call start and call end events for the user that has been subscribed for. These notifications are a great opportunity for customers to collect and data and provide better insights.

## Permissions

| Permission type                       | Permissions (from least to most privileged) | Supported versions |
|:--------------------------------------|:--------------------------------------------|:-------------------|
| Delegated (work or school account)    | N/A                                         | Not supported.     |
| Delegated (personal Microsoft account)| N/A                                         | Not supported.     |
| Application                           | CallEvents.Read.All                         | beta               |

## Calling scenarios
- Adhoc call team calls for 1:1 or group calls.
- Public Switched Telephone Network (PSTN) for 1:1 or group calls, see [Teams voice solution](/microsoftteams/cloud-voice-landing-page) for more details.


## Subscriptions

For more details on how subscriptions are made to Microsoft Graph, please see [Create Subscriptions](/graph/api/subscription-post-subscriptions).

### Subscription Resource
The following resources will be supported for subscriptions to call events

| Scenario                               | Resource                              | Change types |
|:---------------------------------------|:--------------------------------------|:-------------|
| Call events for a specific user | users/{userId}/communications/callevents | updated      |

### Subscription expiration

Call event subscriptions can have a max duration of a day before it expires. To prolong this subscription, a subscription update request is required. See [Update subscription](/graph/api/subscription-update) for more details. Alternatively, a new subscription may be created for the same resource property after the previous one has expired.

### Subscriptions with resource data

Subscriptions to call events only support notifications notification with resource data and will not support basic notifications. For more details about rich notifications, see [Set up change notifications that include resource data](/graph/webhooks-with-resource-data).

### Subscription payload example

```json
{
    "changeType": "updated",
    "notificationUrl": "https://webhook.contoso.com/api",
    "lifecycleNotificationUrl": "https://webhook.contoso.com/api",
    "resource": "/users/{userId}/communications/callEvents",
    "expirationDateTime": "2023-12-14T10:00:00.0000000Z",
    "includeResourceData": true,
    "encryptionCertificate": "{base64encodedCertificate}",
    "encryptionCertificateId": "{customId}",
    "clientState": "{secretClientState}"
}
```

## Notifications

Call event subscriptions will receive notifications when the user of interest enters or leaves applicable calling scenarios. Resource data from notifications will be included in notification payload and will need to be decrypted before it is used.

### Call event notifications sample
```json
{
  "@odata.type": "#microsoft.graph.changeNotification",
  "changeType": "String",
  "clientState": "String",
  "encryptedContent": {
    "@odata.type": "microsoft.graph.changeNotificationEncryptedContent",
    "data": "String",
    "dataKey": "String",
    "dataSignature": "String",
    "encryptionCertificateId": "String",
    "encryptionCertificateThumbprint": "String"
  },
  "id": "String (identifier)",
  "lifecycleEvent": "String",
  "resource": "String",
  "resourceData": {
    "@odata.type": "microsoft.graph.callEvent",
    "@odata.id": "/users/{userId}/communications/callEvents/{notification ID}",
    "id":"{notification ID}",
  },
  "subscriptionExpirationDateTime": "String (timestamp)",
  "subscriptionId": "Guid",
  "tenantId": "Guid"
}
```

### Call Started event decrypted resource data example
```json
{	 
    "@odata.type":"#Microsoft.Graph.CallEvent", 
    "@odata.id": "/users/{userId}/communications/callEvents", 
    "id":"/users/{userId}/communications/callEvents",
    "eventType":"{Microsoft.Communication.CallEventType.CallStarted}", 
    "direction":"{microsoft.graph.callDirection}",
    "joinCallUrl":"https://api.flightproxy.teams.microsoft.com/api/v2/ep/conv-jpea.conv.skype.com/conv/IU-j__abcdef123343?i=7&e=12345678",
    "callId": "{CallId}"
}
```

### Call Ended event decrypted resource data example
```json
{	 
    "@odata.type":"#Microsoft.Graph.CallEvent", 
    "@odata.id": "/users/{userId}/communications/callEvents", 
    "id":"/users/{userId}/communications/callEvents",
    "eventType":"{Microsoft.Communication.CallEventType.CallEnded}", 
    "direction":"{microsoft.graph.callDirection}",
    "joinCallUrl":"https://api.flightproxy.teams.microsoft.com/api/v2/ep/conv-jpea.conv.skype.com/conv/IU-j__abcdef123343?i=7&e=12345678",
    "callId": "{CallId}"
}
```