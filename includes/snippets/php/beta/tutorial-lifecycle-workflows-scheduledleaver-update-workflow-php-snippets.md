---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Workflow();
$requestBody->setIsEnabled(true);

$requestBody->setIsSchedulingEnabled(true);



$result = $graphServiceClient->identityGovernance()->lifecycleWorkflows()->workflows()->byWorkflowId('workflow-id')->patch($requestBody);


```