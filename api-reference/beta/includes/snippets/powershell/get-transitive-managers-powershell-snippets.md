---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Users

# A UPN can also be used as -UserId.
<<<<<<< HEAD
Get-MgBetaUser -UserId $userId -ExpandProperty "manager(`$levels=max;`$select=id,displayName)" -Property "id,displayName" -CountVariable CountVar -ConsistencyLevel eventual 
=======
Get-MgBetaUser -UserId $userId -ExpandProperty "manager(`$levels=max;`$select=id,displayName)" -Property "id,displayName" -ConsistencyLevel eventual 
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b


```