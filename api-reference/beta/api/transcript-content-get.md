---
title: "Get transcript content"
description: "Read the content of a transcript object."
author: "elmazdremdzhe"
ms.localizationpriority: medium
ms.prod: "sites-and-lists"
doc_type: apiPageType
---

# Get transcript content
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read the content of a [transcript](../resources/transcript.md) object that belongs to a certain media item. 

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|Files.Read, Files.ReadWrite, Files.Read.All, Files.ReadWrite.All, Sites.Read.All, Sites.ReadWrite.All|
|Delegated (personal Microsoft account) | Not supported.    |
|Application|Files.Read.All, Files.ReadWrite.All, Sites.Read.All, Sites.ReadWrite.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /drives/{drive-id}/items/{item-id}/media/transcripts/{transcript-id}/content
GET /drives/{drive-id}/root:/{item-path}/media/transcripts/{transcript-id}/content
GET /groups/{group-id}/drive/items/{item-id}/media/transcripts/{transcript-id}/content
GET /groups/{group-id}/drive/root:/{item-path}/media/transcripts/{transcript-id}/content
GET /me/drive/items/{item-id}/media/transcripts/{transcript-id}/content
GET /me/drive/root:/{item-path}/media/transcripts/{transcript-id}/content
GET /sites/{siteId}/drive/items/{itemId}/media/transcripts/{transcript-id}/content
GET /sites/{siteId}/drive/root:/{item-path}/media/transcripts/{transcript-id}/content
GET /users/{userId}/drive/items/{itemId}/media/transcripts/{transcript-id}/content
GET /users/{userId}/drive/root:/{item-path}/media/transcripts/{transcript-id}/content
```

## Optional query parameters
This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|if-match| If this request header is included and the cTag provided matches the current tag on the transcript content, an HTTP `304 Not Modified` response is returned. Optional.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and the transcript content in the response body.
Response body contains bytes for the transcript. 

## Examples

### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "get_transcript_content"
}
-->
``` http
GET https://graph.microsoft.com/beta/drives/1b502de9-89b4-4bba-a44e-a2aab0b4f293/items/01MNC3BE7ZQHKN7ZE67JB2G36IYRIGNWHA/media/transcripts/9415fe71-68b5-42bd-9e5f-86d41ef3efc9/content
```

### Response
The following is an example of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "stream"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: text/vtt

WEBVTT

1b502de9-89b4-4bba-a44e-a2aab0b4f293/17-0
00:00:03.122 --> 00:00:06.992
Ut enim ad minim veniam
quis nostrud exercitation ullamco.

1b502de9-89b4-4bba-a44e-a2aab0b4f293/21-0
00:00:08.692 --> 00:00:09.982
laboris nisi ut aliquip ex ea
commodo consequat.

1b502de9-89b4-4bba-a44e-a2aab0b4f293/92-0
00:00:10.912 --> 00:00:13.846
Duis aute irure dolor in
reprehenderit in voluptate velit.
```

