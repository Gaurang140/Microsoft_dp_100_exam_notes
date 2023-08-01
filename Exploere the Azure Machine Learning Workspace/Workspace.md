# Learning objectives

- Create an Azure Machine Learning workspace.
- Identify resources and assets.
- Train models in the workspace.

## Create an Azure Machine Learning workspace.

1. Azure portal UI
2. Azure Resource Manager (ARM) template
3. Azure CLI with Azure Machine Learning CLI extension (CLI v2)
4. Azure Machine Learning Python SDK

Example using python SDK v2
```python
from azure.ai.ml.entities import Workspace

workspace_name = "dp100_exam"

ws_basic = Workspace(
    name=workspace_name,
    location="eastus",
    display_name="Basic workspace-example",
    description="This example shows how to create a basic workspace",
)
ml_client.workspaces.begin_create(ws_basic)

```


## Giving Access to Azure Machine Learning Workspace

You can grant access to your Azure Machine Learning workspace using role-based access control (RBAC). In the Access control tab, you can manage permissions for individual users or teams, specifying the actions they can perform.

Built-in roles include:
- **Owner**: Full access and can manage others' access.
- **Contributor**: Full access but can't manage access for others.
- **Reader**: View-only access, no changes allowed.

Azure Machine Learning specific roles:
- **AzureML Data Scientist**: Can perform most actions within the workspace, except compute resource management.
- **AzureML Compute Operator**: Allowed to manage compute resources within the workspace.

If the built-in roles don't meet your needs, you can create custom roles to assign specific permissions.




## Identify resources and assets.


## Train models in the workspace.