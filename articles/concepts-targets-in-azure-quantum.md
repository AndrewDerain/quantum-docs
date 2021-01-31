---
author: KittyYeungQ
description: Article describing the different types of targets existing in Azure Quantum
ms.author: kitty
ms.date: 02/01/21
ms.service: azure-quantum
ms.subservice: core
ms.topic: article
title: Targets in Azure Quantum
uid: microsoft.quantum.concepts.targets
---

# Targets in Azure Quantum

This article introduces the different type of targets available in Azure Quantum and the Quantum Development Kit (QDK).

## Targets as quantum devices

Targets in Azure Quantum can be solvers for optimization
problems or quantum devices (either physical or simulated) that you can use to
run Q# quantum applications.

Each provider in Azure Quantum offers a range of targets to cover different
aspects of quantum computing. For example, some providers offer quantum hardware
to test your quantum algorithms in real quantum computers, and quantum
simulators and validators to test your algorithm in noise-free simulated quantum
devices.

## Different types of targets in Azure Quantum

Currently, Azure Quantum includes the following types of targets:

### Optimization solver

A platform to solve binary optimization problems on classical CPUs, or
hardware accelerated on field-programmable gate arrays (FPGA), GPUs or hardware annealers.

### Quantum Processing Unit (QPU): different profiles

A quantum processing unit (QPU) is a physical or simulated processor that
contains a number of interconnected qubits that can be manipulated to compute
quantum algorithms. It's the central component of a quantum computer. Currently, Azure Quantum and the QDK manage three different
profiles for QPUs:

- **Full:** This profile can run any Q# program within the
  limits of memory for simulated quantum processing units (QPU) or the number of qubits of the physical
  quantum hardware.
- **No Control Flow:** This profile can run any Q# program that doesn't
  require the use of the results from qubit measurements to control the
  program flow. Within a Q# program targeted for this kind of QPU, values of
  type `Result` do not support equality comparison.
- **Basic Measurement Feedback:** This profile has limited ability to use the
  results from qubit measurements to control the program flow. Within a Q# program
  targeted for this kind of QPU, you can only compare values of type `Result` as
  part of conditions within `if` statements in operations. The corresponding
  conditional blocks may not contain `return` or `set` statements.

## Next steps

Before learning how to submit jobs to run on Azure Quantum targets, you need to [prepare
your environment](xref:microsoft.quantum.setup.cli) to use Azure Quantum.