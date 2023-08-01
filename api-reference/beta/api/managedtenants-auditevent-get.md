---
title: "Get auditEvent"
description: "Read the properties and relationships of an auditEvent object."
author: "vkumar2015"
ms.localizationpriority: medium
ms.prod: "multi-tenant-management"
doc_type: apiPageType
---

# Get auditEvent
Namespace: microsoft.graph.managedTenants

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read the properties and relationships of an [auditEvent](../resources/managedtenants-auditevent.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|ManagedTenant.Read.All, ManagedTenant.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /tenantRelationships/managedTenants/auditEvents/{auditEventId}
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

If successful, this method returns a `200 OK` response code and an [auditEvent](../resources/managedtenants-auditevent.md) object in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "get_auditevent"
}
-->
``` http
GET https://graph.microsoft.com/beta/tenantRelationships/managedTenants/auditEvents/{auditEventId}
```

<<<<<<< HEAD
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-auditevent-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.managedTenants.auditEvent"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
      "id": "c3b0d319-9913-bd52-7376-1125f0594129",
      "activityDateTime": "2021-12-21T16:48:23.0330765Z",
      "activityId": "64be6675-3cb8-4b14-95f3-6d5ce9eecd79",
      "initiatedByAppId": "00000003-0000-0000-c000-000000000000",
      "initiatedByUpn": "meganb@contoso.onmicrosoft.com",
      "category": "Baselines",
      "activity": "/managementActionTenantDeploymentStatuses/microsoft.graph.managedTenants.changeDeploymentStatus",
      "httpVerb": "POST",
      "path": "/managementActionTenantDeploymentStatuses/microsoft.graph.managedTenants.changeDeploymentStatus",
      "url": "https://graph.microsoft.com/managementActionTenantDeploymentStatuses/microsoft.graph.managedTenants.changeDeploymentStatus",
      "requestBody": ""
}
```

