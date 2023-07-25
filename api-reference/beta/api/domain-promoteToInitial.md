---
title: "domain: promoteToInitial"
description: "Promotes secondary OnMicrosoft domain to initial."
author: "JamesNyamu"
localization_priority: Normal
ms.prod: "microsoft-identity-platform"
doc_type: apiPageType
---

# domain: promoteToInitial

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Promotes secondary `OnMicrosoft` domain to initial (primary).

> **Important:**
> Only applies to a verified  `OnMicrosoft` domain. This is a domain whose `isVerified` property of the [domain](../resources/domain.md) is true, has `MoeraDomain` value as part of the `supportedServices` collection and the `isInitial` property is set false. There can only be one primary OnMicrosoft domain per organization, and promoting to initial translates to an organizatio(tenant) wide rename of services such as Microsoft365 and MicrosoftAzure with the new primary OnMicrosoft domain prefix e.g,  `contoso.`**`onmicrosoft.com`** primary OnMicrosoft domain will reserve the namespace contoso.sharepoint.com for sharepoint services.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Domain.ReadWrite.All    |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Domain.ReadWrite.All |

## HTTP request

<!-- { "blockType": "ignored" } -->
```http
POST /domains/{id}/promoteToInitial
```

> For {id}, specify the domain with its fully qualified domain name.

## Request headers

| Name       | Description|
|:---------------|:----------|
| Authorization  | Bearer {token}. Required.|
| Content-Type  | application/json |

## Request body

## Response

If successful, this method returns `204 No content` response code.

## Example

##### Request

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "domain_promoteToInitial"
}-->
```http
POST https://graph.microsoft.com/beta/domains/contoso.com/promoteToInitial
```

##### Response
Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.domain"
} -->
```http
HTTP/1.1 204 No content
```
