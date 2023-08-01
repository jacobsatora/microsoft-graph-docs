---
title: "Update authenticationEventListener"
description: "Update the properties of an authenticationEventListener object."
author: "soneff"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# Update authenticationEventListener
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of an [authenticationEventListener](../resources/authenticationeventlistener.md) object. You must specify the **@odata.type** property and the value of the [authenticationEventListener](../resources/authenticationeventlistener.md) object type to update.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|EventListener.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|EventListener.ReadWrite.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /identity/authenticationEventListeners/{authenticationEventListenerId}
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]

You must specify the **@odata.type** property and the value of the [authenticationEventListener](../resources/authenticationeventlistener.md) object type to update. For example, `"@odata.type": "#microsoft.graph.onTokenIssuanceStartListener"`.

|Property|Type|Description|
|:---|:---|:---|
|authenticationEventsFlowId|String|The identifier of the authentication events flow.  Optional.|
|conditions|[authenticationConditions](../resources/authenticationconditions.md)|The conditions on which this authenticationEventListener should trigger. Optional.|
|handler|[onAttributeCollectionHandler](../resources/ontokenissuancestarthandler.md)|The handler to invoke when conditions are met. Can be updated for the **onAttributeCollectionListener** listener type.|
|handler|[onAuthenticationMethodLoadStartHandler](../resources/ontokenissuancestarthandler.md)|The handler to invoke when conditions are met. Can be updated for the **onAuthenticationMethodLoadStartListener** listener type.|
|handler|[onInteractiveAuthFlowStartHandler](../resources/ontokenissuancestarthandler.md)|The handler to invoke when conditions are met. Can be updated for the **onInteractiveAuthFlowStartListener** listener type.|
|handler|[onTokenIssuanceStartHandler](../resources/ontokenissuancestarthandler.md)|The handler to invoke when conditions are met. Can be updated for the **onTokenIssuanceStartListener** listener type.|
|handler|[onUserCreateStartHandler](../resources/ontokenissuancestarthandler.md)|The handler to invoke when conditions are met. Can be updated for the **onUserCreateStartListener** listener type.|
|priority|Int32|The priority of this handler. Between 0 (lower priority) and 1000 (higher priority). Required.|

## Response

If successful, this method returns a `204 No Content` response code.

## Examples

### Request
The following is an example of a request to update an authentication event listener's trigger conditions or priority:
# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "update_authenticationeventlistener"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/identity/authenticationEventListeners/990d94e5-cc8f-4c4b-97b4-27e2678aac28
Content-Type: application/json

{
    "@odata.type": "#microsoft.graph.onTokenIssuanceStartListener",
    "conditions": {
        "applications": {
            "includeAllApplications": false
        }
    },
    "priority": 500
}
```

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/update-authenticationeventlistener-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
The following is an example of the response
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```

