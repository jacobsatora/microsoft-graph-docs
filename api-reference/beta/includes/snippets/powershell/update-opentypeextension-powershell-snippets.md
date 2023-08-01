---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Groups

$params = @{
	"@odata.type" = "#microsoft.outlookServices.openTypeExtension"
	extensionName = "Com.Contoso.Estimate"
	companyName = "Contoso"
	expirationDate = "2016-07-30T11:00:00.000Z"
<<<<<<< HEAD
	DealValue = 1010100
=======
	DealValue = 
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
	topPicks = @(
		"Employees only"
		"Add spouse or guest"
		"Add family"
	)
}

Update-MgBetaGroupThreadPostExtension -GroupId $groupId -ConversationThreadId $conversationThreadId -PostId $postId -ExtensionId $extensionId -BodyParameter $params

```