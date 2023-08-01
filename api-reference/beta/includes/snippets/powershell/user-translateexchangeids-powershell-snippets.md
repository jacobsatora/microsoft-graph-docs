---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Users.Actions

$params = @{
	inputIds = @(
<<<<<<< HEAD
		"{rest-formatted-id-1}"
		"{rest-formatted-id-2}"
=======
		'{rest-formatted-id-1}'
		'{rest-formatted-id-2}'
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
	)
	sourceIdType = "restId"
	targetIdType = "restImmutableEntryId"
}

# A UPN can also be used as -UserId.
Invoke-MgBetaTranslateUserExchangeId -UserId $userId -BodyParameter $params

```