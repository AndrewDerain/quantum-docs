---
author: bradben
ms.author: brbenefield
ms.date: 07/17/2023
ms.service: azure-quantum
ms.subservice: qdk
no-loc: [target, targets]
ms.topic: include
---

## Submit a quantum circuit to the Quantinuum API validator

1. Create a quantum circuit in the [OpenQASM](https://en.wikipedia.org/wiki/OpenQASM) representation. For example, the following example creates a Teleportation circuit:

    ```py
    circuit = """OPENQASM 2.0;
    include "qelib1.inc";
    qreg q[3];
    creg c0[3];
    h q[0];
    cx q[0], q[1];
    cx q[1], q[2];
    measure q[0] -> c0[0];
    measure q[1] -> c0[1];
    measure q[2] -> c0[2];
    """
    ```

    Optionally, you can load the circuit from a file:

    ```py
    with open("my_teleport.qasm", "r") as f:
        circuit = f.read()
    ```

1. Submit the circuit to the Quantinuum target. The following example uses the Quantinuum API validator, which returns a `Job` object. For more information, see [Azure Quantum job reference](xref:microsoft.quantum.optimization.job-reference).

    ```python
    target = workspace.get_targets(name="quantinuum.sim.h1-1sc")
    job = target.submit(circuit, num_shots=500)
    ```

1. Wait until the job is complete and then fetch the results.

    ```python
    results = job.get_results()
    print(results)
    ```

    ```output
    ........
    {'c0': ['000',
    '000',
    '000',
    '000',
    '000',
    '000',
    '000',
    ...
    ]}
    ```

1. You can then visualize the results using [Matplotlib](https://matplotlib.org/stable/users/installing/index.html).

    ```python
    import pylab as pl
    pl.hist(results["c0"])
    pl.ylabel("Counts")
    pl.xlabel("Bitstring")
    ```

![Quantinuum job output](../media/quantinuum-results.png)

Looking at the histogram, you may notice that the random number generator returned 0 every time, which is not very random. This is because that, while the API Validator ensures that your code will run successfully on Quantinuum hardware, it also returns 0 for every quantum measurement. For a true random number generator, you need to run your circuit on quantum hardware.


## Estimate job cost

Before running a job on the QPU, you can estimate how much it will cost to run. To estimate the cost of running a job on the QPU, you can use the `estimate_cost` method.

> [!NOTE]
> To run a cost estimate against a Quantinuum target, you must first reload the *azure-quantum* Python package with the *\[qiskit\]* parameter. For more information, see [Update the azure-quantum Python package](xref:microsoft.quantum.update-qdk#update-the-azure-quantum-python-package).

```python
target = workspace.get_targets(name="quantinuum.qpu.h1-1")
cost = target.estimate_cost(circuit, num_shots=500)

print(f"Estimated cost: {cost.estimated_total}")
```

This prints the estimated cost in H-System Quantum Credits (HQCs).

For the most current pricing details, see [Azure Quantum pricing](xref:microsoft.quantum.providers-pricing#quantinuum), or find your workspace and view pricing options in the "Provider" tab of your workspace via: [aka.ms/aq/myworkspaces](https://aka.ms/aq/myworkspaces).

