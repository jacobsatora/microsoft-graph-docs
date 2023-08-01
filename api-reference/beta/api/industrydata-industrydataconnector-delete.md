---
title: "Delete industryDataConnector"
description: "Delete an industryDataConnector object."
author: "mlafleur"
ms.localizationpriority: medium
ms.prod: "industry-data-etl"
doc_type: apiPageType
---

# Delete industryDataConnector

Namespace: microsoft.graph.industryData

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Delete an [industryDataConnector](../resources/industrydata-industrydataconnector.md) object.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
| :------------------------------------- | :------------------------------------------ |
| Delegated (work or school account)     | IndustryData-DataConnector.ReadWrite.All    |
| Delegated (personal Microsoft account) | Not supported.                              |
| Application                            | IndustryData-DataConnector.ReadWrite.All    |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

```http
DELETE /external/industryData/dataConnectors/{industryDataConnectorId}
```

## Request headers

| Name          | Description               |
| :------------ | :------------------------ |
| Authorization | Bearer {token}. Required. |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `204 No Content` response code.

## Examples

### Request

The following is an example of a request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "delete_azuredatalakeconnector",
  "sampleKeys": ["8c010e87-c28b-4350-bdc1-65ec29258b93"]
}
-->

```http
DELETE https://graph.microsoft.com/beta/external/industryData/dataConnectors/8c010e87-c28b-4350-bdc1-65ec29258b93
```

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/delete-azuredatalakeconnector-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

The following is an example of the response.

<!-- {
  "blockType": "response",
  "truncated": true
}
-->

```http
HTTP/1.1 204 No Content
```
