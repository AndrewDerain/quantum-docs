---
author: bradben
description: Learn about conditional branching and the 'if' statement in the Q# programming language.
ms.author: brbenefield
ms.date: 02/01/2021
ms.service: azure-quantum
ms.subservice: qsharp-guide
ms.topic: reference
no-loc: ['Q#', '$$v']
title: Conditional branching in Q#
uid: microsoft.quantum.qsharp.conditionalbranching
---

# Conditional branching

Conditional branching is expressed in the form of `if` expressions. An `if` expression consists of an `if` clause, followed by zero or more `elif` clauses and optionally an else-block. Each clause follows the pattern

```qsharp
keyword condition {
    <statements>
}
```

where `keyword` is replaced with `if` or `elif` respectively, `condition` is an expression of type `Bool`, and `<statements>` is to be replaced with zero or more statements. The optional `else`-block consists of the keyword `else` followed by zero or more statements enclosed in braces, `{`  `}`.

The first block for which the `condition` evaluates to `true` will run. The `else` block, if present, runs if none of the conditions evaluate to `true`. The block is executed in its own scope, meaning any bindings made as part of the block are not visible after the block ends.

For example, suppose `qubits` is value of type `Qubit[]` and `r1` and `r2` are of type `Result`,

```qsharp
if r1 == One {
    let q = qubits[0];
    H(q);
} 
elif r2 == One {
    let q = qubits[1];
    H(q);
} 
else {
    H(qubits[2]);
}
```

You can also express simple branching in the form of a [conditional expression](xref:microsoft.quantum.qsharp.conditionalexpressions#conditional-expressions).

## Target-specific restrictions

The tight integration between control-flow constructs and quantum computations poses a challenge for current quantum hardware. Certain quantum processors do not support branching based on measurement outcomes. As such, comparison for values of type `Result` will always result in a compilation error for Q# programs that are targeted to run on such hardware.

Other quantum processors support specific kinds of branching based on measurement outcomes. The more general `if` expressions supported in Q# are compiled into suitable instructions that can be run on such processors. The imposed restrictions are that values of type `Result` may only be compared as part of the condition within `if` expressions in operations. Furthermore, the conditionally run blocks cannot contain any `return` expressions or update mutable variables that are declared outside that block.

