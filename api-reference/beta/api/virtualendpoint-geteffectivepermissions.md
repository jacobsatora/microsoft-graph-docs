---
title: "virtualEndpoint: getEffectivePermissions"
description: "Get the effective permissions of the currently authenticated user."
author: "AshleyYangSZ"
ms.localizationpriority: medium
ms.prod: "cloud-pc"
doc_type: apiPageType
---

# virtualEndpoint: getEffectivePermissions

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get the effective permissions of the currently authenticated user, helping UX hide or disable content that the current user doesn't have access to.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|CloudPC.Read.All, CloudPC.ReadWrite.All|
|Delegated (personal Microsoft account) | Not supported.|
|Application| Not supported.|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

``` http
GET /deviceManagement/virtualEndpoint/getEffectivePermissions
```

## Request headers

| Name          | Description               |
| :------------ | :------------------------ |
| Authorization | Bearer {token}. Required. |

## Request body

Do not supply a request body for this method.

## Response

If successful, this function returns a `200 OK` response code and a String collection in the response body. If the user has full permissions, the response is `["*"]`.

## Examples

### Request

The following is an example of the request.

<!-- {
  "blockType": "request",
  "name": "virtualendpoint_geteffectivepermissions"
}
-->

``` http
GET https://graph.microsoft.com/beta/deviceManagement/virtualEndpoint/getEffectivePermissions
```

<<<<<<< HEAD
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/virtualendpoint-geteffectivepermissions-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(Edm.String)"
}
-->

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
   "value":[
      "Microsoft.CloudPC/CloudPCs/Read"
   ]
}
```
