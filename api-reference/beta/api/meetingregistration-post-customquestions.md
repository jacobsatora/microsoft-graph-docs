---
title: "Create meetingRegistrationQuestion"
description: "Create a custom meeting registration question associated with a meetingRegistration object."
author: "awang119"
ms.localizationpriority: medium
ms.prod: "cloud-communications"
doc_type: apiPageType
---

# Create meetingRegistrationQuestion

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create a [custom registration question](../resources/meetingregistrationquestion.md) associated with a [meetingRegistration](../resources/meetingregistration.md) object on behalf of the organizer.

> [!TIP]
> You can create custom registration questions in line when you create a meeting registration. For details, see [Create meetingRegistration](meetingRegistration-post.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type | Permissions (from least to most privileged) |
|:----------------|:--------------------------------------------|
| Delegated (work or school account) | OnlineMeetings.ReadWrite |
| Delegated (personal Microsoft account) | Not supported. |
| Application | Not supported. |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /me/onlineMeetings/{id}/registration/microsoft.graph.meetingRegistration/customQuestions
```

> [!TIP]
> To access `/customQuestions`, follow the [example](#example) to cast the type of **registration** to **meetingRegistration**.

## Request headers

| Name            | Description               |
| :-------------- | :------------------------ |
| Authorization   | Bearer {token}. Required. |

## Request body

In the request body, supply a JSON representation of the writable properties of a [meetingRegistrationQuestion](../resources/meetingregistrationquestion.md) object.

## Response

If successful, this method returns a `201 Created` response code and a [meetingRegistrationQuestion](../resources/meetingregistrationquestion.md) object in the response body.

## Example

### Request


<!-- {
  "blockType": "request",
  "name": "create-custom-question",
  "sampleKeys": ["MSpkYzE3Njc0Yy04MWQ5LTRhZGItYmZ"]
}-->

```http
POST https://graph.microsoft.com/beta/me/onlineMeetings/MSpkYzE3Njc0Yy04MWQ5LTRhZGItYmZ/registration/microsoft.graph.meetingRegistration/customQuestions
Content-Type: application/json

{
  "displayName": "What's your job position?",
  "isRequired": false,
  "answerInputType": "text"
}
```

<<<<<<< HEAD

=======
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
### Response

> **Note**: The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "name": "create-custom-question",
  "@odata.type": "microsoft.graph.meetingRegistrationQuestion"
}-->

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#users('16664f75-11dc-4870-bec6-38c1aaa81431')/onlineMeetings('MSpkYzE3Njc0Yy04MWQ5LTRhZGItYmZ')/registration/microsoft.graph.meetingRegistration/customQuestions/$entity",
  "id": "MSNhYjc5NWI4MC119zX3gwMDIwX3lvdXJfeDAwMjBfam8=",
  "displayName": "What's your job position?",
  "isRequired": false,
  "answerInputType": "text",
  "answerOptions": []
}
```
