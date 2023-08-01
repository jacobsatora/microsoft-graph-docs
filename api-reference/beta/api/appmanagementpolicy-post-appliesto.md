---
title: "Assign appliesTo"
description: "Assign a policy to application or service principal object."
ms.localizationpriority: medium
author: "madansr7"
ms.prod: "identity-and-sign-in"
doc_type: "apiPageType"
---

# Assign appliesTo

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Assign an [appManagementPolicy](../resources/appManagementPolicy.md) policy object to an application or service principal object. The application or service principal adopts this policy over the tenant-wide [tenantAppManagementPolicy](../resources/tenantappmanagementpolicy.md) setting. Only one policy object can be assigned to an application or service principal.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

<!-- { "blockType": "ignored"  } // Note: Removing this line will result in the permissions autogeneration tool overwriting the table. -->
| Permission type                        | Permissions (from least to most privileged)                        |
| :------------------------------------- | :----------------------------------------------------------------- |
| Delegated (work or school account)     | Application.Read.All and Policy.ReadWrite.ApplicationConfiguration |
| Delegated (personal Microsoft account) | Not supported.                                                     |
| Application                            | Application.Read.All and Policy.ReadWrite.ApplicationConfiguration |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
POST /applications/{id}/appManagementPolicies/$ref
```

## Request headers

| Name          | Description                 |
| :------------ | :-------------------------- |
| Authorization | Bearer {token}. Required.   |
| Content-Type  | application/json. Required. |

## Request body

In the request body, provide a reference to a single policy object from the [appManagementPolicies](../resources/appmanagementpolicy.md) collection.

## Response

If successful, this method returns `204 No Content` response code. It does not return anything in the response body.

## Examples

### Example 1: Assign an appManagementPolicy to an application object

#### Request

The following is an example of the request to assign an appManagementPolicy to an application.


<!-- {
  "blockType": "request",
  "name": "ApplicationsAppManagementPolicies"
}-->

```http
POST https://graph.microsoft.com/beta/applications/{id}/appManagementPolicies/$ref
Content-type: application/json

{
 "@odata.id":"https://graph.microsoft.com/beta/policies/appManagementPolicies/{id}"
}
```

<<<<<<< HEAD
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/applicationsappmanagementpolicies-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
#### Response


The following is an example of the response.

<!-- {
  "blockType": "response",
  "truncated": true
} -->

```http
HTTP/1.1 204 No Content
```

### Example 2: Assign an appManagementPolicy to a service principal object

#### Request

The following is an example of the request to assign an appManagementPolicy to a service principal.



<!-- {
  "blockType": "request",
  "name": "servicePrincipals_appManagementPolicy"
}-->

``` http
POST https://graph.microsoft.com/beta/servicePrincipals/{id}/appManagementPolicies/$ref

{
 "@odata.id":"https://graph.microsoft.com/beta/policies/appManagementPolicies/{id}"
}
```

#### Response

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
  "description": "list resources for appManagementPolicies",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
