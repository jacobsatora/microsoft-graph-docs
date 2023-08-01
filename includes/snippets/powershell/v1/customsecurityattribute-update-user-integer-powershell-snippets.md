---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Users

$params = @{
	customSecurityAttributes = @{
		Engineering = @{
			"@odata.type" = "#Microsoft.DirectoryServices.CustomSecurityAttributeValue"
			"NumVendors@odata.type" = "#Int32"
			NumVendors = 8
		}
	}
}

Update-MgBetaUser -UserId $userId -BodyParameter $params

```