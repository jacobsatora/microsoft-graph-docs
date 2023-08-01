---
title: "Update adminReportSettings"
description: "Update tenant-level settings for Microsoft 365 reports."
ms.localizationpriority: medium
author: "qiwhuang"
ms.prod: "reports"
doc_type: apiPageType
---

# Update adminReportSettings

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update tenant-level settings for Microsoft 365 reports.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|----------------------------------------|---------------------------------------------|
| Delegated (work or school account)     | ReportSettings.ReadWrite.All                |
| Delegated (personal Microsoft account) | Not supported.                              |
| Application                            | ReportSettings.ReadWrite.All                |

> **Note:** For delegated permissions to allow apps to update report settings on behalf of a user, the tenant administrator must have assigned the user the appropriate Azure Active Directory limited administrator role. For more details, see [Authorization for APIs to read Microsoft 365 usage reports](/graph/reportroot-authorization).

## HTTP request
<!-- { "blockType": "ignored" } --> 
```http
PATCH /admin/reportSettings
```

## Request headers

| Name          | Description                |
| :------------ | :--------------------------|
| Authorization | Bearer {token}. Required.  |
| Content-Type  | application/json. Required.|

## Request body

[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]

| Property       | Type           | Description                                 |
| -------------- | -------------- | ------------------------------------------- |
| displayConcealedNames | Boolean | If set to `true`, all reports will conceal user information such as usernames, groups, and sites. If `false`, all reports will show identifiable information. This property represents a setting in the Microsoft 365 admin center. Required. |

## Response

If successful, this method returns a `204 No Content` response code.

## Examples

The following is an example of a request that updates a tenant-level setting for Microsoft 365 reports.

### Request
The following is an example of a request.

<!-- {
  "blockType": "request",
  "name": "update_adminreportsettings"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/admin/reportSettings
Content-Type: application/json
Content-length: 37

{
  "displayConcealedNames": true
}
```

<<<<<<< HEAD
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/update-adminreportsettings-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
### Response

The following is an example of the response.

<!-- {
  "blockType": "response"
} -->
```http
HTTP/1.1 204 No Content
```
