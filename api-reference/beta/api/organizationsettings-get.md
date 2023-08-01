---
title: "Get organizationSettings"
description: "Retrieve the properties and relationships of organizationSettings object."
ms.localizationpriority: medium
author: "kevinbellinger"
ms.prod: "people"
doc_type: "apiPageType"
---

# Get organizationSettings

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve the properties and relationships of an [organizationSettings](../resources/organizationsettings.md) object, including **profileCardProperties**.

This operation does not return [insightsSettings](../resources/insightssettings.md). Depending on the type of insights, you can get their settings by using [list itemInsights](organizationsettings-list-iteminsights.md) or [list peopleInsights](organizationsettings-list-peopleinsights.md).

This operation does not return [microsoftApplicationDataAccessSettings](../resources/microsoftApplicationDataAccessSettings.md). To get [microsoftApplicationDataAccessSettings](../resources/microsoftApplicationDataAccessSettings.md), use [list microsoftApplicationDataAccessSettings](organizationsettings-list-microsoftapplicationdataaccess.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | User.Read, User.Read.All                    |
| Delegated (personal Microsoft account) | Not supported.                              |
| Application                            | Not supported.                              |

>**Note:** Using delegated permissions for this operation requires the signed-in user to have a tenant administrator or global administrator role.

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
GET /organization/{organizationId}/settings
```

## Optional query parameters

This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

| Name          |Description                  |
|:--------------|:----------------------------|
| Authorization | Bearer {token}. Required.   |
| Content-Type  | application/json. Required. |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and the requested [organizationSettings](../resources/organizationsettings.md) object in the response body.

## Examples

### Request

The following is an example of the request.

<!-- {
  "blockType": "request",
  "sampleKeys": ["a9f3c90b-04fd-4504-a302-47672bbca6c8"],
  "name": "get_organizationsettings"
}-->

```msgraph-interactive
GET https://graph.microsoft.com/beta/organization/a9f3c90b-04fd-4504-a302-47672bbca6c8/settings
```

<<<<<<< HEAD
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-organizationsettings-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.organizationSettings"
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#organization('a9f3c90b-04fd-4504-a302-47672bbca6c8')/settings/$entity",
    "id": "",
    "profileCardProperties": [
      {
        "directoryPropertyName": "CustomAttribute1",
        "annotations": [
          {
            "displayName": "Cost Center",
            "localizations": [
              {
                "languageTag": "ru-RU",
                "displayName": "центр затрат"
  }
            ]
          }
        ]
      }
    ]
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Get organizationSettings",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
