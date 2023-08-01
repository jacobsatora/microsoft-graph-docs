---
title: "List bookingBusinesses"
description: "Get a collection of bookingBusiness objects that has been created for the tenant."
ms.localizationpriority: medium
author: "arvindmicrosoft"
ms.prod: "bookings"
doc_type: apiPageType
---

# List bookingBusinesses

Namespace: microsoft.graph

 [!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a collection of [bookingBusiness](../resources/bookingbusiness.md) objects that has been created for the tenant.

This operation returns only the **id** and **displayName** of each Microsoft Bookings business in the collection. For performance considerations, it does not return other properties. You can get the other properties of a Bookings business by specifying its **id** in a [GET](bookingbusiness-get.md) operation.

You can also query for Bookings businesses by specifying a string in a `query` parameter to do substring matching among the businesses of a tenant. For details, see [Example 2](#example-2-query-parameter).

> **Note:** Results are limited to 500 mailboxes. Pagination of the results is not currently supported.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) |  Bookings.Read.All, BookingsAppointment.ReadWrite.All, Bookings.ReadWrite.All, Bookings.Manage.All   |
|Delegated (personal Microsoft account) | Not supported.   |
|Application | Not supported.  |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /bookingBusinesses
```

## Optional query parameters
This method supports some of the [OData query parameters](/graph/query-parameters) to help customize the response.

This method also supports the `query` parameter which accepts a string value. This parameter limits the GET results to businesses that match the specified string. 

## Request headers
| Name      |Description|
|:----------|:----------|
| Authorization  | Bearer {code}|

## Request body
Do not supply a request body for this method.
## Response
If successful, this method returns a `200 OK` response code and collection of [bookingBusiness](../resources/bookingbusiness.md) objects in the response body.

## Examples

### Example 1: Get the Bookings buinsesses in a tenant

#### Request 
The following example gets the Bookings businesses in a tenant.

<!-- {
  "blockType": "request",
  "name": "get_bookingbusinesses"
}-->
```msgraph-interactive
GET https://graph.microsoft.com/beta/bookingBusinesses
```

<<<<<<< HEAD
##### Response 1

=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-bookingbusinesses-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response 
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
The following is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.bookingBusiness",
  "isCollection": true
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "@odata.context":"https://graph.microsoft.com/beta/$metadata#bookingBusinesses",
    "value":[
        {
            "id":"Contosolunchdelivery@contoso.onmicrosoft.com",
            "displayName":"Contoso lunch delivery",
        },
        {
            "id":"Fabrikam@contoso.onmicrosoft.com",
            "displayName":"Fabrikam",
        }
    ]
}
```

### Example 2: Query parameter

#### Request

The following example shows how to use the `query` parameter to get one or more matching 
Bookings businesses in the tenant.

<!-- {
  "blockType": "request",
  "name": "query_bookingbusinesses"
}-->
```msgraph-interactive
GET https://graph.microsoft.com/beta/bookingBusinesses?query=Adventure
```

<<<<<<< HEAD
##### Response 2

=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/query-bookingbusinesses-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
The following is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.bookingBusiness",
  "isCollection": true
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "@odata.context":"https://graph.microsoft.com/beta/$metadata#bookingBusinesses",
    "value":[
        {
            "id":"AdventureWorksCycles@M365B960066.onmicrosoft.com",
            "displayName":"Adventure Works Cycles",
        }
    ]
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "List bookingBusinesses",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
