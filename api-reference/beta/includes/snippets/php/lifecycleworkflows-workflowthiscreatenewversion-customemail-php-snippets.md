---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CreateNewVersionPostRequestBody();
$additionalData = [
		'category' => 'joiner', 
		'description' => 'Configure new hire tasks for onboarding employees on their first day', 
		'displayName' => 'custom email marketing API test', 
		'isEnabled' => true,
		'isSchedulingEnabled' => false,
		'executionConditions' => 		[
				'@odata.type' => '#microsoft.graph.identityGovernance.triggerAndScopeBasedConditions', 
				'scope' => 				[
						'@odata.type' => '#microsoft.graph.identityGovernance.ruleBasedSubjectSet', 
						'rule' => '(department eq \'Marketing\')', 
				],

				'trigger' => 				[
						'@odata.type' => '#microsoft.graph.identityGovernance.timeBasedAttributeTrigger', 
						'timeBasedAttribute' => 'employeeHireDate', 
						'offsetInDays' => 0,
				],

		],

		'tasks' => [
				[
						'continueOnError' => false,
						'description' => 'Enable user account in the directory', 
						'displayName' => 'Enable User Account', 
						'isEnabled' => true,
						'taskDefinitionId' => '6fc52c9d-398b-4305-9763-15f42c1676fc', 
						'arguments' => [
							],
				],
				[
						'continueOnError' => false,
						'description' => 'Send welcome email to new hire', 
						'displayName' => 'Send Welcome Email', 
						'isEnabled' => true,
						'taskDefinitionId' => '70b29d51-b59a-4773-9280-8841dfd3f2ea', 
						'arguments' => [
								[
										'name' => 'cc', 
										'value' => '1baa57fa-3c4e-4526-ba5a-db47a9df95f0', 
								],
								[
										'name' => 'customSubject', 
										'value' => 'Welcome to the organization {{userDisplayName}}!', 
								],
								[
										'name' => 'customBody', 
										'value' => 'Welcome to our organization {{userGivenName}}!', 
								],
								[
										'name' => 'locale', 
										'value' => 'en-us', 
								],
							],
				],
			],
];
$requestBody->setAdditionalData($additionalData);




$result = $graphServiceClient->identityGovernance()->lifecycleWorkflows()->workflows()->byWorkflowId('workflow-id')->microsoftGraphIdentityGovernanceCreateNewVersion()->post($requestBody);


```