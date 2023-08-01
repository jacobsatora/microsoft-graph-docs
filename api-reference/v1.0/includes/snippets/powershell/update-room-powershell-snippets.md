---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Calendar

$params = @{
	"@odata.type" = "microsoft.graph.room"
	nickname = "Conf Room"
	building = "1"
	label = "100"
<<<<<<< HEAD
	capacity = 50
=======
	capacity = 
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
	isWheelChairAccessible = $false
}

Update-MgPlace -PlaceId $placeId -BodyParameter $params

```