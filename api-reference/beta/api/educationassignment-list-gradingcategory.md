---
title: "List educationGradingCategories"
description: "Get a list of the educationGradingCategory objects and their properties."
author: "cristobal-buenrostro"
ms.localizationpriority: medium
ms.prod: "education"
doc_type: apiPageType
---

# List educationGradingCategories
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [educationGradingCategory](../resources/educationgradingcategory.md) objects and their properties.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|EduAssignments.ReadWriteBasic, EduAssignments.ReadWrite|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /education/classes/{educationClassId}/assignmentSettings/gradingCategories
```

## Optional query parameters
This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [educationGradingCategory](../resources/educationgradingcategory.md) objects in the response body.

## Examples

### Request
The following is an example of a request.
# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "list_educationgradingcategory"
}
-->
``` http
GET https://graph.microsoft.com/beta/education/classes/37d99af7-cfc5-4e3b-8566-f7d40e4a2070/assignmentSettings/gradingCategories
```

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/list-educationgradingcategory-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
The following is an example of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.educationGradingCategory"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#education/classes('37d99af7-cfc5-4e3b-8566-f7d40e4a2070')/assignmentSettings/$entity",
    "submissionAnimationDisabled": false,
    "gradingCategories@odata.context": "https://graph.microsoft.com/beta/$metadata#education/classes('37d99af7-cfc5-4e3b-8566-f7d40e4a2070')/assignmentSettings/gradingCategories",
    "gradingCategories": [
        {
            "id": "7625dccd-35e0-4014-a831-06f1b768ec6d",
            "displayName": "Lab Theory",
            "percentageWeight": 15
        },
        {
            "id": "92e6b56a-c85c-4928-a18f-62b7b3bd4319",
            "displayName": "Lab Practice",
            "percentageWeight": 30
        },
        {
            "id": "4a19d24d-779c-4ee2-93c3-7b7cf815ed94",
            "displayName": "Attendance",
            "percentageWeight": 30
        },
        {
            "id": "948f5c3f-12af-47ec-b2a9-6ea225811f0d",
            "displayName": "Assesstment",
            "percentageWeight": 25
        }
    ]
}
```
