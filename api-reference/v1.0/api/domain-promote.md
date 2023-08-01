---
title: "domain: promote"
description: "Promote a verified subdomain to the root domain."
author: "adimitui"
ms.localizationpriority: medium
ms.prod: "directory-management"
doc_type: apiPageType
---

# domain: promote

Namespace: microsoft.graph

Promote a verified subdomain to the root domain. A verified domain has its **isVerified** property set to `true`.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions  |
|:--------------------|:-------------|
|Delegated (work or school account) | Domain.ReadWrite.All |
|Delegated (personal Microsoft account) | Not supported. |
|Application | Domain.ReadWrite.All |

The work or school account needs to belong to one of the following roles:

* Global Administrator
* Domain Name Administrator
* Partner Tier2 Support

## HTTP request

<!-- { "blockType": "ignored" } -->
```http
POST /domains/{id}/promote
```

> For {id}, specify the domain with its fully qualified domain name.

## Request headers

| Name       | Description|
|:---------------|:----------|
| Authorization  | Bearer {token}. Required.|
| Content-Type  | application/json |

## Request body

## Response

If successful, this call returns a `200 OK` response and a Boolean value that specifies the publishing status of the content type.

## Example

### Request


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "domain_promote",
  "sampleKeys": ["contoso.com"]
}-->
```http
POST https://graph.microsoft.com/v1.0/domains/contoso.com/promote
```

<<<<<<< HEAD
# [Cli](#tab/cli)
=======
# [CLI](#tab/cli)
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
[!INCLUDE [sample-code](../includes/snippets/cli/domain-promote-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "string"
}
-->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#Edm.Boolean",
    "value": true
}
```
