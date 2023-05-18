---
title: Which optimization solver should I use?
description: This document provides a basic guide on which solvers to use in Azure Quantum.
author: SoniaLopezBravo
ms.author: sonialopez
ms.service: azure-quantum
ms.subservice: optimization
ms.date: 05/01/2023
ms.topic: conceptual
uid: microsoft.quantum.optimization.choose-solver
---

# Which optimization solver should I use?

[!INCLUDE [QIO deprecation warning](includes/qio-deprecate-warning.md)]

Azure Quantum offers a broad range of solvers for optimization problems. You can consult the full list in the [reference page](xref:microsoft.quantum.reference.qio-target-list). However, it is unfortunately not possible to determine *a priori* which solver will perform best for a new optimization problem. This article describes Microsoft's suggested strategy to find a suitable solver by benchmarking.

## Benchmarking objective

The benchmarking objective will have a large influence on the selection of a suitable solver. This objective for the solvers is dictated by the application. For example, one benchmarking objective is to find the closest solution to the global minimum. Another objective might be to find the closest solution to the global minimum but in a given time interval or for a specified runtime cost.
If you are interested in solving several problems from a similar domain, a benchmarking objective might be to find a solver which produces good results for most instances, rather than returning very good results for some instances but failing to give a good enough solution for the remaining instances.

## Benchmarking strategy

Optimization problems from the same field of domain might share common features. As such, you could start with the solver which worked best for previous problems of the same domain and use that as a baseline. Nevertheless, even in such a case it makes sense to benchmark the other solvers again from time to time.

Start with the parameter-free solvers, as they don't require parameter tuning:

- [Parameter-free simulated annealing](xref:microsoft.quantum.optimization.simulated-annealing#parameter-free-simulated-annealing-cpu): This solver provides a solid baseline for the runtime and possible minima.

- [Parameter-free parallel tempering](xref:microsoft.quantum.optimization.parallel-tempering#parameter-free-parallel-tempering)

Automatically determining parameters for solvers is convenient, but also creates a runtime overhead. If you have to solve many similar problems or want to achieve better performance, parameterized solvers should be considered. Start with parameterized simulated annealing if the parameter-free simulated annealing solver provided better results than the parameter-free parallel tempering. Otherwise, start with parameterized parallel tempering.

Afterwards, you should benchmark the remaining solvers.

## Next steps

Explore more aspects of optimization in Azure Quantum.

- [Parameterized simulated annealing](xref:microsoft.quantum.optimization.simulated-annealing#parameterized-simulated-annealing-cpu)
- [Parameterized parallel tempering](xref:microsoft.quantum.optimization.parallel-tempering#parameterized-parallel-tempering)
- [Binary optimization](xref:microsoft.quantum.optimization.concepts.binary-optimization)
- [Ising model](xref:microsoft.quantum.optimization.concepts.ising-model)
- [Cost functions](xref:microsoft.quantum.optimization.concepts.cost-function)
