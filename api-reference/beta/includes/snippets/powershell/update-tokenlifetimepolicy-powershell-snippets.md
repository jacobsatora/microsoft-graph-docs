---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Identity.SignIns

$params = @{
	definition = @(
<<<<<<< HEAD
		"definition-value"
	)
	displayName = "displayName-value"
=======
		'{"TokenLifetimePolicy":{"Version":1,"AccessTokenLifetime":"5:30:00"}}'
	)
	displayName = "Contoso token lifetime policy"
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
	isOrganizationDefault = $true
}

Update-MgBetaPolicyTokenLifetimePolicy -TokenLifetimePolicyId $tokenLifetimePolicyId -BodyParameter $params

```