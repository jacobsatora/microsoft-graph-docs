---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Identity.DirectoryManagement

$params = @{
<<<<<<< HEAD
=======
	displayName = "Executive Division"
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
	membershipType = "Dynamic"
	membershipRule = "(user.country -eq "United States")"
	membershipRuleProcessingState = "On"
}

Update-MgBetaAdministrativeUnit -AdministrativeUnitId $administrativeUnitId -BodyParameter $params

```