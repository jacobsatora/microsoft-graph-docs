---
title: "Delete personAward"
description: "Deletes an personAward object."
ms.localizationpriority: medium
author: "kevinbellinger"
ms.prod: "people"
doc_type: apiPageType
---

# Delete personAward

Namespace: microsoft.graph

Deletes a [personAward](../resources/personaward.md) object from a user's [profile](../resources/profile.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged)                                      |
|:---------------------------------------|:---------------------------------------------------------------------------------|
| Delegated (work or school account)     | User.ReadWrite, User.ReadWrite.All |
| Delegated (personal Microsoft account) | User.ReadWrite, User.ReadWrite.All |
| Application                            | User.ReadWrite.All                            |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
DELETE /me/profile/awards/{id}
DELETE /users/{id | userPrincipalName}/profile/awards/{id}
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `204 No Content` response code.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "delete_personaward"
}
-->
``` http
DELETE https://graph.microsoft.com/beta/users/{userId}/profile/awards/{personAwardId}
```

<<<<<<< HEAD
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/delete-personaward-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
### Response


<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```


