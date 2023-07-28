---
author: JeremyKelley
ms.date: 09/10/2017
title: Share a file with a link
ms.localizationpriority: medium
ms.prod: "sharepoint"
description: "You can use createLink action to share a DriveItem via a sharing link."
doc_type: apiPageType
---
# Create a sharing link for a DriveItem

Namespace: microsoft.graph

You can use **createLink** action to share a [DriveItem](../resources/driveitem.md) via a sharing link.

The **createLink** action will create a new sharing link if the specified link type doesn't already exist for the calling application.
If a sharing link of the specified type already exists for the app, the existing sharing link will be returned.

DriveItem resources inherit sharing permissions from their ancestors.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Files.ReadWrite, Files.ReadWrite.All, Sites.ReadWrite.All    |
|Delegated (personal Microsoft account) | Files.ReadWrite, Files.ReadWrite.All    |
|Application | Files.ReadWrite.All, Sites.ReadWrite.All |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
POST /drives/{driveId}/items/{itemId}/createLink
POST /groups/{groupId}/drive/items/{itemId}/createLink
POST /me/drive/items/{itemId}/createLink
POST /sites/{siteId}/drive/items/{itemId}/createLink
POST /users/{userId}/drive/items/{itemId}/createLink
```

### Request body

The body of the request defines properties of the sharing link your application is requesting.
The request should be a JSON object with the following properties.

|   Name       |  Type  |                                 Description                                  |
| :------------| :----- | :--------------------------------------------------------------------------- |
| **type**     | string | The type of sharing link to create. Either `view`, `edit`, or `embed`.       |
| **password** | string | The password of the sharing link that is set by the creator. Optional and OneDrive Personal only.
| **expirationDateTime** | string | A String with format of yyyy-MM-ddTHH:mm:ssZ of DateTime indicates the expiration time of the permission. |
| **recipients** |[driveRecipient](../resources/driverecipient.md) collection|Optional. A collection of recipients who will receive access to the sharing link.|
| **retainInheritedPermissions** |  Boolean          | Optional. If `true` (default), any existing inherited permissions are retained on the shared item when sharing this item for the first time. If `false`, all existing permissions are removed when sharing for the first time.  |
| **scope** | string | Optional. The scope of link to create. Either `anonymous`, `organization`, or `users`. |
| **message** | string | Optional. A message sent to recipients in addition to the sharing link they receive when `sendNotification` is true and `recipients` are specified. This option is only available for files in OneDrive for Business and SharePoint. |
| **sendNotification** |Boolean|If `true`, this method sends a [sharing link](../resources/permission.md#sharing-links) in an email to users specified in `recipients`. Applicable to OneDrive for Business or SharePoint. The default value is `false`. Optional.|

### Link types

The following values are allowed for the **type** parameter.

| Type value | Description                                                                                  |
|:-----------|:---------------------------------------------------------------------------------------------|
| `view`     | Creates a read-only link to the DriveItem.                                                        |
| `review`         | Creates a review link to the **driveItem**. This option is only available for files in OneDrive for Business and SharePoint.                   |
| `edit`     | Creates a read-write link to the DriveItem.                                                       |
| `embed`    | Creates an embeddable link to the DriveItem. This option is only available for files in OneDrive personal. |
| `blocksDownload` | Creates a read-only link that blocks download to the **driveItem**. This option is only available for files in OneDrive for Business and SharePoint.  |
| `submitOnly`     | Creates an upload-only link to the **driveItem**. This option is only available for folders in OneDrive for Business and SharePoint.

### Scope types

The following values are allowed for the **scope** parameter.
If the **scope** parameter is not specified, the default link type for the organization is created.

| Value          | Description
|:---------------|:------------------------------------------------------------
| `anonymous`    | Anyone with the link has access, without needing to sign in. This may include people outside of your organization. Anonymous link support may be disabled by an administrator.
| `organization` | Anyone signed into your organization (tenant) can use the link to get access. Only available in OneDrive for Business and SharePoint.
| `users`        | Share only with people you choose inside or outside the organization.

## Response

If successful, this method returns a single [Permission](../resources/permission.md) resource in the response body that represents the requested sharing permissions.

The response will be `201 Created` if a new sharing link is created for the item or `200 OK` if an existing link is returned.

## Examples

### Example 1: Create an anonymous sharing link
The following example requests a sharing link to be created for the **driveItem** specified by {itemId} in the user's OneDrive.
The sharing link is configured to be read-only and usable by anyone with the link.
For OneDrive for Business and SharePoint users, use the `sendNotification` parameter to create a sharing link. The sharing link is then sent to recipients via email.
All existing permissions are removed when sharing for the first time if `retainInheritedPermissions` is false.

#### Request

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "driveItem_createlink"
}-->

```http
POST /me/drive/items/{itemId}/createLink
Content-Type: application/json

{
  "type": "view",
  "scope": "anonymous",
  "password": "String",
  "recipients": [
    {
      "@odata.type": "microsoft.graph.driveRecipient"
    }
  ],
  "sendNotification": true,
  "retainInheritedPermissions": false
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/driveitem-createlink-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/create-link-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/driveitem-createlink-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/create-link-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/create-link-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/driveitem-createlink-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/create-link-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/driveitem-createlink-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.permission"
}
-->

```http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "id": "123ABC",
  "roles": ["write"],
  "link": {
    "type": "view",
    "scope": "anonymous",
    "webUrl": "https://1drv.ms/A6913278E564460AA616C71B28AD6EB6",
    "application": {
      "id": "1234",
      "displayName": "Sample Application"
    },
  },
  "hasPassword": true
}
```

### Example 2: Creating company sharable links

OneDrive for Business and SharePoint support company sharable links.
These are similar to anonymous links, except they only work for members of the owning organization.
To create a company sharable link, use the **scope** parameter with a value of `organization`.

#### Request

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "create-link-scoped",
  "scopes": "files.readwrite service.sharepoint"
 } -->

```http
POST /me/drive/items/{item-id}/createLink
Content-Type: application/json

{
  "type": "edit",
  "scope": "organization"
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/create-link-scoped-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/create-link-scoped-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/create-link-scoped-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/create-link-scoped-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/create-link-scoped-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/create-link-scoped-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/create-link-scoped-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/create-link-scoped-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

<!-- { "blockType": "response", "@odata.type": "microsoft.graph.permission" } -->

```http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "id": "123ABC",
  "roles": ["write"],
  "link": {
    "type": "edit",
    "scope": "organization",
    "webUrl": "https://contoso-my.sharepoint.com/personal/ellen_contoso_com/...",
    "application": {
      "id": "1234",
      "displayName": "Sample Application"
    },
  }
}
```

### Example 3: Creating embeddable links

When using the `embed` link type, the webUrl returned can be embedded in an `<iframe>` HTML element.
When an embed link is created, the `webHtml` property contains the HTML code for an `<iframe>` to host the content.

>**Note:** Embed links are only supported for OneDrive personal.

#### Request

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "create-embedded-link",
  "scopes": "files.readwrite service.onedrive"
} -->

```http
POST /me/drive/items/{item-id}/createLink
Content-Type: application/json

{
  "type": "embed"
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/create-embedded-link-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/create-embedded-link-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/create-embedded-link-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/create-embedded-link-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/create-embedded-link-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/create-embedded-link-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/create-embedded-link-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/create-embedded-link-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

<!-- { "blockType": "response", "@odata.type": "microsoft.graph.permission" } -->

```http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "id": "123ABC",
  "roles": ["read"],
  "link": {
    "type": "embed",
    "webHtml": "<IFRAME src=\"https://onedrive.live.com/...\"></IFRAME>",
    "webUrl": "https://onedive.live.com/...",
    "application": {
      "id": "1234",
      "displayName": "Sample Application"
    },
  }
}
```

## Remarks

* Links created using this action do not expire unless a default expiration policy is enforced for the organization.
* Links are visible in the sharing permissions for the item and can be removed by an owner of the item.
* Links always point to the current version of a item unless the item is checked out (SharePoint only).

<!-- {
  "type": "#page.annotation",
  "description": "Create a new sharing link for an item.",
  "keywords": "create,sharing,sharing link",
  "section": "documentation",
  "tocPath": "Sharing/Create link",
  "suppressions": [
  ]
} -->

