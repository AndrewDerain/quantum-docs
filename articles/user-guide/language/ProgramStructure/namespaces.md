---
author: bradben
description: Learn about how namespaces are used in the Q# programming language.
ms.author: brbenefield
ms.date: 02/01/2021
ms.service: azure-quantum
ms.subservice: qsharp-guide
ms.topic: reference
no-loc: ['Q#', '$$v']
title: Namespaces in Q#
uid: microsoft.quantum.qsharp.namespaces
---

# Namespaces

At its top-level, a Q# program consists of a set of namespaces. Aside from [comments](xref:microsoft.quantum.qsharp.comments#comments), namespaces are the only top-level elements in a Q# program, and any other elements must reside within a namespace.
Each file may contain zero or more namespaces, and each namespace may span multiple files. Q# does not support nested namespaces.

A namespace block consists of the keyword `namespace`, followed by the namespace name, and the content of the block inside braces `{ }`.
Namespace names consist of a sequence of one or more [legal symbols](xref:microsoft.quantum.qsharp.expressions-overview#identifiers) separated by a dot (`.`).
While namespace names may contain dots for better readability, Q# does not support relative references to namespaces. For example, two namespaces `Foo` and `Foo.Bar` are unrelated, and there is no notion of a hierarchy. In particular, for a function `Baz` defined in `Foo.Bar`, it is *not* possible to open `Foo` and then access that function via `Bar.Baz`.

Namespace blocks may contain [open directives](#open-directives) as well as [operation](xref:microsoft.quantum.qsharp.callabledeclarations#callable-declarations), [function](xref:microsoft.quantum.qsharp.callabledeclarations#callable-declarations), and [type](xref:microsoft.quantum.qsharp.typedeclarations#type-declarations) declarations. These may occur in any order and are recursive by default, meaning they can be declared and used in any order and can call themselves; there is no need for the declaration of a type or callable to precede its use.

## Open Directives

By default, everything declared within the same namespace can be accessed without further qualification. However, declarations in a different namespace can only be used by qualifying their name with the name of the namespace they belong to or by opening that namespace before it is used, as shown in the following example.  

```qsharp
namespace Microsoft.Quantum.Samples {
    
    open Microsoft.Quantum.Arithmetic; 
    open Microsoft.Quantum.Arrays as Array; 

    // ...
}
```

The example uses an `open` directive to import all types and callables declared in the Microsoft.Quantum.Artithmetic namespace. They can then be referred to by their unqualified name unless that name conflicts with a declaration in the namespace block or another opened namespace.

To avoid typing out the full name while still distinguishing where certain elements come from, you can define an alternative name, or *alias*, which is usually shorter, for a particular namespace. In this case, all types and callables declared in that namespace can be qualified by the defined short name instead.
In the previous example, this is the case for the `Microsoft.Quantum.Arrays` namespace. A function `IndexRange` declared in `Microsoft.Quantum.Arrays`, for example, can then be used via `Array.IndexRange` within that namespace block.

Whether you are opening a namespace or defining an alias, `open` directives are valid throughout the namespace piece in that file only.



