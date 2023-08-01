---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Users

$params = @{
	customSecurityAttributes = @{
		Engineering = @{
			"@odata.type" = "#Microsoft.DirectoryServices.CustomSecurityAttributeValue"
			"CostCenter@odata.type" = "#Collection(Int32)"
			CostCenter = @(
				1001
				1003
			)
		}
	}
}

Update-MgBetaUser -UserId $userId -BodyParameter $params

```