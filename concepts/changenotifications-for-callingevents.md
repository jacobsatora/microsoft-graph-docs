---
title: "Get change notifications for Microsoft Teams calls"
description: "Use change notifications in Microsoft Graph to enable you to subscribe to call started/ended for Microsoft Teams calls."
author: "awang119"
ms.localizationpriority: high
ms.prod: "cloud-communications"
ms.custom: scenarios:getting-started
---

# Get change notifications for Microsoft Teams call updates

Changes to call conversation events are available for subscriptions. Subscriptions to call conversations provide notifications for call start and call end events for the user that has been subscribed for. These notifications are a great opportunity for customers to  collect and data and provide better insights.

## Permissions

| Permission type                       | Permissions (from least to most privileged)              | Supported versions |
|:--------------------------------------|:---------------------------------------------------------|:-------------------|
| Delegated (work or school account)    | N/A                                                      | Not supported.     |
| Delegated (personal Microsoft account)| N/A                                                      | Not supported.     |
| Application                           | CallConversation.Read.All (Pending)                      | beta               |

## Calling scenarios

| Call type          | Description                                              |
|:-------------------|:---------------------------------------------------------|
| PSTN               | Pending                                                  |
| Adhoc call         | Pending                                                  |


## Subscriptions

For more details on how subscriptions are made to Microsoft Graph, please see [Create Subscriptions](/graph/api/subscription-post-subscriptions).

### Subscription Resource
The following resources will be supported for subscription to call conversations

| Scenario                               | Resource                              | Change types |
|:---------------------------------------|:--------------------------------------|:-------------|
| Call conversations for a specific user | user/{userObjectId}/callConversations | updated      |

### Subscription expiration

Call conversation subscriptions can have a max duration of a day before it expires. To prolong this subscription, a subscription update request is required. See [Update subscription](/graph/api/subscription-update) for more details. Alternatively, a new subscription may be created for the same resource property after the previous one has expired.

### Subscriptions with resource data

Subscriptions to call conversations only support notifications notification with resrouce data and will not support basic notifications. For more details about rich notifications, see [Set up change notifications that include resource data](/graph/webhooks-with-resource-data).

### Subscription payload example

```json
{
    "changeType": "updated",
    "notificationUrl": "https://webhook.contoso.com/api",
    "lifecycleNotificationUrl": "https://webhook.contoso.com/api",
    "resource": "user/{userObjectId}/callConversations",
    "expirationDateTime": "2023-12-14T10:00:00.0000000Z",
    "includeResourceData": true,
    "encryptionCertificate": "{base64encodedCertificate}",
    "encryptionCertificateId": "{customId}",
    "clientState": "{secretClientState}"
}
```

## Notifications

Call conversation subscriptions will receive notifications when the user of interest enters or leaves applicable calling scenarios. Resource data from notifications will be included in notification payload and will need to be decrypted before it is used.

### CallConversationStarted resource data example

```json
{	 
    "@odata.type":"#Microsoft.Graph.CallConversation", 
    "@odata.id": "/user/{userObjectId}/callConversations", 
    "id":"/user/{userObjectId}/callConversations", 
    "eventType":"{Microsoft.Communication.CallConversationStarted}", 
    "direction":"{incoming/outgoing}",
    "csUrl":"https://api.flightproxy.teams.microsoft.com/api/v2/ep/conv-jpea.conv.skype.com/conv/IU-j__abcdef123343?i=7&e=12345678"
}
```

### CallConversationEnded resource data example

```json
{	 
    "@odata.type":"#Microsoft.Graph.CallConversation", 
    "@odata.id": "/user/{userObjectId}/callConversations", 
    "id":"/user/{userObjectId}/callConversations", 
    "eventType":"{Microsoft.Communication.CallConversationEnded}", 
    "direction":"{incoming/outgoing}",
    "csUrl":"https://api.flightproxy.teams.microsoft.com/api/v2/ep/conv-jpea.conv.skype.com/conv/IU-j__abcdef123343?i=7&e=12345678"
}
```