---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Security

$params = @{
	"@odata.type" = "#microsoft.graph.security.retentionLabel"
<<<<<<< HEAD
	displayName = "String"
	behaviorDuringRetentionPeriod = "String"
	actionAfterRetentionPeriod = "String"
	retentionTrigger = "String"
	retentionDuration = @{
		"@odata.type" = "microsoft.graph.security.retentionDuration"
	}
	isInUse = "Boolean"
	descriptionForAdmins = "String"
	descriptionForUsers = "String"
	createdBy = @{
		"@odata.type" = "microsoft.graph.identitySet"
	}
=======
	retentionDuration = @{
		"@odata.type" = "microsoft.graph.security.retentionDuration"
	}
	descriptionForAdmins = "String"
	descriptionForUsers = "String"
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
	labelToBeApplied = "String"
	defaultRecordBehavior = "String"
}

Update-MgBetaSecurityLabelRetentionLabel -RetentionLabelId $retentionLabelId -BodyParameter $params

```