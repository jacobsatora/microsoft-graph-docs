---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Identity.DirectoryManagement

$params = @{
	configuration = @{
		accidentalDeletionPrevention = @{
			synchronizationPreventionType = "enabledForCount"
			alertThreshold = 500
		}
	}
	features = @{
		groupWriteBackEnabled = $true
	}
}

Update-MgBetaDirectoryOnPremiseSynchronization -OnPremisesDirectorySynchronizationId $onPremisesDirectorySynchronizationId -BodyParameter $params

```