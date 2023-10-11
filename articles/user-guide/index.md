---
author: bradben
description: A guide to the Q# programming language, the Q# libraries, and how to develop quantum programs.
ms.author: brbenefield
ms.date: 08/29/2023
ms.service: azure-quantum
ms.subservice: qsharp-guide
ms.topic: overview
no-loc: ['Q#', '$$v', Quantum Development Kit, Quantum machine learning, target, targets]
title: The Q# user guide
uid: microsoft.quantum.user-guide-qdk.overview
---

# The Q# quantum programming language user guide

The [Q# quantum programming language](xref:microsoft.quantum.overview.q-sharp) is part of Microsoft's Quantum Development Kit, which provides rich IDE support and tools for program visualization and analysis. With Q# and the Quantum Development Kit (QDK) you can write your quantum programs and run them on real quantum hardware using [Azure Quantum](xref:microsoft.quantum.azure-quantum-overview).

For more information, see [how to configure your quantum development environment](xref:microsoft.quantum.install-qdk.overview) and [how to submit Q# jobs to Azure Quantum](xref:microsoft.quantum.submit-jobs).

[!INCLUDE [Copilot in Azure Quantum banner](../includes/copilot-banner.md)]

The Q# user guide contains:

- [**Ways to run a Q# program**](xref:microsoft.quantum.user-guide-qdk.overview.host-programs): A Q# program can be run as a standalone application, or with an additional host program, written in Python or a .NET language.

- [**Testing and debugging Q# programs**](xref:microsoft.quantum.user-guide-qdk.overview.testingdebugging): As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior. The Quantum Development Kit for testing and debugging quantum programs.

- **The Q# language guide**: Q# is a stand-alone language offering a high level of abstraction. There is no notion of a quantum state or a circuit; instead, Q# implements programs in terms of statements and expressions, much like classical programming languages. The Q# language guide provides a full specification and documentation of the Q# quantum programming language. 

- [**Quantum simulators documentation**](xref:microsoft.quantum.machines.overview): Quantum simulators are software programs that run on classical computers and act as the target machine for a Q# program, making it possible to run and test quantum programs on classical computers.

- [**The Q# library documentation**](xref:microsoft.quantum.libraries.overview): The Quantum Development Kit provides additional domain-specific functionality through *NuGet* packages that can be added to your Q# projects. The documentation includes operations, functions, user-defined types, examples, and concepts that make up the standard Q# library, as well as the quantum chemistry, quantum machine learning, and quantum numerics libraries.

## What is in a Q# program?

Let's explore the general pieces that fit within a Q# program. Consider the following Q# program:

```qsharp
namespace HelloQuantum {

    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;


    @EntryPoint()
    operation SayHelloQ() : Unit {
        Message("Hello quantum world!");
    }
}
```

`EntryPoint` tells the Q# compiler where to begin executing the program. The program prints this message:

```output
    Hello quantum world!
```

### Namespaces

Every Q# file typically starts with a namespace. Here's an example:

```qsharp
namespace HelloQuantum {
    // Your code goes here.
}
```

[Namespaces](xref:microsoft.quantum.qsharp.namespaces) help you organize related functionality. Their use becomes important when you use Q# libraries in your programs and when you write your own libraries.

### Libraries

Q# makes extensive use of libraries. A library is a package that contains functions and operations that you can use in quantum programs.

For example, the [Microsoft.Quantum.Chemistry](/qsharp/api/qsharp/microsoft.quantum.chemistry?azure-portal=true) library helps you perform quantum calculations that relate to chemistry. There are several standard libraries that include all sorts of basic operations.

When you call a function or operation from a library, you specify the library's namespace. Here's an example that calls the `Message` function from the [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) library to print a message to the console:

```qsharp
namespace HelloQuantum {

    @EntryPoint()
    operation SayHelloQ() : Unit {
        Microsoft.Quantum.Intrinsic.Message("Hello quantum world!");
    }
}
```

More commonly, you use the `open` directive to make your code more succinct and easier to read. 

This example does the same thing as the previous example, except this one uses the `open` directive to bring the `Microsoft.Quantum.Intrinsic` namespace into the program:

```qsharp
namespace HelloQuantum {

    open Microsoft.Quantum.Intrinsic;

    @EntryPoint()
    operation SayHelloQ() : Unit {
        Message("Hello quantum world!");
    }
}
```

Here, you simply specify `Message` and the compiler understands which namespace it belongs to.

The Q# documentation provides complete reference documentation for each built-in library. For more information, see [the Q# libraries documentation](/quantum/user-guide/libraries/additional-libraries?tabs=tabid-csproj).

### Types

Q# provides many [built-in types](xref:microsoft.quantum.qsharp.typesystem-overview) you're already familiar with, including `Int`, `Double`, `Bool`, and `String`, along with types that are specific to quantum computing. For example, the `Result` type represents the result of a qubit measurement and can have one of two possible values: `One` and `Zero`. Q# also provides types that define ranges, arrays, and tuples. You can even define your [own custom types](xref:microsoft.quantum.qsharp.typedeclarations).

All in all, the Q# type system is fairly minimalist, in the sense that there isn't an explicit notion of classes or interfaces as one might be used to from classical languages like C# or Java. 

### Allocating qubits

In Q#, qubits are allocated through the `use` keyword. You can allocate one or many qubits at a time.

Here's an example that allocates one qubit:

```qsharp
// Allocate a qubit.
use q = Qubit();

// Do something with q here.
```
By default, every qubit you allocate with the `use` keyword starts in the zero state.

### Quantum operations

Once allocated, a qubit can be passed to operations and functions, also referred to as [*callables*](xref:microsoft.quantum.qsharp.callabledeclarations). In some sense, this is all that a Q# program can do with a qubit. [Operations](xref:microsoft.quantum.qsharp.operationsandfunctions) are the basic building blocks of a Q# program. A Q# operation is a quantum subroutine. That is, it's a callable routine that contains quantum operations that modify the state of the qubit register.

To define a Q# operation, you specify a name for the operation along with its inputs and its output. Here's a basic example:

```qsharp
operation SayHelloQ() : Unit {
    Message("Hello quantum world!");
}
```

Here, `SayHelloQ` is the name of the operation. It takes zero arguments as its input and returns type `Unit`, which means that the operation returns no information.

The [Q# libraries](xref:microsoft.quantum.libraries.overview) also provide operations that you can use in your programs, for example the Hadamard or `H` operation. Given a qubit in Z-basis, the `H` operation puts the qubit into an *even* superposition. Once in superposition, the qubit has a 50% chance of being measured as zero or one.

Any direct actions on state of a qubit are all defined by *intrinsic* callables such as [`X`](xref:Microsoft.Quantum.Intrinsic.X) and [`H`](xref:Microsoft.Quantum.Intrinsic.H) - that is, callables whose implementations are not defined within Q# but are instead defined by the target machine. What these operations actually *do* is only made concrete by the target machine you choose to run the particular Q# program. For more information, see [Q# program implementation](xref:microsoft.quantum.qsharp.programstructure-overview).

For example, if running the program on the [full-state simulator](xref:microsoft.quantum.machines.overview.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system. But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding **real operations** on the **real quantum hardware**. For example, in a trapped-ion quantum computer the quantum operations are realized by precisely timed laser pulses.

A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.
In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.

### Measuring qubits

There are many sorts of quantum measurements, but Q# focuses on projective measurements on single qubits, also known as [Pauli measurements](xref:microsoft.quantum.concepts.pauli). Upon measurement in a given basis (for example, the computational basis $\ket{0},\ket{1}$) the qubit state is projected onto whichever basis state was measured, hence destroying any superposition between the two.

In Q#, Pauli measurements are done by applying [`Measure` operation](xref:Microsoft.Quantum.Intrinsic.Measure), which performs a joint measurement of one or more qubits in the specified Pauli bases. `Measure` operation returns a `Result` type.

> [!NOTE]
> If the basis array and qubit array are different lengths, then the `Measure` operation will fail.

To implement a measurement in the computational basis $\ket{0},\ket{1}$, you can also use the [`M` operation](xref:Microsoft.Quantum.Intrinsic.M), wich performs a measurement of a single qubit in the Pauli Z basis. Therefore `M` operation is equivalent to applying `Measure([PauliZ], [qubit])`.

A simple example is the following program, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // Allocate a qubit, by default it is in zero state      
    use q = Qubit();  
    // We apply a Hadamard operation H to the state
    // It now has a 50% chance of being measured 0 or 1  
    H(q);      
    // Now we measure the qubit in Z-basis.
    let result = M(q);
    // We reset the qubit before releasing it.
    if result == One { X(q); }
    // Finally, we return the result of the measurement.
    return result;
    
}
```

For performing measurements beyond a single joint measurement, the [`Microsoft.Quantum.Measurement` namespace](xref:Microsoft.Quantum.Measurement) includes more specific operations. For example, the [`MultiM` operation](xref:Microsoft.Quantum.Measurement.MultiM) takes an array of qubits and returns an array of measurement results in the computational basis. 

## Next steps

- [Ways to run a Q# program](xref:microsoft.quantum.user-guide-qdk.overview.host-programs)
- [Testing and debugging Q# programs](xref:microsoft.quantum.user-guide-qdk.overview.testingdebugging)
- [Statements in Q#](xref:microsoft.quantum.qsharp.statements-overview)
- [Program implementation in Q#](xref:microsoft.quantum.qsharp.programstructure-overview)
- [Expressions in Q#](xref:microsoft.quantum.qsharp.expressions-overview)
- [Data types in Q#](xref:microsoft.quantum.qsharp.typesystem-overview)
- [Q# libraries](xref:microsoft.quantum.libraries.overview)
- [Quantum simulators](xref:microsoft.quantum.machines.overview)
