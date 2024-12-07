# Configuring ECR Roles in Authorizer

## Modify the `Authorizer` class constructor

To make the `ECR role` variable, update the constructor of the `Authorizer` class by adding an `ecr_roles` parameter. This allows the `Authorizer` to accept a list of roles. If no roles are provided, the default role `EBA_DOCUMENT_SUBMITTER_ROLE` will be used.

**Changes to the constructor:**

```python
class Authorizer:
    def __init__(self, hby, vdb, eacrdntler_rgy_reger, leis, ecr_roles=None):
        self.ecr_roles = ecr_roles if ecr_roles else [EBA_DOCUMENT_SUBMITTER_ROLE]
```
