---
title: "Update governanceRoleAssignmentRequests"
description: "Enable administrators to update their decisions (`AdminApproved` or `AdminDenied`) on governanceRoleAssignmentRequests that are in status of `PendingAdminDecision`."
ms.localizationpriority: medium
doc_type: apiPageType
ms.prod: "governance"
author: "rkarim-ms"
---

# Update governanceRoleAssignmentRequests

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

[!INCLUDE [pim-v2ResourceRoles-deprecation](../../includes/pim-v2ResourceRoles-deprecation.md)]

Enable administrators to update their decisions (`AdminApproved` or `AdminDenied`) on [governanceRoleAssignmentRequests](../resources/governanceroleassignmentrequest.md) that are in status of `PendingAdminDecision`.

## Permissions

The following table shows the least privileged permission or permissions required to call this API on each supported resource type. Follow [best practices](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions) to request least privileged permissions. For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

| Supported resource | Delegated (work or school account) | Delegated (personal Microsoft account) | Application |
|:-|:-|:-|:-|
| Azure AD | PrivilegedAccess.ReadWrite.AzureAD | Not supported. | Not supported. |
| Azure resources | PrivilegedAccess.ReadWrite.AzureResources | Not supported. | Not supported. |
| [group](../resources/group.md) | PrivilegedAccess.ReadWrite.AzureADGroup | Not supported. | Not supported. |

The requester must also have at least one active administrator role assignment (`owner` or `user access administrator`) on the resource that the [governanceRoleAssignmentRequest](../resources/governanceroleassignmentrequest.md) belongs to.

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /privilegedAccess/azureResources/roleAssignmentRequests/{id}/updateRequest   
```

## Request headers
| Name           | Description|
|:---------------|:----------|
| Authorization  | Bearer {code}|
| Content-type  | application/json|

## Request body

|Parameters	     |Type	                 |Required |Description|
|:-------------|:----------------------|:--------|:----------|
|reason        |String                 |✓        |The reason provided by the administrator for his decision.|
|decision        |String                 |✓        |The administrator decision of the role assignment request. The value should be updated as `AdminApproved` or `AdminDenied`.|
|schedule      |[governanceSchedule](../resources/governanceschedule.md)|        | The schedule of the role assignment request. For status of `AdminApproved`, it is required.|
|assignmentState      |String|         | The state of assignment, and the values can be `Eligible` or `Active`. For decision of `AdminApproved`, it is required. |
### Response
This method can only be applied to requests that are in status of `PendingAdminDecision`.

If successful, this method returns a `204 No Content` response code. It does not return anything in the response body.

## Example
##### Request

<!-- {
  "blockType": "request",
  "name": "updaterequest_governanceroleassignmentrequest"
}-->
```http
POST https://graph.microsoft.com/beta/privilegedAccess/azureResources/roleAssignmentRequests/7c53453e-d5a4-41e0-8eb1-32d5ec8bfdee/updateRequest
```

<<<<<<< HEAD
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/updaterequest-governanceroleassignmentrequest-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
##### Request body

```json
{
  "reason":"approve the request to extend role assignment",
  "schedule":{
    "type":"Once",
    "startDateTime":"2018-02-20T07:31:13.451Z",
    "stopDateTime":"2018-05-21T07:31:13.451Z",
    },
  "decision":"AdminApproved",
  "assignmentState": "Eligible"
}
```

##### Response
<!-- {
  "blockType": "response"
} -->
```http
HTTP/1.1 204 No Content
```


<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "UpdateRequest governanceRoleAssignmentRequest",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->


