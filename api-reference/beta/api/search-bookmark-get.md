---
title: "Get bookmark"
description: "Read the properties and relationships of a bookmark object."
author: "jakeost-msft"
ms.localizationpriority: medium
ms.prod: "search"
doc_type: apiPageType
---

# Get bookmark
Namespace: microsoft.graph.search

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read the properties and relationships of a [bookmark](../resources/search-bookmark.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)| SearchConfiguration.Read.All, SearchConfiguration.ReadWrite.All |
|Delegated (personal Microsoft account)| Not supported. |
|Application| SearchConfiguration.Read.All, SearchConfiguration.ReadWrite.All |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /search/bookmarks/{bookmarksId}
```

## Optional query parameters
This method supports the `select`, `expand`, `filter`, `orderBy`, `maxTop`, and `count` [OData Query Parameters](/graph/query-parameters) to help customize the response.

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [bookmark](../resources/search-bookmark.md) object in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "get_bookmark"
}
-->
``` http
GET https://graph.microsoft.com/beta/search/bookmarks/{bookmarksId}
```

<<<<<<< HEAD
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-bookmark-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.search.bookmark"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": "733b26d5-af76-4eea-ac69-1a0ce8716897",
  "displayName": "Italy Holiday",
  "webUrl": "http://www.margiestravel.com/",
  "description": "Book a fancy vacation in Tuscany or browse museums in Florence.",
  "lastModifiedDateTime": "2016-03-21T20:01:37Z",
  "lastModifiedBy": {
    "user": {
        "id": "efee1b77-fb3b-4f65-99d6-274c11914d12",
        "displayName": "Amalie Larsen"
    }
  },
  "keywords":  {
    "keywords": ["Vacation in Europe", "Holiday in Europe"],
    "reservedKeywords": ["Vacation in Italy"],
    "matchSimilarKeywords": true
  },
  "categories": ["HR"],
  "availabilityStartDateTime": "2020-09-21T20:01:37Z",
  "availabilityEndDateTime": "2020-11-21T20:01:37Z",
  "languageTags": ["en-us"],
  "platforms": ["ios"],
  "groupIds": ["groupId"],
  "targetedVariations": null,
  "powerAppIds": ["powerAppId"],
  "state": "published",
  "isSuggested": false
}
```

