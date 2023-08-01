---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.WindowsUpdates

$params = @{
	"@odata.type" = "#microsoft.graph.windowsUpdates.deployment"
	content = @{
<<<<<<< HEAD
		"@odata.type" = "microsoft.graph.windowsUpdates.featureUpdateReference"
		version = "20H2"
	}
	settings = @{
		"@odata.type" = "microsoft.graph.windowsUpdates.windowsDeploymentSettings"
		monitoring = @{
			monitoringRules = @(
				@{
					"@odata.type" = "#microsoft.graph.windowsUpdates.monitoringRule"
=======
		"@odata.type" = "#microsoft.graph.windowsUpdates.catalogContent"
		catalogEntry = @{
			"@odata.type" = "#microsoft.graph.windowsUpdates.featureUpdateCatalogEntry"
			id = "f341705b-0b15-4ce3-aaf2-6a1681d78606"
		}
	}
	settings = @{
		"@odata.type" = "microsoft.graph.windowsUpdates.deploymentSettings"
		schedule = @{
			gradualRollout = @{
				"@odata.type" = "#microsoft.graph.windowsUpdates.rateDrivenRolloutSettings"
				durationBetweenOffers = "P7D"
				devicePerOffer = 
			}
		}
		monitoring = @{
			monitoringRules = @(
				@{
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
					signal = "rollback"
					threshold = 5
					action = "pauseDeployment"
				}
			)
		}
	}
}

New-MgBetaWindowsUpdatesDeployment -BodyParameter $params

```