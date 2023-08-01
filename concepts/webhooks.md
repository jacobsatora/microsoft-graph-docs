---
title: "Set up notifications for changes in resource data."
description: "Change notifications enable applications to receive alerts when a Microsoft Graph resource they're interested changes."
author: FaithOmbongi
ms.author: ombongifaith
ms.reviewer: keylimesoda
ms.prod: "change-notifications"
ms.localizationpriority: high
ms.custom: graphiamtop20
ms.date: 07/19/2023
---

# Set up notifications for changes in resource data

Change notifications enable applications to receive alerts when a Microsoft Graph resource they're interested in changes; that is, created, updated, or deleted. Microsoft Graph sends notifications to the specified client endpoint, and the client service processes the notifications according to the business requirements. For example, the service may fetch more data, update its cache and views, and so on.

## Why get change notifications?

Change notifications follow an event-driven model where customers receive alerts when changes occur instead of them polling Microsoft Graph. Depending on your business logic, change notifications are suitable when:

- You're subscribing to a resource that changes frequently.
- You need to react to changes in near real-time.
- You want to avoid frequently polling Microsoft Graph which might cause you to hit the throttling limits.

> [!VIDEO https://www.youtube-nocookie.com/embed/rC1bunenaq4]

<!-- Add illustration-->

## Types of change notifications

Microsoft Graph supports three types of change notifications:

- **Basic notifications**: Change notifications that don't contain resource data other than the **id** of the resource that changed. All Microsoft Graph resources support basic notifications. When an app receives a basic notification, the service can use the **id** to query to changed object.
- **Rich notifications**: Change notifications that include the resource data of the object that changed. For more information about rich notifications, see [Rich notifications](./webhooks-with-resource-data.md).
- **Lifecycle notifications**: Notifications that alert the customer when they are at risk of missing change notifications due to the lifecycle of their subscription. For more information about lifecycle notifications, see [Lifecycle notifications](./webhooks-lifecycle.md).

## Supported resources

[!INCLUDE [change-notifications-supported-resources-expanded](includes/change-notifications-supported-resources-expanded.md)]

## Receiving change notifications

Microsoft Graph can deliver change notifications to clients via the following channels.

- **Webhooks**. For more information, see [Receive change notifications through webhooks](./change-notifications-delivery-webhooks.md).
- **Azure Event Hubs**. For more information, see [Receive change notifications through Azure Event Hubs](./change-notifications-delivery-event-hubs.md).
- **Azure Event Grid** (preview). For more information, see [Receive change notifications through Azure Event Grid](/azure/event-grid/subscribe-to-graph-api-events?context=graph%2Fcontext).

## Managing subscriptions

Clients can create subscriptions, renew subscriptions, and delete subscriptions. Then while the subscription is valid and when changes occur in the subscribed resource, Microsoft Graph sends change notifications to the specified notification endpoint.

You manage the subscription using the [subscription resource type](/graph/api/resources/subscription) and its related methods. While the subscription is valid and changes occur in the subscribed resource, Microsoft Graph sends a change notification in a structure defined in the [changeNotificationCollection resource type](/graph/api/resources/changenotificationcollection).

### Subscription lifetime

Subscriptions have a limited lifetime. Apps need to renew their subscriptions before the expiration time; Otherwise, they need to create a new subscription. Apps can also unsubscribe at any time to stop getting change notifications.

The following table shows the maximum expiration times for subscriptions per resource in Microsoft Graph.

[!INCLUDE [change-notifications-subscription-lifetime](includes/change-notifications-subscription-lifetime.md)]

### Manage subscriptions for different delivery channels

<<<<<<< HEAD
1. The Microsoft Graph sends a response back to the client.

The client must store the subscription ID to correlate change notifications with the subscription.

#### Subscription request example


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "change-notifications-subscriptions-example"
}-->
```http
POST https://graph.microsoft.com/v1.0/subscriptions
Content-Type: application/json

{
  "changeType": "created,updated",
  "notificationUrl": "https://webhook.azurewebsites.net/notificationClient",
  "resource": "/me/mailfolders('inbox')/messages",
  "expirationDateTime": "2016-03-20T11:00:00.0000000Z",
  "clientState": "SecretClientState"
}
```

# [Cli](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/change-notifications-subscriptions-example-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

The `changeType`, `notificationUrl`, `resource`, and `expirationDateTime` properties are required. See [subscription resource type](/graph/api/resources/subscription) for property definitions and values.

The `resource` property specifies the resource that will be monitored for changes. For example, you can create a subscription to a specific mail folder: `me/mailFolders('inbox')/messages` or on behalf of a user given by an administrator  consent: `users/john.doe@onmicrosoft.com/mailFolders('inbox')/messages`.

Although `clientState` is not required, you must include it to comply with our recommended change notification handling process. Setting this property will allow you to confirm that change notifications you receive originate from the Microsoft Graph service. For this reason, the value of the property should remain secret and known only to your application and the Microsoft Graph service.

If successful, Microsoft Graph returns a `201 Created` code and a [subscription](/graph/api/resources/subscription) object in the body.

> [!NOTE]
> Any query string parameter included in the **notificationUrl** property will be included in the HTTP POST request when notifications are being delivered.

#### Notification endpoint validation

Microsoft Graph validates the notification endpoint provided in the `notificationUrl` property of the subscription request before creating the subscription. The validation process occurs as follows:

1. Microsoft Graph encodes a validation token and includes it in a POST request to the notification URL:

    ``` http
    Content-Type: text/plain; charset=utf-8
    POST https://{notificationUrl}?validationToken={opaqueTokenCreatedByMicrosoftGraph}
    ```

1. The client must properly URL decode the `validationToken` query parameter provided in the preceding step, and escape any HTML/JavaScript.

   Escaping is a good practice because malicious actors can use the notification endpoint for cross-site scripting type of attacks.

   In general, treat the validation token value as opaque, as the token format can generally change without notice. Microsoft Graph never sends any value containing HTML or JavaScript code.

1. The client must provide a response with the following characteristics within 10 seconds of step 1:

    - A status code of `HTTP 200 OK`.
    - A content type of `text/plain`.
    - A body that includes the _URL decoded_ validation token. Simply reflect back the same string that was sent in the `validationToken` query parameter.

    The client should discard the validation token after providing it in the response.

    > [!IMPORTANT]
    > If the client returns an encoded validation token, the validation fails.

Additionally, you can use the [Microsoft Graph Postman collection](use-postman.md) to confirm that your endpoint properly implements the validation request. The **Subscription Validation** request in the **Misc** folder provides unit tests that validate the response provided by your endpoint.  

![validation response test results](images/change-notifications/validation-request-tests-results.png)

### Renewing a subscription

The client can renew a subscription with a specific expiration date of up to three days from the time of request. The `expirationDateTime` property is required.

#### Subscription renewal example


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "change-notifications-subscriptions-example-renewal"
}-->
```http
PATCH https://graph.microsoft.com/v1.0/subscriptions/{id}
Content-Type: application/json

{
  "expirationDateTime": "2016-03-22T11:00:00.0000000Z"
}
```

# [Cli](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/change-notifications-subscriptions-example-renewal-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

If successful, Microsoft Graph returns a `200 OK` code and a [subscription](/graph/api/resources/subscription) object in the body. The subscription object includes the new `expirationDateTime` value.

### Deleting a subscription

The client can stop receiving change notifications by deleting the subscription using its ID.


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "change-notifications-subscriptions-example-delete"
}-->
```http
DELETE https://graph.microsoft.com/v1.0/subscriptions/{id}
```

# [Cli](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/change-notifications-subscriptions-example-delete-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

If successful, Microsoft Graph returns a `204 No Content` code.

## Change notifications

With a client subscribing to changes to a resource, Microsoft Graph sends a `POST` request to the notification URL whenever the resource changes. It sends notifications only for changes of the type that's specified in the subscription, for example, `created`.

> [!NOTE]
> If a client has multiple subscriptions that monitor the same resource and use the same notification URL, Microsoft Graph can send multiple change notifications that correspond to different subscriptions, each showing the corresponding subscription ID. There is no guarantee that all change notifications in the `POST` request belong to a single subscription.

### Change notification example

This section shows an example of a notification for a message creation. When the user receives an email, Microsoft Graph sends a change notification as shown in the following example.
Note that the notification is in a collection represented in the `value` field. See [changeNotificationCollection](/graph/api/resources/changenotificationcollection) for details of the notification payload. 

When many changes occur, Microsoft Graph may send multiple notifications that correspond to different subscriptions in the same `POST` request.

```json
{
  "value": [
    {
      "id": "lsgTZMr9KwAAA",
      "subscriptionId":"{subscription_guid}",
      "subscriptionExpirationDateTime":"2016-03-19T22:11:09.952Z",
      "clientState":"secretClientValue",
      "changeType":"created",
      "resource":"users/{user_guid}@{tenant_guid}/messages/{long_id_string}",
      "tenantId": "84bd8158-6d4d-4958-8b9f-9d6445542f95",
      "resourceData":
      {
        "@odata.type":"#Microsoft.Graph.Message",
        "@odata.id":"Users/{user_guid}@{tenant_guid}/Messages/{long_id_string}",
        "@odata.etag":"W/\"CQAAABYAAADkrWGo7bouTKlsgTZMr9KwAAAUWRHf\"",
        "id":"{long_id_string}"
      }
    }
  ]
}
```

### Processing the change notification

Your process should process every change notification it receives. The following are the minimum tasks that your app must perform to process a change notification:

1. Your process should process every change notification it receives and send a 2xx class code. If Microsoft Graph doesn't receive a 2xx class code within 3 seconds, it will try to publish the change notification a number of times, for a period of about 4 hours; after that, the change notification will be dropped and won't be delivered. If your process consistently does not respond within 3 seconds, your notification might be subject to throttling.

    If your processing is expected to take more than 3 seconds, you should persist the notification, return a `202 - Accepted` status code in your response to Microsoft Graph, then process the notifications. If the notification is not persisted, return a 5xx class code to indicate an error so the notification will be retried.

    If your processing is expected to take less than 3 seconds, you should process the notifications and return a `200 - OK` status code in your response to Microsoft Graph. If the notification is not processes correctly, return a 5xx class code to indicate an error so the notification will be retried.

1. Validate the `clientState` property. It must match the value originally submitted with the subscription creation request.

    > [!NOTE]
    > If this isn't true, you should not consider this a valid change notification. It is possible that the change notification has not originated from Microsoft Graph and may have been sent by a rogue actor. You should also investigate where the change notification comes from and take appropriate action.

1. Update your application based on your business logic.

Repeat for other change notifications in the request.

### Throttling

Send a `202 - Accepted` status code as soon as you receive the change notification, even before validating its authenticity. You are simply acknowledging the receipt of the change notification and preventing unnecessary retries. For most subscriptions, notifications are not subjected to any additional delay during publishing and all notifications are delivered within the SLA unless the service is experiencing an incident. However, if a subscription notification URL is slow or fails to response, notifications might be throttled for the host associated with the subscription. The following process is used to determine when to throttle and how to handle throttled endpoints.

Notifications are published using an HTTP client with a 3 second timeout. Upon completion of publishing of a notification, regardless of outcome, the total time spent attempting to publish, including network latency, is tracked for the host associated with the notification URL. If the publishing time is greater than 2900 ms, the response is considered slow. The responses are accumulated for the host and the percentage of slow responses is calculated after 100 notifications have been received. When the percentage of slow responses reaches 10%, the host associated with the notification URL is flagged as a slow endpoint. Because slow endpoints are associated with the host in the notification URL, all notifications for all subscriptions associated with the host are considered for evaluation and are subjected to throttling.

The evaluation continues in real time. If the publishing time for a host drops below 290 0ms, this non-slow response is included in the total count of responses, the percentage of slow responses is re-calculated, and the endpoint is re-evaluated. Additionally, the accumulation of responses is flushed every 10 minutes and the evaluation starts again, waiting for 100 notifications before evaluating an endpoint. Therefore, a temporary spike in network latency or publishing delay will recover after the delay is mitigated. A more persistent network latency or publishing delay greater than 2900 ms will be continually re-evaluated every 10 minutes. 

While an endpoint is throttled, notifications are subjected to the following additional delays:
-	Notifications are automatically offloaded to a set of workers dedicated to failed and throttled notifications and an additional delay of 10 minutes is incurred.
-	Notifications are dropped if the throttled endpoint slow % is >= 15%.
-	Notifications that failed to deliver due to an unsuccessful HTTP call are retried again in 10 minutes.
=======
For more information about managing subscriptions for the different delivery channels using Microsoft Graph, see the following articles.
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b

- [Receive change notifications through webhooks](./change-notifications-delivery-webhooks.md).
- [Receive change notifications through Azure Event Hubs](./change-notifications-delivery-event-hubs.md).
- [Receive change notifications through Azure Event Grid](/azure/event-grid/subscribe-to-graph-api-events?context=graph%2Fcontext) (preview).

## Code samples

The following code samples are available on GitHub.

- [Microsoft Graph Training Module - Using Change Notifications and Track Changes with Microsoft Graph](https://github.com/microsoftgraph/msgraph-training-changenotifications)
- [Microsoft Graph Webhooks Sample for Node.js](https://github.com/microsoftgraph/nodejs-webhooks-rest-sample)
- [Microsoft Graph Webhooks Sample for ASP.NET Core](https://github.com/microsoftgraph/aspnetcore-webhooks-sample)
- [Microsoft Graph Webhooks Sample for Java Spring](https://github.com/microsoftgraph/java-spring-webhooks-sample)

## Latency

[!INCLUDE [change-notifications-delivery-latency](includes/change-notifications-delivery-latency.md)]

## Deployment resources

- [Get change notifications through webhooks](./change-notifications-delivery-webhooks.md)
- [Get change notifications through Azure Event Hubs](./change-notifications-delivery-event-hubs.md)
- [Get change notifications through Azure Event Grid](/azure/event-grid/subscribe-to-graph-api-events?context=graph%2Fcontext)
- [Rich notifications (notifications with resource data)](./webhooks-with-resource-data.md)
- [Lifecycle notifications](./webhooks-lifecycle.md)
- Tutorials
    - [Change notifications for cloud printing](./universal-print-webhook-notifications.md)
    - [Change notifications for Outlook resources](./outlook-change-notifications-overview.md)
    - [Change notifications for Microsoft Teams resources](./teams-change-notification-in-microsoft-teams-overview.md)

## See also

- [Training: Use change notifications and track changes with Microsoft Graph](/training/modules/msgraph-changenotifications-trackchanges)

[contact]: /graph/api/resources/contact
[conversation]: /graph/api/resources/conversation
[driveItem]: /graph/api/resources/driveitem
[event]: /graph/api/resources/event
[group]: /graph/api/resources/group
[message]: /graph/api/resources/message
[user]: /graph/api/resources/user
[alert]: /graph/api/resources/alert
[callRecord]: /graph/api/resources/callrecords-callrecord
[presence]: /graph/api/resources/presence
[chatMessage]: /graph/api/resources/chatmessage
[list]: /graph/api/resources/list
[printer]: /graph/api/resources/printer
[printTaskDefinition]: /graph/api/resources/printtaskdefinition
[todoTask]: /graph/api/resources/todotask
[channel]: /graph/api/resources/channel
[chat]: /graph/api/resources/chat
[conversationMember]: /graph/api/resources/conversationmember
[team]: /graph/api/resources/team
[onlineMeeting]: /graph/api/resources/onlinemeeting
