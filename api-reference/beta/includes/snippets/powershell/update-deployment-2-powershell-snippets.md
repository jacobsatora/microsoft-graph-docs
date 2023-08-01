---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.WindowsUpdates

$params = @{
	"@odata.type" = "#microsoft.graph.windowsUpdates.deployment"
	settings = @{
<<<<<<< HEAD
		"@odata.type" = "microsoft.graph.windowsUpdates.windowsDeploymentSettings"
=======
		"@odata.type" = "microsoft.graph.windowsUpdates.deploymentSettings"
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
		monitoring = @{
			monitoringRules = @(
				@{
					signal = "rollback"
					threshold = 5
					action = "pauseDeployment"
				}
			)
		}
	}
}

Update-MgBetaWindowsUpdatesDeployment -DeploymentId $deploymentId -BodyParameter $params

```