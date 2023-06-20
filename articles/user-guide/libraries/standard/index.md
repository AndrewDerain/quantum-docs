---
author: bradben
description: Learn about the Microsoft Q# standard libraries that define the operations, functions and data types used in quantum programs.
ms.author: brbenefield
ms.date: 06/21/2023
ms.service: azure-quantum
ms.subservice: qsharp-guide
ms.topic: conceptual
no-loc: ['Q#', '$$v']
title: Introduction to Microsoft Q# standard libraries
uid: microsoft.quantum.libraries.overview.standard.intro
---

# Introduction to the Q# Standard Libraries

Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.
The [`Microsoft.Quantum.Sdk` NuGet package](https://www.nuget.org/packages/Microsoft.Quantum.Sdk/) installed during [installation and validation](xref:microsoft.quantum.install-qdk.overview) automatically provides the Q# standard library.

The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.apiref-intro).

This section describes the most salient features of each part of the standard library and how each feature might be used in practice. 

## Prelude

The [prelude](xref:microsoft.quantum.libraries.overview.standard.prelude) provides a set of essential and very useful functions and operations that can be used when writing quantum programs in Q#.

For example, the <xref:Microsoft.Quantum.Intrinsic> includes the Pauli operators (<xref:Microsoft.Quantum.Intrinsic.X>, <xref:Microsoft.Quantum.Intrinsic.Y> and <xref:Microsoft.Quantum.Intrinsic.Z>), the [Hadamard operation](xref:Microsoft.Quantum.Intrinsic.H), rotations such as the <xref:Microsoft.Quantum.Intrinsic.S>, the <xref:Microsoft.Quantum.Intrinsic.T> and the general <xref:Microsoft.Quantum.Intrinsic.R>. You can also find two-qubit operations such as the <xref:Microsoft.Quantum.Intrinsic.CNOT> and the <xref:Microsoft.Quantum.Intrinsic.SWAP>. This section it also defines the <xref:Microsoft.Quantum.Intrinsic.Measure> which performs a joint measurement of one or more qubits. 

## Classical mathematics

The standard libraries offer the possibility of doing [classical mathematics](xref:microsoft.quantum.libraries.overview.math). The <xref:Microsoft.Quantum.Math> contains classical mathematical functions and data types, which are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.
 
## Type conversions

Q# is a strongly-typed language, which implies that Q# does not implicitly cast between distinct types. You can use the standard libraries to perform [type conversions](xref:microsoft.quantum.libraries.overview.convert). The <xref:Microsoft.Quantum.Convert> contains functions for converting between various Q# data types, for example the <xref:Microsoft.Quantum.Convert.BoolAsResult> converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.

## Higher-order control flow

You can use the standard libraries to manage [higher-order control flow](xref:microsoft.quantum.libraries.overview-standard.control-flow). Fpr example, the <xref:Microsoft.Quantum.Canon> provides a variety of different flow control constructs to express high-level algorithmic as quantum programs easier.

## Data structures and modeling

The standard libraries allow working with [data structures and modeling](xref:microsoft.quantum.libraries.overview.data-structures). The <xref:Microsoft.Quantum.Canon> provides operations, functions, and types for working with classical data, such as pairs and arrays. 

This section also includes two quantum oracles, *Amplitude Amplification* and *Phase Estimation*. The <xref:Microsoft.Quantum.Oracles> provides user-defined types that are used to label the different oracle representations in a type-safe way, making it difficult to accidentally conflate different kinds of black box operations.

## Quantum algorithms

With the standard libraries you can write some of the common and very useful  [quantum algorithms](xref:microsoft.quantum.libraries.overview.standard.algorithms). For example, the <xref:Microsoft.Quantum.Canon> provides the <xref:Microsoft.Quantum.Canon.ApproximateQFT>, which is and approximate generalization of the Quantum Fourier Transform.

## Diagnostics

The standard libraries allow different ways to [diagnose](xref:microsoft.quantum.libraries.overview.diagnostics) mistakes and errors in quantum programs. For example, the <xref:Microsoft.Quantum.Diagnostics> provides many operators for testing and debugging.

## Characterization

You can use the standard libraries to [characterize](xref:microsoft.quantum.libraries.overview.characterization) the effects of operations in order to develop useful quantum algorithms. Since every measurement of a quantum system yields at most one bit of information, the aim is less to learn classical information about the system, rather than to perform a unitary transformation on a state vector. 

## Error correction

One of the most known applications of quantum computing is [quantum error correction](xref:microsoft.quantum.libraries.overview.error-correction). The <xref:Microsoft.Quantum.Canon> provides several distinct user-defined types for building error correcting codes.

## Applications 

[Applications](xref:microsoft.quantum.libraries.overview.applications) describes some other applications of quantum computing that can be performed using Q#, such as the simulation of algorithms and Hamiltonians, and Shor's algorithm.


