---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Devices.CloudPrint

$params = @{
	displayName = "Test Printer"
	manufacturer = "Test Printer Manufacturer"
	model = "Test Printer Model"
	physicalDeviceId = $null
	hasPhysicalDevice = $false
	certificateSigningRequest = @{
<<<<<<< HEAD
		content = "{content}"
		transportKey = "{sampleTransportKey}"
=======
		content = '{content}'
		transportKey = '{sampleTransportKey}'
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
	}
	connectorId = $null
}

New-MgPrintPrinter -BodyParameter $params

```