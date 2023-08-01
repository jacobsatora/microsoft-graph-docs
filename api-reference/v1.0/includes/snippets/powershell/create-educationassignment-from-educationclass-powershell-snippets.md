---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Education

$params = @{
	dueDateTime = [System.DateTime]::Parse("2022-09-16T00:00:00Z")
	displayName = "Reading test 09.14"
	instructions = @{
		contentType = "text"
		content = "Read chapter 4"
	}
	grading = @{
		"@odata.type" = "#microsoft.graph.educationAssignmentPointsGradeType"
<<<<<<< HEAD
		maxPoints = 50
=======
		maxPoints = 
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
	}
	assignTo = @{
		"@odata.type" = "#microsoft.graph.educationAssignmentClassRecipient"
	}
	status = "draft"
	allowStudentsToAddResourcesToSubmission = $true
}

New-MgEducationClassAssignment -EducationClassId $educationClassId -BodyParameter $params

```