---
title: "Delete authenticationContextClassReference"
description: "Delete an authenticationContextClassReference object that's not published or used by a conditional access policy."
ms.localizationpriority: medium
author: "bakerCaleb"
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# Delete authenticationContextClassReference

Namespace: microsoft.graph

Delete an [authenticationContextClassReference](../resources/authenticationcontextclassreference.md) object that's not published or used by a conditional access policy.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type                        | Permissions (from least to most privileged)                                       |
|:--------------------------------------|:----------------------------------------------------------------------------------|
|Delegated (work or school account)     | Policy.Read.ConditionalAccess |
|Delegated (personal Microsoft account) | Not supported. |
|Application                            | Policy.Read.ConditionalAccess |

## HTTP request

<!-- { "blockType": "ignored" } -->
```http
DELETE /identity/conditionalAccess/authenticationContextClassReferences/{id}
```

## Request headers

| Name      |Description|
|:----------|:----------|
| Authorization | Bearer {token}. Required. |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `204 No Content` response code. It does not return anything in the response body.
This method will return a `403 Forbidden` error code when deleting a published authenticationContextClassReference (where **isAvailable** is set to `true`). If authenticationContextClassReference, though unpublished, is used by any Conditional Access policy, this method will return a `400 Bad Request` error code.

## Examples

### Request

The following is an example of the request.


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "delete_authenticationcontextclassreference",
  "sampleKeys": ["c1"]
}-->

```http
DELETE /identity/conditionalAccess/authenticationContextClassReferences/c1
```

<<<<<<< HEAD
# [Cli](#tab/cli)
=======
# [CLI](#tab/cli)
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
[!INCLUDE [sample-code](../includes/snippets/cli/delete-authenticationcontextclassreference-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

The following is an example of the response.

<!-- {
  "blockType": "response",
  "truncated": true
} -->

```http
HTTP/1.1 204 No Content
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Delete authenticationContextClassReference",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
