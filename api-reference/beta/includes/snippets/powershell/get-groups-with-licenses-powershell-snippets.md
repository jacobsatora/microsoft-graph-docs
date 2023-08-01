---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Groups

<<<<<<< HEAD
Get-MgBetaGroup -Property "id,assignedLicenses" -Filter "assignedLicenses/any()" 
=======
Get-MgBetaGroup -Property "id,assignedLicenses" -Filter "assignedLicenses/any()" -ExpandProperty "members(`$select=id,displayName)" 
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b

```