---
author: bradben
description: Learn how to set up an Azure Quantum environment for different languages and platforms.
ms.author: brbenefield
ms.date: 10/26/2023
ms.service: azure-quantum
ms.subservice: qdk
ms.topic: quickstart
no-loc: ['Q#', '$$v', Quantum Development Kit, target, targets]
title: Set up the Quantum Development Kit 
uid: microsoft.quantum.install-qdk.overview
---

# Set up the Quantum Development Kit

> [!NOTE]
> Now available! The [Azure Quantum Development Kit (QDK) Preview](https://github.com/microsoft/qsharp/wiki/Installation) is the latest preview of the Q# development kit, and is available as an extension for Visual Studio Code. For more information, see the [Modern QDK](#the-azure-quantum-development-kit-modern-qdk-preview).

Learn about the different environment options available to develop quantum computing and optimization applications using the [Azure Quantum](xref:microsoft.quantum.azure-quantum-overview) service.

Every environment uses the [Quantum Development Kit (QDK)](xref:microsoft.quantum.overview.q-sharp), an open-source set of tools that includes the quantum programming language Q# and accompanying libraries. With the QDK, you can develop quantum computing applications using different IDEs and languages, and run them on quantum simulators or quantum hardware using Azure Quantum. 

## The Azure Quantum website

With the [Azure Quantum website](https://quantum.microsoft.com/), you can run Q# code in your browser with no setup required. For more information, see [Explore Azure Quantum](xref:microsoft.quantum.get-started.azure-quantum). 

## The Azure Quantum Development Kit (Modern QDK) Preview

The [Modern QDK](https://github.com/microsoft/qsharp/wiki/Installation) is a preview of the next version of the Q# language and development tools. With a smaller footprint and faster performance, it is tightly integrated with Visual Studio Code, it features one-step installation, language improvements, integrated Python and Jupyter Notebook support, new syntax highlighting, debugger support, error messages, and integrated Azure connectivity. By eliminating the dependencies of the [Microsoft QDK](#the-microsoft-quantum-development-kit-qdk), it is now truly platform independent, running on Windows, Mac, Linux, and the web. 

[![download icon.](media/download-install.png) <br>**Download the Modern QDK**](https://marketplace.visualstudio.com/items?itemName=quantum.qsharp-lang-vscode)

> [!WARNING]
> The Modern QDK preview is not fully backwards-compatible with the Classic QDK. Not all APIs have been ported, and existing project files aren't recognized. Your current programs and projects coul require significant changes and updates. 
>
> To help you get started, a new set of samples specifically for the Modern QDK is available on the [QSharp GitHub samples page](https://github.com/microsoft/qsharp/tree/main/samples).
>
> For installation steps and a walkthrough of the new features, see the [Installation page](https://github.com/microsoft/qsharp/wiki/Installation).

> [!NOTE]
> The Modern QDK extension and the Classic QDK extension can both be installed in VS Code at the same time, but cannot be enabled at the same time. If you are working exclusively with the Modern QDK, or if your programs require features not supported yet in the Modern QDK, only enable one extension at a time. 

### What's new 

| Classic QDK | Modern QDK |
| ---- | ---- |
| Requires .NET SDK | No .NET dependency |  
| Azure job integration through Azure CLI  | Azure job integration built-in to VS Code Explorer | 
| No native debugging  | Integrated Q# debugger:<br>- Breakpoints<br>- Stepping into code<br>- Error checking in Q# source files<br>- Auto-completion<br>- Go to definition<br>- Function signature help<br>- Hover definitions<br>- Inspect values for quantum and classic variables  | 
| N/A  | Improved compiler error messages |
| N/A  | Improved language syntax |
| Multiple in-memory simulators | Integrated sparse state simulator |
| Python and Jupyter Notebook support  | Integrated Python and Jupyter Notebook support  | 
| Multiple files  | At this time, the Modern QDK supports single Q# files only  |
| Hybrid computing  | The Modern QDK does not yet support Batch, Interactive, and Integrated computing  |
| Visual Studio support | The Modern QDK will not support the Visual Studio IDE environment  |

For an updated list of Modern QDK features and changes from the Classic QDK, see the [QSharp GitHub Wiki](https://github.com/microsoft/qsharp/wiki/Differences-from-the-previous-QDK).

## The Microsoft Quantum Development Kit (QDK)

The QDK provides: 

- Python packages to submit Qiskit, Cirq and Q# applications to the Azure Quantum service
- The Q# programming language and libraries 
- The IQ# kernel for running Q# on Jupyter Notebooks 
- Extensions for Visual Studio Code and Visual Studio 
- Azure CLI extension to manage the Azure Quantum service and submit Q# applications
- APIs for using Python and .NET languages (C#, F#, and VB.NET) with Q#

Choose from several development environment options: 

- [Use a Jupyter Notebook in the Azure Quantum portal and submit jobs to Azure Quantum (recommended)](#use-a-jupyter-notebook-in-the-azure-quantum-portal-and-submit-jobs-to-azure-quantum-recommended)
- [Use your preferred IDE and language locally and submit jobs to Azure Quantum](#use-your-preferred-ide-and-language-locally-and-submit-jobs-to-azure-quantum)
- [Use GitHub Codespaces](#use-the-qdk-with-github-codespaces)

## Jupyter Notebooks

Jupyter Notebooks allow running code in-place alongside instructions, notes, and other content. This environment is ideal for writing Python and Q# code with embedded explanations or creating quantum computing interactive tutorials. The Jupyter Notebooks environment is built-in to the Azure Quantum portal or can be installed on your local computer.

> [!NOTE]
> Accessing remote quantum hardware and submitting jobs to the Azure Quantum service requires an Azure account with an active subscription. You can [create an account for free](https://azure.microsoft.com/free/?WT.mc_id=A261C142F).

## Use a Jupyter Notebook in the Azure Quantum portal and submit jobs to Azure Quantum (recommended)

The Azure Quantum portal provides a built-in development environment where you can create, upload, store, and run your quantum code in Jupyter Notebooks, using both quantum simulators and quantum hardware targets. A gallery of sample Jupyter Notebooks is provided to get you started with quantum programming in Q#, running Qiskit and Cirq circuits, or submitting optimization problems.  From the portal, you can also manage quantum workspaces, jobs, activity, credits and usage, and access control. To get started, see [Create an Azure Quantum workspace](xref:microsoft.quantum.how-to.workspace). 

[!INCLUDE [Azure Quantum credits banner](includes/azure-quantum-credits.md)]

## Use your preferred IDE and language locally and submit jobs to Azure Quantum

Installing the QDK on your local computer provides support for Jupyter Notebooks, Python, and Q#, along with extensions for Visual Studio Code and Visual Studio. Develop quantum computing applications in your preferred IDE and language and run them on quantum simulators, quantum hardware, or optimization solvers using the Azure Quantum service.

Some scenarios where you might prefer a local environment:

- You have a customized environment or preferred tools that are not available online. 
- You require source control on your project.
- You are working with a multi-file project.

:::image type="content" source="./media/install-portal-3.png" alt-text="Portal installation options":::

> [!NOTE]
> Accessing remote quantum hardware and submitting jobs to the Azure Quantum service requires an Azure account with an active subscription. You can [create an account for free](https://azure.microsoft.com/free/?WT.mc_id=A261C142F).

Select your preferred IDE: 

- [Use Q# and Python with Visual Studio Code or Visual Studio](#use-q-and-python-with-visual-studio-and-visual-studio-code)
- [Use Python with Qiskit, Cirq, or Azure Quantum optimization solvers](#use-python-with-qiskit-or-cirq-or-azure-quantum-optimization-solvers)
- [Use Q# and Python with Jupyter Notebooks](#use-q-and-python-with-jupyter-notebooks)
- [Use the QDK with a pre-configured Docker image](#use-the-qdk-with-a-pre-configured-docker-image-advanced)



### Use Q# and Python with Visual Studio and Visual Studio Code 

While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications. Developing in either of these environments leverages the rich functionality of the Quantum Development Kit (QDK) extension, which includes submitting quantum jobs via the Azure CLI, warnings, syntax highlighting, project templates, and more.

Alternatively, you can go to [Azure portal](https://portal.azure.com/#home) and under your **Quantum workspace > Overview**, you'll find a link to local configuration install guide at the bottom of the page. 

:::image type="content" source="./media/local-guide-overview.png" alt-text="Screenshot of Azure portal showing how to find a link to a local configuration install guide.":::

#### Prerequisite

- [.NET SDK 6.0](https://dotnet.microsoft.com/download)

#### Azure CLI 

The Azure CLI is the preferred method for submitting quantum jobs using a terminal window in VS Code or Visual Studio. 

- Install the [Azure CLI](/cli/azure/install-azure-cli).
- Install the latest Azure CLI `quantum` extension. Open a command prompt and run the following command:

    ```azurecli
    az extension add \
        --upgrade \
        -n quantum

Configure the QDK for your preferred environment from one of the following options:

#### [VS Code](#tab/tabid-vscode)

1. Download and install [VS Code](https://code.visualstudio.com/download) 1.52.0 or greater (Windows, Linux and Mac).
1. Install the [QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

> [!NOTE]
> If you are a Arm-based Mac user, make sure you install [.NET SDK](https://dotnet.microsoft.com/download) 6.0 or greater, as older versions are not supported on this architecture. 

#### [Visual Studio (Windows only)](#tab/tabid-vs)

1. Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 17.0 or greater, with the .NET Core cross-platform development workload enabled.
1. Download and install the [QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit64).

> [!NOTE]
> Although there is Visual Studio for Mac, the QDK extension is only compatible with Visual Studio for Windows.

***

To test your environment, see [Submit Q# jobs to Azure Quantum](xref:microsoft.quantum.submit-jobs?pivots=ide-azurecli).

### Use Python with Qiskit or Cirq, or Azure Quantum optimization solvers

You can use the `azure-quantum` Python package to submit and run Qiskit or Cirq jobs.

To install the `azure-quantum` Python package 

1. Install [Python](https://www.python.org/downloads/) 3.9 or later if you haven't already.
1. Install [PIP](https://pip.pypa.io/en/stable/) and ensure you have **version 19.2 or higher**.
1. Install the `azure-quantum` python package. Use the `--upgrade` flag to make sure to get the latest version.

   To install the `azure-quantum` package without any optional dependencies, run:

   ```Shell
   pip install --upgrade azure-quantum
   ```

   To install the optional dependencies required for submitting Qiskit programs, install using the `[qiskit]` tag:

   ```Shell
   pip install --upgrade azure-quantum[qiskit]
   ```

   To install the optional dependencies required for submitting Cirq programs, install using the `[cirq]` tag:

   ```Shell
   pip install --upgrade azure-quantum[cirq]
   ```

To test your environment, see [Create a quantum-based random number generator](xref:microsoft.quantum.quickstarts.computing) or [Submit a circuit with Qiskit](xref:microsoft.quantum.quickstarts.computing.qiskit).

### Use Q# and Python with Jupyter Notebooks 

All the necessary components for a Jupyter Notebooks environment can be set up with a single conda installation. 

> [!NOTE]
> While a conda installion is recommended, if you prefer not to install conda, you can also set up your environment using the .NET CLI.


#### [Install using conda (recommended)](#tab/tabid-conda)

1. Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads). Consult their [installation guide](https://docs.conda.io/projects/conda/en/latest/user-guide/install/) if you are unsure about any steps. **Note:** 64-bit installation required.

1. Initialize conda for your preferred shell with the `conda init` initialization command. The steps below are tailored to your operating system:

    **(Windows)** Open an Anaconda Prompt by searching for it in the start menu. Then run the initialization command for your shell, for example, `conda init powershell cmd.exe` will set up both the Windows PowerShell and command prompt for you. You can then close this prompt.

    > [!IMPORTANT]
    > To work with PowerShell, conda will configure a startup script to run whenever you launch a PowerShell instance. By default, the script's execution will be blocked on Windows, and requires modifying the PowerShell execution policy with the following command (executed from within PowerShell):
    >
    > ```powershell
    > Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
    > ```

    **(Linux)** If you haven't done so during installation, you can still initialize conda now. Open a terminal and navigate to the `bin` directory inside your selected install location (for example, `/home/ubuntu/miniconda3/bin`). Then run the appropriate command for your shell, for example,`./conda init bash`. Close your terminal for the changes to take effect.

1. From a new terminal, create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:

    ```shell
    conda create -n qsharp-env -c microsoft qsharp notebook

    conda activate qsharp-env
    ```

1. Finally, run `python -c "import qsharp"` to verify your installation and populate your local package cache with all required QDK components.

#### [Install using .NET CLI and pip (advanced)](#tab/tabid-dotnetcli)

1. Prerequisites:

    - [Python](https://www.python.org/downloads/) 3.9 or later
    - The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager
    - [.NET SDK 6.0](https://dotnet.microsoft.com/download/)
    - [Jupyter](https://jupyter.org/install)

1. Install the `qsharp` package, a Python package that enables interop between Q# and Python.

    ```shell
    pip install qsharp
    ```

1. Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and running Q# operations.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > If you encounter a permission error in Linux, install the IQ# kernel in user mode instead with `dotnet iqsharp install --user`.

    > [!NOTE]
    > If you encounter an error and you just installed .NET, you won't be able to run the `dotnet iqsharp install` command immediately. Instead, under Windows, open a new terminal window and try again. Under Linux, log out of your session and log back in to try again.
    > If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:
    >
    > ```dotnetcli
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    >
    > where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system. Typically this will be under `.dotnet/tools` in your user profile folder.

***

You now have both the qsharp Python package and the IQ# kernel for Jupyter, allowing you to compile and run Q# operations from Python and Q# Jupyter Notebooks. To test your environment, see [Submit a quantum program](xref:microsoft.quantum.submit-jobs?pivots=ide-jupyter).

### Use the QDK with a pre-configured Docker image (advanced)

You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.

You can download the IQ# Docker image from <https://github.com/microsoft/iqsharp/#using-iq-as-a-container>. 

You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments. For more information about VS Code Development Containers, see <https://github.com/microsoft/Quantum/tree/master/.devcontainer>.

## Use the QDK with GitHub Codespaces

[GitHub Codespaces](https://docs.github.com/en/codespaces/overview) is a secure and configurable cloud-powered development environment. There is no local setup involved and the default compute instances are available free of charge, with options to increase the number of cores and the amount of RAM and storage.

### Prerequisites

- You will need a GitHub account (https://github.com/join) and access to the GitHub repository you want to work with.

### Configuring your codespace

1. From the root page of your repository, select **Code > Codespaces > ... > Configure dev container**.
1. Replace the contents of the default *devcontainer.json* file with the following:

    ```json
    {    
        "image": "mcr.microsoft.com/devcontainers/universal:2",
        "extensions": [
            "quantum.quantum-devkit-vscode",
            "ms-vscode.csharp",
            "editorconfig.editorconfig",
            "ms-python.python"
        ],
        "features": {
            "ghcr.io/devcontainers/features/python:1": {
            "version": "3.11.2",
            "installJupyterlab": "true"
            },
        "ghcr.io/devcontainers/features/azure-cli:1": {
            "extensions": "quantum"
            }
        },
        "postCreateCommand": "wget https://dot.net/v1/dotnet-install.sh && chmod +x dotnet-install.sh && ./dotnet-install.sh -c 6.0 && rm dotnet-install.sh && pip install azure-quantum[qiskit]"
    }
    
    ```

    > [!TIP]
    > You can customize your GitHub Codespaces at any time after setup. For more information, see [Introduction to dev containers](https://docs.github.com/en/codespaces/setting-up-your-project-for-codespaces/adding-a-dev-container-configuration/introduction-to-dev-containers).

1. Select **Start commit > Commit directly to the main branch**, then select **Commit new file**. GitHub creates a folder named **.devcontainer** with your new configuration file.
1. If you want to create your codespace on a branch other than **main**, select that branch.
1. Select **Code > Codespaces > Create codespace on main** (or your preferred branch). The initial setup could take 5-10 minutes.
1. When the setup is complete, the codespace development shell opens. Wait for the *postCreateCommand* to complete.
1. Enable web-based authentication:
    1. From a command prompt, run **az login --use-device-code**.
    1. Copy the device code and use it to authenticate at **https://microsoft.com/devicelogin**.

### Additional configurations (optional)

- **Codespace names** - Codespaces uses a randomly generated name when it creates a new codespace. You can rename a codespace to a friendlier name by selecting **Code > Codespaces > ... > Rename** next to the codespace name.
- **Compute resources** - By default, each codespace is created with a minimal compute setup. You can increase the compute resources by selecting **Code > Codespaces > ... > Change machine type** next to the codespace name. For more information about fees for additional compute usage, see [Pricing for paid usage](https://docs.github.com/en/billing/managing-billing-for-github-codespaces/about-billing-for-github-codespaces#pricing-for-paid-usage).
- **Billing configuration** - By default, usage costs for GitHub Codespaces are automatically billed to the GitHub account that created the codespace. Optionally, you can connect an Azure subscription to pay for GitHub Codespaces and other GitHub services. For more information and requirements, see [Connecting an Azure subscription to your enterprise](https://docs.github.com/en/enterprise-cloud@latest/billing/managing-billing-for-your-github-account/connecting-an-azure-subscription-to-your-enterprise).

## Next steps

Using the Azure portal:

- [Run Jupyter notebooks on Azure Quantum](xref:microsoft.quantum.how-to.notebooks)
- [Create and submit a Qiskit circuit](xref:microsoft.quantum.quickstarts.computing.qiskit.portal) to quantum hardware.

Using your local environment:

- [Explore development with Q# and Python](xref:microsoft.quantum.how-to.python-local)

