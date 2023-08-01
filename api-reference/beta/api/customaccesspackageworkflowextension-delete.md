---
title: "Delete customAccessPackageWorkflowExtension"
description: "Delete a customAccessPackageWorkflowExtension object."
author: "currenmehta-zz"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: apiPageType
---

# Delete customAccessPackageWorkflowExtension
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Delete a [customAccessPackageWorkflowExtension](../resources/customaccesspackageworkflowextension.md) object. The custom workflow extension must first be removed from any associated [policies](../resources/accesspackageassignmentpolicy.md) before it can be deleted. Follow these steps to remove the custom workflow extension from any associated policies:
1. First retrieve the accessPackageCatalogId by calling the [Get accessPackageAssignmentPolicies](accesspackageassignmentpolicy-get.md) operation and appending `?$expand=accessPackage($expand=accessPackageCatalog)` to the query. For example, `https://graph.microsoft.com/beta/identityGovernance/entitlementManagement/accessPackageAssignmentPolicies?$expand=accessPackage($expand=accessPackageCatalog)`.
2. Use the access package catalog ID and retrieve the ID of the **customAccessPackageWorkflowExtension** object that you want to delete by running the [LIST customAccessPackageWorkflowExtensions](accesspackagecatalog-list-customaccesspackageworkflowextensions.md) operation.
3. Call the [Update accessPackageAssignmentPolicy](accesspackageassignmentpolicy-update.md) operation to remove the custom workflow extension object from the policy. For an example, see [Example 2: Remove the customExtensionHandlers and verifiableCredentialSettings from a policy](accesspackageassignmentpolicy-update.md#example-2-remove-the-customextensionhandlers-and-verifiablecredentialsettings-from-a-policy).

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|EntitlementManagement.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|EntitlementManagement.ReadWrite.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
DELETE /identityGovernance/entitlementManagement/accessPackageCatalogs/{catalogId}/customAccessPackageWorkflowExtensions/{customAccessPackageWorkflowExtensionId}
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
  "name": "delete_customaccesspackageworkflowextension"
}
-->
``` http
DELETE /identityGovernance/entitlementManagement/accessPackageCatalogs/32efb28c-9a7a-446c-986b-ca6528c6669d/customAccessPackageWorkflowExtensions/98ffaec5-ae8e-4902-a434-5ffc5d3d3cd0
```

<<<<<<< HEAD

=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/delete-customaccesspackageworkflowextension-cli-snippets.md)]
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
HTTP/1.1 204 No Response
```
