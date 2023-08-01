---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

<<<<<<< HEAD
Import-Module Microsoft.Graph.Beta.Identity.Governance

$params = @{
	action = "AdminRemove"
	justification = "Assign User Admin eligibility to IT Helpdesk (User) group"
	roleDefinitionId = "fdd7a751-b60b-444a-984c-02652fe8fa1c"
	directoryScopeId = "/"
	principalId = "07706ff1-46c7-4847-ae33-3003830675a1"
	scheduleInfo = @{
		startDateTime = [System.DateTime]::Parse("2021-07-26T18:08:06.2081758Z")
		expiration = @{
			endDateTime = [System.DateTime]::Parse("2022-06-30T00:00:00Z")
			type = "AfterDateTime"
		}
	}
=======
Import-Module Microsoft.Graph.Identity.Governance

$params = @{
	action = "adminRemove"
	roleDefinitionId = "8424c6f0-a189-499e-bbd0-26c1753c96d4"
	directoryScopeId = "/"
	principalId = "071cc716-8147-4397-a5ba-b2105951cc0b"
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
}

New-MgBetaRoleManagementDirectoryRoleEligibilityScheduleRequest -BodyParameter $params

```