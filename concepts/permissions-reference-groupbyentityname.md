---
title: "Microsoft Graph permissions reference "
description: "Microsoft Graph exposes granular permissions that control the access that apps have to resources, like users, groups, and mail. As a developer, you decide which permissions for Microsoft Graph your app requests."
author: "FaithOmbongi"
ms.author: ombongifaith
ms.reviewer: jackson.woods
ms.localizationpriority: high
ms.topic: reference
ms.prod: "applications"
ms.custom: graphiamtop20, scenarios:getting-started
ms.date: 02/17/2022
---

# Microsoft Graph permissions reference

For an app to access data in Microsoft Graph, the user or administrator must grant it the permissions it needs. This topic lists the delegated and application permissions exposed by Microsoft Graph. For guidance about how to use the permissions, see the [Overview of Microsoft Graph permissions](permissions-overview.md).

To find the unique identifiers for all permissions, see [All permissions and IDs](#all-permissions-and-ids).

To read information about all Microsoft Graph permissions programmatically, sign-in to Graph Explorer using an account that has at least the *Application.Read.All* permission and run the following request.

```msgraph-interactive
GET https://graph.microsoft.com/v1.0/servicePrincipals(appId='00000003-0000-0000-c000-000000000000')?$select=id,appId,displayName,appRoles,oauth2PermissionScopes
```

[!INCLUDE [auth-use-least-privileged](../includes/auth-use-least-privileged.md)]

## AccessReview

| Permission name | Type | Identifier | Display name | Description | Admin consent required? | Microsoft Account supported? |
|---|---|---|---|---|---|---|
| AccessReview.Read.All | Application | d07a8cc0-3d51-4b77-b3b0-32704d1f69fa | Read all access reviews | Allows the app to read access reviews, reviewers, decisions and settings in the organization, without a signed-in user. | Y |  |
| AccessReview.Read.All | Delegated | ebfcd32b-babb-40f4-a14b-42706e83bd28 | Read all access reviews that user can access | Allows the app to read access reviews, reviewers, decisions and settings that the signed-in user has access to in the organization. |  |  |
| AccessReview.ReadWrite.All | Application | ef5f7d5c-338f-44b0-86c3-351f46c8bb5f | Manage all access reviews | Allows the app to read, update, delete and perform actions on access reviews, reviewers, decisions and settings in the organization, without a signed-in user. | Y |  |
| AccessReview.ReadWrite.All | Delegated | e4aa47b9-9a69-4109-82ed-36ec70d85ff1 | Manage all access reviews that user can access | Allows the app to read, update, delete and perform actions on access reviews, reviewers, decisions and settings that the signed-in user has access to in the organization. |  |  |
| AccessReview.ReadWrite.Membership | Application | 18228521-a591-40f1-b215-5fad4488c117 | Manage access reviews for group and app memberships | Allows the app to read, update, delete and perform actions on access reviews, reviewers, decisions and settings in the organization for group and app memberships, without a signed-in user. | Y |  |
| AccessReview.ReadWrite.Membership | Delegated | 5af8c3f5-baca-439a-97b0-ea58a435e269 | Manage access reviews for group and app memberships | Allows the app to read, update, delete and perform actions on access reviews, reviewers, decisions and settings for group and app memberships that the signed-in user has access to in the organization. |

## Application

| Permission name | Type | Identifier | Display name | Description | Admin consent required? | Microsoft Account supported? |
|---|---|---|---|---|---|---|
| Application.Read.All | Application | 9a5d68dd-52b0-4cc2-bd40-abcf44ac3a30 | Read all applications | Allows the app to read all applications and service principals without a signed-in user. | Y |  |
| Application.Read.All | Delegated | c79f8feb-a9db-4090-85f9-90d820caa0eb | Read applications | Allows the app to read applications and service principals on behalf of the signed-in user. |  | Y |
| Application.ReadWrite.All | Application | 1bfefb4e-e0b5-418b-a88f-73c46d2cc8e9 | Read and write all applications | Allows the app to create, read, update and delete applications and service principals without a signed-in user.  Does not allow management of consent grants. | Y |  |
| Application.ReadWrite.All | Delegated | bdfbf15f-ee85-4955-8675-146e8e5296b5 | Read and write all applications | Allows the app to create, read, update and delete applications and service principals on behalf of the signed-in user. Does not allow management of consent grants. |  | Y |
| Application.ReadWrite.OwnedBy | Application | 18a4783c-866b-4cc7-a460-3d5e5662c884 | Manage apps that this app creates or owns | Allows the app to create other applications, and fully manage those applications (read, update, update application secrets and delete), without a signed-in user. ?It cannot update any apps that it is not an owner of. | Y |

## Calendars

| Permission name | Type | Identifier | Display name | Description | Admin consent required? | Microsoft Account supported? |
|---|---|---|---|---|---|---|
| Calendars.Read             | Application | 798ee544-9d2d-430c-a058-570e29e34338 | Read calendars in all mailboxes                   | Allows the app to read events of all calendars without a signed-in user.                                                                                                   | Y | Y |
| Calendars.Read             | Delegated   | 465a38f9-76ea-45b9-9f34-9e8b0d4b0b42 | Read user calendars                               | Allows the app to read events in user calendars .                                                                                                                          |   | N |
| Calendars.Read.Shared      | Delegated   | 2b9c4092-424d-4249-948d-b43879977640 | Read user and shared calendars                    | Allows the app to read events in all calendars that the user can access, including delegate and shared calendars.                                                          |   | Y |
| Calendars.ReadBasic        | Delegated   | 662d75ba-a364-42ad-adee-f5f880ea4878 | Read basic details of user calendars              | Allows the app to read events in user calendars, except for properties such as body, attachments, and extensions.                                                          |   | N |
| Calendars.ReadBasic.All    | Application | 8ba4a692-bc31-4128-9094-475872af8a53 | Read basic details of calendars in all mailboxes  | Allows the app to read events of all calendars, except for properties such as body, attachments, and extensions, without a signed-in user.                                 | Y | Y |
| Calendars.ReadWrite        | Application | ef54d2bf-783f-4e0f-bca1-3210c0444d99 | Read and write calendars in all mailboxes         | Allows the app to create, read, update, and delete events of all calendars without a signed-in user.                                                                       | Y | Y |
| Calendars.ReadWrite        | Delegated   | 1ec239c2-d7c9-4623-a91a-a9775856bb36 | Have full access to user calendars                | Allows the app to create, read, update, and delete events in user calendars.                                                                                               |   | Y |
| Calendars.ReadWrite.Shared | Delegated   | 12466101-c9b8-439a-8589-dd09ee67e8e9 | Read and write user and shared calendars          | Allows the app to create, read, update and delete events in all calendars in the organization user has permissions to access. This includes delegate and shared calendars. |   | Y |