---
title: "Delete internalDomainFederation"
description: "Deletes an internalDomainFederation object."
author: "rahul-nagraj"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# Delete internalDomainFederation
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Deletes an [internalDomainFederation](../resources/internaldomainfederation.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|Domain.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported|
|Application|Domain.ReadWrite.All|

The calling user must be assigned one of the following [Azure AD roles](/azure/active-directory/roles/permissions-reference):

- Security Administrator
- External Identity Provider Administrator

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
DELETE /domains/{domainsId}/federationConfiguration/{internalDomainFederationId}
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `204 No Content` response code.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "delete_internaldomainfederation",
  "sampleKeys": ["contoso.com", "96db02e2-80c1-5555-bc3a-de92ffb8c5be"]
}
-->
``` http
DELETE https://graph.microsoft.com/beta/domains/contoso.com/federationConfiguration/96db02e2-80c1-5555-bc3a-de92ffb8c5be
```

<<<<<<< HEAD
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/delete-internaldomainfederation-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
### Response
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```

