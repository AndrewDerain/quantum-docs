---
author: bradben
description: Learn how to submit Cirq quantum circuits to the Azure Quantum service using an online notebook.
ms.author: brbenefield
ms.date: 10/19/2022
ms.service: azure-quantum
ms.subservice: qdk
ms.topic: quickstart
no-loc: ['Python', '$$v', target, targets]
title: 'Quickstart: Create Cirq circuits with online notebooks'
zone_pivot_groups: quantum-computing-platforms
uid: microsoft.quantum.quickstarts.computing.cirq.portal
--- 

# Quickstart: Submit a circuit with Cirq using an Azure Quantum notebook

[!INCLUDE [Modern QDK portal banner](includes/new-qdk-portal-support.md)]

Learn how to use the Azure Quantum service to submit a Cirq quantum circuits to an IonQ or Quantinuum quantum computing target via the Azure Quantum service. This example uses an Azure Quantum notebook and the built-in *azure-quantum* Python package - no installation or configuration is required. For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits).

## Prerequisites

- An Azure account with an active subscription. If you don’t have an Azure account, register for free and sign up for a [pay-as-you-go subscription](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go).
- An Azure Quantum workspace. For more information, see [Create an Azure Quantum workspace](xref:microsoft.quantum.how-to.workspace).

## Create a new Notebook in your workspace

1. Log in to the [Azure portal](https://portal.azure.com/) and select the workspace from the previous step.
1. In the left blade, select **Notebooks**.
1. Click **My Notebooks** and click **Add New**.
1. In **Kernel Type**, select **IPython**.
1. Type a name for the file, for example *Cirq.ipynb*, and click **Create file**. 

When your new Notebook opens, it automatically creates the code for the first cell, based on your subscription and workspace information.

```py
from azure.quantum import Workspace
workspace = Workspace (
    subscription_id = <your subscription ID>, 
    resource_group = <your resource group>,   
    name = <your workspace name>,          
    location = <your location>        
    )
```

> [!NOTE]
> Unless otherwise noted, you should run each cell in order as you create it to avoid any compilation issues. 

Click the triangular "play" icon to the left of the cell to run the code. 

## Load the required imports

First, you'll need to import an additional module. 

Click **+ Code** to add a new cell, then add and run the following code:

```python
from azure.quantum.cirq import AzureQuantumService
```

## Connect to the Azure Quantum service

Next, use an `AzureQuantumService` constructor to create a `service` object that connects to your Azure Quantum workspace.  Add a new cell, but don't run it yet, with the following code:

```python
service = AzureQuantumService(
  resource_id="",
  location=""
)
```

Before running this cell, your program needs the resource ID and the
location of your Azure Quantum workspace: 

1. Click **Save** to save your notebook.
1. Click **Overview** to view the workspace properties.
1. Hover over the **Resource ID** field and click the **Copy to clipboard** icon. 
1. Click **Notebooks** and open your Cirq notebook. 
1. Paste the resource ID into the value for *resource_id*, and then add the location string from the first cell to *location*.
1. Run the cell.

 :::image type="content" source="media/azure-quantum-resource-id.png" alt-text="Screenshot of the overview pane showing the details of your Azure Quantum workspace.":::

::: zone pivot="platform-ionq"

[!INCLUDE [ionq-procedure](includes/quickstart-cirq-include-ionq-portal.md)]

::: zone-end

::: zone pivot="platform-quantinuum"

[!INCLUDE [quantinuum-procedure](includes/quickstart-cirq-include-quantinuum-portal.md)]

::: zone-end

> [!IMPORTANT]
> Submitting multiple circuits on a single job is currently not supported. As a workaround you can call the `backend.run` method to submit each circuit asynchronously, then fetch the results of each job. For example:
>
> ```python
> jobs = []
> for circuit in circuits:
>     jobs.append(backend.run(circuit, shots=N))
> 
> results = []
> for job in jobs:
>     results.append(job.result())
>```
