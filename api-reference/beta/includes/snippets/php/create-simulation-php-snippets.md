---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Simulation();
$requestBody->setDisplayName('Graph Simulation');

$requestBody->setDurationInDays(7);

$requestBody->setAttackTechnique(new SimulationAttackTechnique('credentialHarvesting'));

$requestBody->setStatus(new SimulationStatus('scheduled'));

$includedAccountTarget = new AddressBookAccountTargetContent();
$includedAccountTarget->setOdataType('#microsoft.graph.addressBookAccountTargetContent');

$includedAccountTarget->setType(new AccountTargetContentType('addressBook'));

$includedAccountTarget->setAccountTargetEmails(['john@contoso.com', 	]);


$requestBody->setIncludedAccountTarget($includedAccountTarget);
$additionalData = [
		'payload@odata.bind' => 'https://graph.microsoft.com/beta/security/attacksimulation/payloads/12345678-9abc-def0-123456789a', 
];
$requestBody->setAdditionalData($additionalData);




$result = $graphServiceClient->security()->attackSimulation()->simulations()->post($requestBody);


```