---
title: "List resourceNamespaces"
description: "Get a list of the unifiedRbacResourceNamespace objects and their properties."
author: "DougKirschner"
ms.localizationpriority: medium
ms.prod: "directory-management"
doc_type: apiPageType
---

# List resourceNamespaces
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [unifiedRbacResourceNamespace](../resources/unifiedrbacresourcenamespace.md) objects and their properties.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|RoleManagement.Read.Directory, RoleManagement.Read.All, RoleManagement.ReadWrite.Directory|
|Delegated (personal Microsoft account)|Not supported.|
|Application|RoleManagement.Read.Directory, RoleManagement.Read.All, RoleManagement.ReadWrite.Directory|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /roleManagement/directory/resourceNamespaces
```

## Optional query parameters
This method supports the `$filter` and `$select` OData query parameters to help customize the response. This method supports `$filter` for **id** and **name**. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [unifiedRbacResourceNamespace](../resources/unifiedrbacresourcenamespace.md) objects in the response body.

## Examples

The following example gets all resource namespaces.

### Request

<!-- {
  "blockType": "request",
  "name": "list_unifiedrbacresourcenamespace"
}
-->
``` http
GET https://graph.microsoft.com/beta/roleManagement/directory/resourceNamespaces
```

<<<<<<< HEAD
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/list-unifiedrbacresourcenamespace-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
### Response
>**Note:** The response object shown here has been shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.unifiedRbacResourceNamespace)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#roleManagement/directory/resourceNamespaces",
    "value": [
        {
            "id": "microsoft.aad.b2c",
            "name": "microsoft.aad.b2c"
        },
        {
            "id": "microsoft.aad.cloudAppSecurity",
            "name": "microsoft.aad.cloudAppSecurity"
        },
        {
            "id": "microsoft.directory",
            "name": "microsoft.directory"
        }
    ]
}
```
