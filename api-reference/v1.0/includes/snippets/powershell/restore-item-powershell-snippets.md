---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

<<<<<<< HEAD
Import-Module Microsoft.Graph.Beta.Files
=======
Import-Module Microsoft.Graph.Files
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b

$params = @{
	parentReference = @{
		id = "String"
	}
	name = "String"
}

<<<<<<< HEAD
Restore-MgBetaDriveItem -DriveId $driveId -DriveItemId $driveItemId -BodyParameter $params
=======
Restore-MgDriveItem -DriveId $driveId -DriveItemId $driveItemId -BodyParameter $params
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b

```