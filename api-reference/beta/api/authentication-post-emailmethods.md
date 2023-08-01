---
title: "Create emailAuthenticationMethod"
description: "Create a new emailAuthenticationMethod object."
author: "jpettere"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: "apiPageType"
---

# Create emailAuthenticationMethod
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Set a user's [emailAuthenticationMethod](../resources/emailauthenticationmethod.md) object. Email authentication is a self-service password reset method. A user may only have one email authentication method.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:---------------------------------------|:-------------------------|
| Delegated (work or school account)     | UserAuthenticationMethod.ReadWrite.All |
| Delegated (personal Microsoft account) | Not supported. |
| Application                            | UserAuthenticationMethod.ReadWrite.All |

[!INCLUDE [rbac-authentication-methods-apis-write-others](../includes/rbac-for-apis/rbac-authentication-methods-apis-write-others.md)]

Users cannot add an email authentication method to their own account.

## HTTP request

Add an email authentication method to another user's account.
<!-- {  "blockType": "ignored" } -->
``` http
POST /users/{id | userPrincipalName}/authentication/emailMethods
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [emailAuthenticationMethod](../resources/emailauthenticationmethod.md) object with the desired email address.

The following table shows the properties that are required when you create the [emailAuthenticationMethod](../resources/emailauthenticationmethod.md).

|Property|Type|Description|
|:---|:---|:---|
|emailAddress|String|Email address|



## Response

If successful, this method returns a `201 Created` response code and a new [emailAuthenticationMethod](../resources/emailauthenticationmethod.md) object in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "create_emailauthenticationmethod_from_",
  "sampleKeys": ["kim@contoso.com"]
}
-->
``` http
POST https://graph.microsoft.com/beta/users/kim@contoso.com/authentication/emailMethods
Content-Type: application/json

{
  "emailAddress": "kim@contoso.com"
}
```

<<<<<<< HEAD
=======
# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/create-emailauthenticationmethod-from--cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
### Response
The following is an example of the response.

**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.emailAuthenticationMethod"
}
-->
``` http
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "3ddfcfc8-9383-446f-83cc-3ab9be4be18f",
  "emailAddress": "kim@contoso.com"
}
```
