---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
mgc users mail-folders child-folders create --user-id {user-id} --mail-folder-id {mailFolder-id} --body '{\
  "@odata.type": "microsoft.graph.mailSearchFolder",\
  "displayName": "Weekly digests",\
  "includeNestedFolders": true,\
  "sourceFolderIds": ["AQMkADYAAAIBDAAAAA=="],\
  "filterQuery": "contains(subject, 'weekly digest')"\
}\
'

```