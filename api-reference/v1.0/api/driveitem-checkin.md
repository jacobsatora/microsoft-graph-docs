---
author: learafa
description: "Check in a checked out driveItem resource, which makes the version of the document available to others."
title: "driveItem: checkin"
ms.localizationpriority: medium
ms.prod: "sharepoint"
doc_type: apiPageType
---
# driveItem: checkin

Namespace: microsoft.graph

Check in a checked out **driveItem** resource, which makes the version of the document available to others.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Files.ReadWrite, Files.ReadWrite.All, Sites.ReadWrite.All    |
|Delegated (personal Microsoft account) | Files.ReadWrite, Files.ReadWrite.All    |
|Application | Files.ReadWrite.All, Sites.ReadWrite.All |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
POST /drives/{driveId}/items/{itemId}/checkin
POST /groups/{groupId}/drive/items/{itemId}/checkin
POST /me/drive/items/{item-id}/checkin
POST /sites/{siteId}/drive/items/{itemId}/checkin
POST /users/{userId}/drive/items/{itemId}/checkin
```

## Request body

In the request body, provide a JSON object with the following parameters.


|   Name    | Value  |                                                Description                                                |
| :-------- | :----- | :-------------------------------------------------------------------------------------------------------- |
| checkInAs | string | Optional. The status of the document after the check-in operation is complete. Can be `published` or unspecified. |
| comment   | string | A check-in comment that is associated with the version.                                                   |

## Response

If successful, the API call returns `204 No content`.

## Example

This example checks in a file identified by `{item-id}`.

### Request

# [HTTP](#tab/http)
<!-- { "blockType": "request", "name": "checkin-item", "scopes": "files.readwrite", "target": "action" } -->

```http
POST /drives/{drive-id}/items/{item-id}/checkin
Content-Type: application/json

{
  "comment": "Updating the latest guidelines"
}
```

<<<<<<< HEAD
# [Cli](#tab/cli)
=======
# [CLI](#tab/cli)
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
[!INCLUDE [sample-code](../includes/snippets/cli/checkin-item-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

<!-- { "blockType": "response" } -->

```http
HTTP/1.1 204 No content
```

[item-resource]: ../resources/driveitem.md

<!--
{
  "type": "#page.annotation",
  "description": "Create a copy of an existing item.",
  "keywords": "copy existing item",
  "section": "documentation",
  "tocPath": "Items/Copy",
  "suppressions": [
  ]
}
-->

