---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Security

$params = @{
<<<<<<< HEAD
	displayname = "My legalHold with sources"
=======
	displayName = "My legalHold with sources"
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
	description = "Created from Graph API"
	"userSources@odata.bind" = @(
		@{
			"@odata.type" = "microsoft.graph.security.userSource"
			email = "SalesTeam@M365x809305.OnMicrosoft.com"
		}
	)
	"siteSources@odata.bind" = @(
		@{
			"@odata.type" = "microsoft.graph.security.siteSource"
		}
	)
}

New-MgBetaSecurityCaseEdiscoveryCaseLegalHold -EdiscoveryCaseId $ediscoveryCaseId -BodyParameter $params

```