---
title: "Get cloudPcCrossCloudGovernmentOrganizationMapping"
description: "Read the properties and relationships of a cloudPcCrossCloudGovernmentOrganizationMapping object."
author: "GuojMS"
ms.localizationpriority: medium
ms.prod: "cloud-pc"
doc_type: apiPageType
---

# Get cloudPcCrossCloudGovernmentOrganizationMapping
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read the properties and relationships of a [cloudPcCrossCloudGovernmentOrganizationMapping](../resources/cloudpccrosscloudgovernmentorganizationmapping.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|CloudPC.Read.All, CloudPC.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /deviceManagement/virtualEndpoint/crossCloudGovernmentOrganizationMapping
```

## Optional query parameters
This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [cloudPcCrossCloudGovernmentOrganizationMapping](../resources/cloudpccrosscloudgovernmentorganizationmapping.md) object in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "get_cloudpccrosscloudgovernmentorganizationmapping"
}
-->
``` http
GET https://graph.microsoft.com/beta/deviceManagement/virtualEndpoint/crossCloudGovernmentOrganizationMapping
```

<<<<<<< HEAD
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-cloudpccrosscloudgovernmentorganizationmapping-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
### Response
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.cloudPcCrossCloudGovernmentOrganizationMapping"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.cloudPcCrossCloudGovernmentOrganizationMapping",
    "id": "7e6e7d5b-8dd5-5078-16cf-d1e488be48a8",
    "organizationIdsInUSGovCloud": [
      "String"
    ]
  }
}
```

