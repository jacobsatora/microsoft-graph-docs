---
title: "Create permission"
description: "Create a new permission object."
author: "BarrySh"
ms.localizationpriority: medium
ms.prod: "sharepoint"
doc_type: apiPageType
---

# Create permission
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create a new [permission](../resources/permission.md) object on a site.

>**Note:** You can only use this method to create a new application permission; you can't use it to create a new user site permission.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | Not supported.                              |
| Delegated (personal Microsoft account) | Not supported.                              |
| Application                            | Sites.FullControl.All                       |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /sites/{sitesId}/permissions
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [permission](../resources/permission.md) object.

## Response

If successful, this method returns a `201 Created` response code and a [permission](../resources/permission.md) object in the response body.

## Examples

### Request

<<<<<<< HEAD
=======
The following is an example of a request.

# [HTTP](#tab/http)
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
<!-- {
  "blockType": "request",
  "name": "create_permission_from_"
}
-->
``` http
POST https://graph.microsoft.com/beta/sites/f2d90359-865b-4b6c-8848-d2722dd630e5/permissions
Content-Type: application/json

{
  "roles": [
    "write"
  ],
  "grantedToIdentities": [
    {
      "application": {
        "id": "89ea5c94-7736-4e25-95ad-3fa95f62b66e",
        "displayName": "Contoso Time Manager App"
      }
    }
  ]
}
```

<<<<<<< HEAD
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/create-permission-from--cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
### Response

The following is an example of the response.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.permission"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "id": "1",
  "@deprecated.GrantedToIdentities": "GrantedToIdentities has been deprecated. Refer to GrantedToIdentitiesV2",
  "roles": [
    "write"
  ],
  "grantedToIdentities": [
    {
      "application": {
        "id": "89ea5c94-7736-4e25-95ad-3fa95f62b66e",
        "displayName": "Contoso Time Manager App"
      }
    }
  ],
  "grantedToIdentitiesV2": [
    {
      "application": {
        "id": "89ea5c94-7736-4e25-95ad-3fa95f62b66e",
        "displayName": "Contoso Time Manager App"
      }
    }
  ]
}
```

<!-- {
  "type": "#page.annotation",
  "section": "documentation",
  "tocPath": "Sites/Permissions/Create site permissions"
} -->
