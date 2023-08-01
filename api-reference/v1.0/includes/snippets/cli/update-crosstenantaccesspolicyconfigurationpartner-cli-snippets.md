---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

mgc policies cross-tenant-access-policy partners patch --cross-tenant-access-policy-configuration-partner-tenant-id {crossTenantAccessPolicyConfigurationPartner-tenantId} --body '{\
  "inboundTrust": \
  {\
    "isMfaAccepted": true,\
    "isCompliantDeviceAccepted": true,\
    "isHybridAzureADJoinedDeviceAccepted" : true\
=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc policies cross-tenant-access-policy partners patch --cross-tenant-access-policy-configuration-partner-tenant-id {crossTenantAccessPolicyConfigurationPartner-tenantId} --body '{\
  "inboundTrust": {\
    "isMfaAccepted": true,\
    "isCompliantDeviceAccepted": true,\
    "isHybridAzureADJoinedDeviceAccepted": true\
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
  }\
}\
'

```