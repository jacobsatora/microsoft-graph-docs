---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Mail

$params = @{
	subject = "Annual review"
	body = @{
		contentType = "HTML"
		content = "You should be proud!"
	}
	toRecipients = @(
		@{
			emailAddress = @{
				address = "rufus@contoso.com"
			}
		}
	)
	extensions = @(
		@{
			"@odata.type" = "microsoft.graph.openTypeExtension"
			extensionName = "Com.Contoso.Referral"
			companyName = "Wingtip Toys"
			expirationDate = "2015-12-30T11:00:00.000Z"
<<<<<<< HEAD
			dealValue = 10000
=======
			dealValue = 
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
		}
	)
}

# A UPN can also be used as -UserId.
New-MgBetaUserMessage -UserId $userId -BodyParameter $params

```