---
author: george-moussa
description: Reference for azure.quantum.Workspace
ms.author: georgenm
ms.date: 02/01/2021
ms.service: azure-quantum
ms.subservice: optimization
ms.topic: reference
title: Azure Quantum Workspace
uid: microsoft.quantum.optimization.workspace
---

# Quantum Workspace

```python
from azure.quantum import Workspace
```

## Constructor

To create a Workspace object, you must supply the following arguments in order
to connect. If you have not already created a workspace, follow the steps in
[Creating an Azure Quantum workspace
guide](xref:microsoft.quantum.workspaces-portal) using the following values:

- `subscription_id`: The subscription ID where the workspace is deployed.
- `resource_group`: The name of the resource group where the workspace is deployed.
- `name`: The name of the workspace.
- `location`: The location where the workspace is deployed, for example **West US**,
with either the `create` or `show` commands.

```py
workspace = Workspace (
    subscription_id = "",  # Add your subscription_id
    resource_group = "",   # Add your resource_group
    name = ""              # Add your workspace name
    location= ""           # Add the workspace location, for example, westus
)
```

## Workspace.get_job

Retrieves information about a job.

```py
from azure.quantum import Workspace

workspace = Workspace(...)
job = workspace.get_job("285cfcb4-6822-11ea-a05f-2a16a847b8a3")
print(job.details.status)

> Succeeded
```


## Workspace.list_jobs

Returns the list of existing jobs in the workspace.
```py
from azure.quantum import Workspace

workspace = Workspace(...)
jobs = workspace.list_jobs()
for job in jobs:
    print(job.id, job.details.status)

> 08ea8792-68f2-11ea-acc5-2a16a847b8a3 Succeeded
> 0ab1863a-68f2-11ea-82b3-2a16a847b8a3 Succeeded
> 0c5c507e-68f2-11ea-ba75-2a16a847b8a3 Cancelled
> f0c8de58-68f1-11ea-a565-2a16a847b8a3 Executing
```

## Workspace.cancel_job

Cancels a job that was previously submitted.

```py
from azure.quantum import Workspace

workspace = Workspace(...)
job = workspace.get_job("285cfcb4-6822-11ea-a05f-2a16a847b8a3")

workspace.cancel_job(job)
print(job.details.status)

> Succeeded
```

## Workspace.login

Logs the local user in to Azure. It first attempts to use cached credentials
from a secure local cache. An optional `refresh` argument can be used to bypass
the cache and force authentication.

> [!NOTE]
> Passing `refresh=True` will clear the workspace.credentials property and force a new Interactive Device Authentication.
Whatever credentials were set in the workspace.credentials will be lost, including ServicePrincipalCredentials.

```python
workspace = Workspace(...)
workspace.login()
```

When you call login you will see the following printed in your console:

```output
To sign in, use a web browser to open the page https://microsoft.com/devicelogin and enter the code <CODE> to authenticate.
```

Once logged in, the credentials are cached locally. The location of the
cache can be specified via the `AZURE_QUANTUM_TOKEN_CACHE` environment variable.