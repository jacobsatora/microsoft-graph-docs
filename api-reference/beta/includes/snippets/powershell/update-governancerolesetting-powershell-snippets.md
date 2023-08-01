---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Identity.Governance

$params = @{
	adminEligibleSettings = @(
		@{
			ruleIdentifier = "ExpirationRule"
<<<<<<< HEAD
			setting = "{"permanentAssignment":false,"maximumGrantPeriodInMinutes":129600}"
=======
			setting = '{"permanentAssignment":false,"maximumGrantPeriodInMinutes":129600}'
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
		}
	)
}

Update-MgBetaPrivilegedAccessRoleSetting -PrivilegedAccessId $privilegedAccessId -GovernanceRoleSettingId $governanceRoleSettingId -BodyParameter $params

```