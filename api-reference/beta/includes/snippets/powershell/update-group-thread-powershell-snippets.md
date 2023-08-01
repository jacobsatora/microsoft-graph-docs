---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Groups

$params = @{
	originalStartTimeZone = "originalStartTimeZone-value"
	originalEndTimeZone = "originalEndTimeZone-value"
	uid = "iCalUId-value"
<<<<<<< HEAD
	reminderMinutesBeforeStart = 99
=======
	reminderMinutesBeforeStart = 
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
	isReminderOn = $true
}

Update-MgBetaGroupThread -GroupId $groupId -ConversationThreadId $conversationThreadId -BodyParameter $params

```