---
title: "Remove tokenLifetimePolicy"
description: "Remove a tokenLifetimePolicy from an application or servicePrincipal."
ms.localizationpriority: medium
author: "sureshja"
ms.prod: "applications"
doc_type: "apiPageType"
---

# Remove tokenLifetimePolicy

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Remove a [tokenLifetimePolicy](../resources/tokenlifetimepolicy.md) from an [application](../resources/application.md) or [servicePrincipal](../resources/servicePrincipal.md).

## Permissions

One of the following sets of permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

<!-- { "blockType": "ignored"  } // Note: Removing this line will result in the permissions autogeneration tool overwriting the table. -->
| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | Policy.Read.All and Application.ReadWrite.All, Policy.ReadWrite.ApplicationConfiguration and Application.ReadWrite.All |
| Delegated (personal Microsoft account) | Not supported. |
| Application                            | Policy.Read.All and Application.ReadWrite.OwnedBy, Policy.Read.All and Application.ReadWrite.All, Policy.ReadWrite.ApplicationConfiguration and Application.ReadWrite.OwnedBy, Policy.ReadWrite.ApplicationConfiguration and Application.ReadWrite.All |

## HTTP request

Token lifetime policies can be assigned to both applications and service principals.

You can address the application using either its **id** or **appId**. **id** and **appId** are referred to as the **Object ID** and **Application (Client) ID**, respectively, in the Azure portal.

<!-- { "blockType": "ignored" } -->
```http
DELETE /applications/{applicationObjectId}/tokenLifetimePolicies/{tokenLifetimePolicyId}/$ref

DELETE /applications(appId='{appId}')/tokenLifetimePolicies/{tokenLifetimePolicyId}/$ref

DELETE /servicePrincipals/{servicePrincipalObjectId}/tokenLifetimePolicies/{tokenLifetimePolicyId}/$ref

DELETE /servicePrincipals(appId='{appId}')/tokenLifetimePolicies/{tokenLifetimePolicyId}/$ref
```

## Request headers

| Name          | Description   |
|:--------------|:--------------|
| Authorization | Bearer {token} |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns `204 No Content` response code.

## Examples

### Request

The following is an example of the request.

<!-- {
  "blockType": "request",
  "name": "delete_tokenlifetimepolicy_from_application"
}-->

```http
DELETE https://graph.microsoft.com/beta/applications/3ccc9971-9ae7-45d6-8de8-263fd25fe116/tokenLifetimePolicies/4d2f137b-e8a9-46da-a5c3-cc85b2b840a4/$ref
```

<<<<<<< HEAD
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/delete-tokenlifetimepolicy-from-application-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
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
  "description": "Remove tokenLifetimePolicy",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->



