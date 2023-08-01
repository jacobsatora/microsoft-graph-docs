---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Calendar

# A UPN can also be used as -UserId.
<<<<<<< HEAD
Get-MgBetaUserCalendarEvent -UserId $userId -Filter "startsWith(subject,'All')" 
=======
Get-MgBetaUserDefaultCalendarEvent -UserId $userId -Filter "startsWith(subject,'All')" 
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b

```