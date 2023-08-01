---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Groups

$params = @{
	originalStartTimeZone = "originalStartTimeZone-value"
	originalEndTimeZone = "originalEndTimeZone-value"
	iCalUId = "iCalUId-value"
<<<<<<< HEAD
	reminderMinutesBeforeStart = 99
=======
	reminderMinutesBeforeStart = 
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
	isReminderOn = $true
}

Update-MgGroupThread -GroupId $groupId -ConversationThreadId $conversationThreadId -BodyParameter $params

```