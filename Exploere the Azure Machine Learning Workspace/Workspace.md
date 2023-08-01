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

### Azure Machine Learning Resources Overview

- **Workspace**: The top-level resource for Azure Machine Learning, used for managing projects, models, and experiments.

- **Compute Resources**: Crucial for training and deploying models, with various types available:
  - Compute instance: For development environments like Jupyter notebooks.
  - Compute cluster: On-demand CPU/GPU nodes for production workloads.
  - Inference cluster: For deploying ML models in production with AKS.
  - Attached compute: To connect other Azure resources.

- **Datastores**: Hold data, with two default datastores for workspace files and blobs. Additional ones can connect to Azure data services like Storage Accounts or Data Lake Storage.

Ensure careful access management to the workspace as it stores important logs, metrics, and models.


### Azure Machine Learning Assets Overview

As a data scientist in Azure Machine Learning, you'll work with various assets within the workspace:

- Models
- Environments
- Data
- Components

#### Models

- Outcome of model training, stored as binary files or in MLModel format using MLflow.
- Versions allow easy tracking and management.

#### Environments

- Ensure code compatibility across different compute targets.
- Specify software packages, environment variables, and settings.
- Stored as images in the Azure Container Registry.

#### Data

- Data assets represent specific files or folders.
- Enable easy access without repeated authentication.

#### Components

- Reusable code snippets for sharing and managing within the workspace.
- Commonly used in pipelines to represent steps.



### Train Models in Azure Machine Learning Workspace

1. **Use the Designer in Azure Machine Learning Studio**
   - Create and run pipelines with a drag-and-drop web-based UI.
   - Ideal for quick exploration during initial model training.
   - Utilize built-in or custom components.

2. **Explore Algorithms and Hyperparameters with Automated Machine Learning**
   - Experiment with various algorithms and hyperparameter values.
   - Automated Machine Learning finds the best performing model.
   - Speeds up the process of model evaluation.

3. **Run a Jupyter Notebook**
   - Develop using Jupyter notebooks in the workspace.
   - Edit and run notebooks in the built-in Notebooks section.
   - Use compute instances for notebook execution.

4. **Run a Script as a Job**
   - Prepare code for production readiness with scripts.
   - Automate machine learning workloads as jobs.
   - Job inputs and outputs are stored in the workspace.

   - Job types: Command (execute a single script), Sweep (hyperparameter tuning), and Pipeline (multiple scripts/components).



[Exercise Repo](https://microsoftlearning.github.io/mslearn-azure-ml/)

practice Explore the Azure Machine Learning workspace exercise.