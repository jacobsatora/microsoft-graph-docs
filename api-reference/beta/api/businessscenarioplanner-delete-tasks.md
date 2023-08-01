---
title: "Delete businessScenarioTask"
description: "Delete a businessScenarioTask object."
author: "TarkanSevilmis"
ms.localizationpriority: medium
ms.prod: "business-scenarios"
doc_type: apiPageType
---

# Delete businessScenarioTask

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Delete a [businessScenarioTask](../resources/businessscenariotask.md) object.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|BusinessScenarioData.ReadWrite.OwnedBy|
|Delegated (personal Microsoft account)|Not supported.|
|Application| BusinessScenarioData.ReadWrite.OwnedBy|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
DELETE /solutions/businessScenarios/{businessScenarioId}/planner/tasks/{businessScenarioTaskId}
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

The following is an example of a request.

<!-- {
  "blockType": "request",
  "name": "delete_businessscenariotask",
  "sampleKeys": ["c5d514e6c6864911ac46c720affb6e4d", "pmc1rS1Io0C3rXQhyXIsNmUAOeIi"]
}
-->
``` http
DELETE https://graph.microsoft.com/beta/solutions/businessScenarios/c5d514e6c6864911ac46c720affb6e4d/planner/tasks/pmc1rS1Io0C3rXQhyXIsNmUAOeIi
```

<<<<<<< HEAD
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/delete-businessscenariotask-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
### Response

The following is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```
