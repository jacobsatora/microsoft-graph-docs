---
title: "Microsoft Graph permissions reference "
description: "Microsoft Graph exposes granular permissions that control the access that apps have to resources, like users, groups, and mail. As a developer, you decide which permissions for Microsoft Graph your app requests."
author: "FaithOmbongi"
ms.author: ombongifaith
ms.reviewer: jackson.woods
ms.localizationpriority: high
ms.topic: reference
ms.prod: "applications"
zone_pivot_groups: grant-api-permissions
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

<!-- start the delegated permissions zone -->
::: zone pivot="grant-delegated-permissions"

### AccessReview permissions

| Permission | Identifier | Display String | Description | Admin Consent Required | Microsoft Account supported |
|---|---|---|---|---|---|
| AccessReview.Read.All | ebfcd32b-babb-40f4-a14b-42706e83bd28 | Read all access reviews | Allows the app to read access reviews on behalf of the signed-in user. | Yes | No |
| AccessReview.ReadWrite.All | e4aa47b9-9a69-4109-82ed-36ec70d85ff1 | Manage all access reviews | Allows the app to read and write access reviews on behalf of the signed-in user. | Yes | No |
| AccessReview.ReadWrite.Membership | 5af8c3f5-baca-439a-97b0-ea58a435e269 | Manage access reviews for group and app memberships | Allows the app to read and write access reviews of groups and apps on behalf of the signed-in user. | Yes | No |

---

### AdministrativeUnit permissions

| Permission | Identifier | Display String | Description | Admin Consent Required | Microsoft Account supported |
|---|---|---|---|---|---|
| _AdministrativeUnit.Read.All_ | 3361d15d-be43-4de6-b441-3c746d05163d | Read administrative units | Allows the app to read administrative units and administrative unit membership on behalf of the signed-in user. | Yes | No |
| _AdministrativeUnit.ReadWrite.All_ | 7b8a2d34-6b3f-4542-a343-54651608ad81 | Read and write administrative units | Allows the app to create, read, update, and delete administrative units and manage administrative unit membership on behalf of the signed-in user. | Yes | No |

---

### AppCatalog permissions

| Permission | Identifier | Display String | Description | Admin Consent Required | Microsoft Account Required |
|---|---|---|---|---|---|
| _AppCatalog.Read.All_ | 88e58d74-d3df-44f3-ad47-e89edf4472e4 | Read all app catalogs | Allows the app to read the apps in the app catalogs. | No | No |
| _AppCatalog.ReadWrite.All_ | 1ca167d5-1655-44a1-8adf-1414072e1ef9 | Read and write to all app catalogs | Allows the app to create, read, update, and delete apps in the app catalogs. | Yes | No |
| _AppCatalog.Submit_ | 3db89e36-7fa6-4012-b281-85f3d9d9fd2e | Submit an app for admin review | Allows the user to submit and app for admin review for publication in an organization's app catalog and allows user to cancel past submissions that have not been published.</br> &#119821;&#119822;&#119827;&#119812;: Non-admin users submit apps for review by including the  `requiresReview=true` query parameter. | Yes | No |

---
::: zone-end
<!-- end the delegated permissions zone -->

<!-- start the application permissions zone -->
::: zone pivot="grant-application-permissions"

### AccessReview permissions

| Permission | Identifier | Display String | Description | Admin Consent Required |
|---|---|---|---|---|
| AccessReview.Read.All | d07a8cc0-3d51-4b77-b3b0-32704d1f69fa | Read all access reviews | Allows the app to read access reviews without a signed-in user. | Yes |
| AccessReview.ReadWrite.All | ef5f7d5c-338f-44b0-86c3-351f46c8bb5f | Manage all access reviews | Allows the app to read, update, delete and perform actions on access reviews, reviewers, decisions and settings in the organization, without a signed-in user. | Yes |
| AccessReview.ReadWrite.Membership | ef5f7d5c-338f-44b0-86c3-351f46c8bb5f | Manage access reviews for group and app memberships | Allows the app to manage access reviews of groups and apps without a signed-in user. | Yes |

---

### AdministrativeUnit permissions

| Permission | Identifier | Display String | Description | Admin Consent Required |
|---|---|---|---|---|
| _AdministrativeUnit.Read.All_ | 134fd756-38ce-4afd-ba33-e9623dbe66c2 | Read all administrative units | Allows the app to read administrative units and administrative unit membership without a signed-in user. | Yes |
| _AdministrativeUnit.ReadWrite.All_ | 134fd756-38ce-4afd-ba33-e9623dbe66c2 | Read and write all administrative units | Allows the app to create, read, update, and delete administrative units and manage administrative unit membership without a signed-in user. | Yes |

---

### AppCatalog permissions

| Permission | Identifier | Display String | Description | Admin Consent Required |
|---|---|---|---|---|
| _AppCatalog.Read.All_ | e12dae10-5a57-4817-b79d-dfbec5348930 | Read all app catalogs | Allows the app to read apps in the app catalogs without a signed-in user. | Yes |
| _AppCatalog.ReadWrite.All_ | dc149144-f292-421e-b185-5953f2e98d7f | Read and write to all app catalogs | Allows the app to create, read, update, and delete apps in the app catalogs without a signed-in user. | Yes |

---
::: zone-end
<!-- end the application permissions zone -->