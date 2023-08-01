---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Users

$params = @{
	customSecurityAttributes = @{
		Engineering = @{
			"@odata.type" = "#Microsoft.DirectoryServices.CustomSecurityAttributeValue"
			"Project@odata.type" = "#Collection(String)"
			Project = @(
				"Baker"
				"Cascade"
			)
		}
	}
}

Update-MgBetaUser -UserId $userId -BodyParameter $params

```