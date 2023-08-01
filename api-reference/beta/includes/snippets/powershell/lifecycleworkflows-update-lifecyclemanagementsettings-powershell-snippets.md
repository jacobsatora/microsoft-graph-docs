---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Identity.Governance

$params = @{
	"@odata.context" = "https://graph.microsoft.com/beta/$metadata#identityGovernance/lifecycleWorkflows/settings/$entity"
	workflowScheduleIntervalInHours = 3
<<<<<<< HEAD
=======
	emailSettings = @{
		senderDomain = "ContosoIndustries.net"
		useCompanyBranding = $true
	}
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
}

Update-MgBetaIdentityGovernanceLifecycleWorkflowSetting -BodyParameter $params

```