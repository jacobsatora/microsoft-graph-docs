---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new VersionsRequestBuilderGetRequestConfiguration();
$queryParameters = VersionsRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->select = ["category","displayName","versionNumber"];
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->identityGovernance()->lifecycleWorkflows()->workflows()->byWorkflowId('workflow-id')->versions()->get($requestConfiguration);


```