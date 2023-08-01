---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Calendar

# A UPN can also be used as -UserId.
<<<<<<< HEAD
Get-MgUserCalendarEvent -UserId $userId -Filter "startsWith(subject,'All')" 
=======
Get-MgUserDefaultCalendarEvent -UserId $userId -Filter "startsWith(subject,'All')" 
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b

```