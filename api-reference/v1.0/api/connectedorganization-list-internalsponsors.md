---
title: "List internalSponsors"
description: "Retrieve a list of connectedOrganization's internalSponsors."
author: "markwahl-msft"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: apiPageType
---
# List internalSponsors

Namespace: microsoft.graph


Retrieve a list of a [connectedOrganization](../resources/connectedorganization.md)'s internal sponsors.  The [internal sponsors](../resources/internalsponsors.md) are a set of users who can approve requests on behalf of other users from that connected organization.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
| Delegated (work or school account)     | EntitlementManagement.Read.All, EntitlementManagement.ReadWrite.All |
| Delegated (personal Microsoft account) | Not supported. |
| Application                            | EntitlementManagement.Read.All, EntitlementManagement.ReadWrite.All |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /identityGovernance/entitlementManagement/connectedOrganizations/{id}/internalSponsors
```
## Optional query parameters

This method supports the [OData query parameters](/graph/query-parameters) for paging.

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [directoryObject](../resources/directoryobject.md) objects in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "list_directoryobject_internalsponsors"
}
-->
``` http
GET https://graph.microsoft.com/v1.0/identityGovernance/entitlementManagement/assignments/{accessPackageAssignmentId}/target/connectedOrganization/internalSponsors
```

<<<<<<< HEAD


=======
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.directoryObject)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.directoryObject",
      "id": "60dffb62-fb62-60df-62fb-df6062fbdf60"
    }
  ]
}
```


