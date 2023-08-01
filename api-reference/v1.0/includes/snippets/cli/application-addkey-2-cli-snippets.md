---
description: "Automatically generated file. DO NOT MODIFY"
---

<<<<<<< HEAD
```cli

=======
```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
>>>>>>> ac57e61007f395881f1814eae37dc23911227b9b
mgc applications add-key post --application-id {application-id} --body '{\
    "keyCredential": {\
        "type": "X509CertAndPassword",\
        "usage": "Sign",\
        "key": "MIIDYDCCAki..."\
    },\
    "passwordCredential": {\
        "secretText": "MKTr0w1..."\
    },\
    "proof":"eyJ0eXAiOiJ..."\
}\
'

```