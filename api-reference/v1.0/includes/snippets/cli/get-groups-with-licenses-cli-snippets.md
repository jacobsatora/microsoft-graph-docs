---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

mgc groups list --select "id,assignedLicenses&`$filter=assignedLicenses/any()"
=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc groups list --select "id,assignedLicenses&`$filter=assignedLicenses/any()&`$expand=members(`$select=id,displayName)"
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b

```