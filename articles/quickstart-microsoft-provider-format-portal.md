---
author: bradben
description: Learn how to to submit provider-formatted quantum circuits with OpenQASM and IonQ JSON to the Azure Quantum service using an online notebook.
ms.author: brbenefield
ms.date: 11/13/2023
ms.service: azure-quantum
ms.subservice: qdk
ms.topic: quickstart
no-loc: ['Python', '$$v', target, targets]
title: 'Quickstart: Submit provider-formatted circuits with online notebooks'
zone_pivot_groups: quantum-computing-platforms-Pasqal
uid: microsoft.quantum.quickstarts.computing.provider.portal
--- 

# Quickstart: Submit a circuit with a provider-specific format using an Azure Quantum notebook.

[!INCLUDE [Modern QDK portal banner](includes/new-qdk-portal-support.md)]

Learn how to use the `azure-quantum` Python package to submit provider-specific formatted quantum circuits, (for example, [OpenQASM 2.0](https://github.com/Qiskit/openqasm/tree/OpenQASM2.x) or [IonQ JSON](https://docs.ionq.com/#tag/quantum_programs)), to an IonQ or Quantinuum quantum computing target via the Azure Quantum service. This example uses an Azure Quantum notebook and the built-in *azure-quantum* Python package - no installation or configuration is required. For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits).

## Prerequisites

- An Azure account with an active subscription. If you don’t have an Azure account, register for free and sign up for a [pay-as-you-go subscription](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go).
- An Azure Quantum workspace. For more information, see [Create an Azure Quantum workspace](xref:microsoft.quantum.how-to.workspace).


## Create a new Notebook in your workspace

1. Log in to the [Azure portal](https://portal.azure.com/) and select the workspace from the previous step.
1. In the left blade, select **Notebooks**.
1. Click **My Notebooks** and click **Add New**.
1. In **Kernel Type**, select **IPython**.
1. Type a name for the file, for example *OpenQASM.ipynb*, and click **Create file**. 

When your new Notebook opens, it automatically creates the code for the first cell, based on your subscription and workspace information.

```py
from azure.quantum import Workspace
workspace = Workspace ( 
    resource_id = "", # Add your resource_id 
    location = ""  # Add your workspace location (for example, "westus") 
)
```

> [!NOTE]
> Unless otherwise noted, you should run each cell in order as you create it to avoid any compilation issues. 

Click the triangular "play" icon to the left of the cell to run the code. 

::: zone pivot="platform-ionq"

[!INCLUDE [ionq-procedure](includes/quickstart-provider-include-ionq-portal.md)]

::: zone-end

::: zone pivot="platform-pasqal"

[!INCLUDE [pasqal-procedure](includes/quickstart-provider-include-pasqal-portal.md)]

::: zone-end

::: zone pivot="platform-quantinuum"

[!INCLUDE [quantinuum-procedure](includes/quickstart-provider-include-quantinuum-portal.md)]

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

