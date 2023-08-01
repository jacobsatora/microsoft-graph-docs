---
title: "Update attributeSet"
description: "Update the properties of an attributeSet object."
author: "rolyon"
ms.localizationpriority: medium
ms.prod: "directory-management"
doc_type: apiPageType
---

# Update attributeSet

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of an [attributeSet](../resources/attributeset.md) object.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|CustomSecAttributeDefinition.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|CustomSecAttributeDefinition.ReadWrite.All|

[!INCLUDE [rbac-customsecurityattibutes-apis-write](../includes/rbac-for-apis/rbac-customsecurityattibutes-apis-write.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /directory/attributeSets/{attributeSetId}
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body

[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]

|Property|Type|Description|
|:---|:---|:---|
|description|String|Description of the attribute set. Can be up to 128 characters long and include Unicode characters. Optional.|
|maxAttributesPerSet|Int32|Maximum number of custom security attributes that can be defined in this attribute set. Default value is `null`. If not specified, the administrator can add up to the maximum of 500 active attributes per tenant. Optional.|

## Response

If successful, this method returns a `204 No Content` response code.

## Examples

### Request

The following example updates the description and the maximum number of attributes for an attribute set named `Engineering`.

<<<<<<< HEAD
#### Request

=======
# [HTTP](#tab/http)
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
<!-- {
  "blockType": "request",
  "name": "update_attributeset",
  "sampleKeys": ["Engineering"]
}
-->
``` http
PATCH https://graph.microsoft.com/beta/directory/attributeSets/Engineering
Content-Type: application/json
Content-length: 119

{
    "description":"Attributes for engineering team",
    "maxAttributesPerSet":20
}
```

<<<<<<< HEAD
#### Response
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/update-attributeset-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

The following is an example of the response.
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b

<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```
