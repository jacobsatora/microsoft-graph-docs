---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Identity.SignIns

$params = @{
<<<<<<< HEAD
	displayName = "CrossTenantAccessPolicy"
=======
	allowedCloudEndpoints = @(
		"microsoftonline.us"
	)
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
}

Update-MgPolicyCrossTenantAccessPolicy -BodyParameter $params

```