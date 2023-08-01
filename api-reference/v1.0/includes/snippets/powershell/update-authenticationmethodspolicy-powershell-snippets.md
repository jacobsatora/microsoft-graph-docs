---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Identity.SignIns

$params = @{
<<<<<<< HEAD
	"@odata.context" = "https://graph.microsoft.com/v1.0/$metadata#authenticationMethodsPolicy"
=======
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
	registrationEnforcement = @{
		authenticationMethodsRegistrationCampaign = @{
			snoozeDurationInDays = 1
			state = "enabled"
			excludeTargets = @(
			)
			includeTargets = @(
				@{
					id = "3ee3a9de-0a86-4e12-a287-9769accf1ba2"
					targetType = "group"
					targetedAuthenticationMethod = "microsoftAuthenticator"
				}
			)
		}
	}
<<<<<<< HEAD
	authenticationMethodConfigurations = @(
		@{
			"@odata.type" = "#microsoft.graph.fido2AuthenticationMethodConfiguration"
			id = "Fido2"
			state = "disabled"
			isSelfServiceRegistrationAllowed = $false
			isAttestationEnforced = $false
		}
	)
=======
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
}

Update-MgPolicyAuthenticationMethodPolicy -BodyParameter $params

```