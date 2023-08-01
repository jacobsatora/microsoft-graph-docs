---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Teams

<<<<<<< HEAD
Get-MgBetaChatMessage -ChatId $chatId -Top 2 -Sort "lastModifiedDateTime desc" -Filter "lastModifiedDateTime ge 2022-09-22T00:00:00.000Z and lastModifiedDateTime le 2022-09-24T00:00:00.000Z" 
=======
Get-MgBetaChatMessage -ChatId $chatId -Top 2 -Sort "lastModifiedDateTime desc" -Filter "lastModifiedDateTime gt 2022-09-22T00:00:00.000Z and lastModifiedDateTime lt 2022-09-24T00:00:00.000Z" 
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b

```