---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Identity.SignIns

$params = @{
	phoneNumber = "+1 2065555555"
	phoneType = "mobile"
}

<<<<<<< HEAD
# A UPN can also be used as -UserId.
=======
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
New-MgBetaUserAuthenticationPhoneMethod -UserId $userId -BodyParameter $params

```