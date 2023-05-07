---
author: SoniaLopezBravo
description: A reference list with deep coverage of quantum computing topics if you want to learn more about quantum computer programming.
ms.author: sonialopez
ms.date: 08/24/2022
ms.service: azure-quantum
ms.subservice: computing
ms.topic: resources
no-loc: ['Q#', '$$v', Quantum Approximate Optimization Algorithm, Quantum Development Kit]
title: Quantum computing learning resources
uid: microsoft.quantum.more-information
---

# Further reading: Quantum computing learning resources

In the [quantum computing concepts](xref:microsoft.quantum.concepts.intro) you'll find foundational concepts for any developer of quantum software. However they don't span the depth or breadth of what is known about quantum computer programming. Since quantum computing remains a rapidly developing field, there is no one resource that has all of the information needed.  

This article compiles some of the most popular resources that you may find useful when learning quantum computing. 

## Microsoft quantum computing resources 

Learn how to develop and apply quantum computing solutions with the Quantum Development Kit and Azure Quantum services.

+ [Quantum computing foundations modules](/training/paths/quantum-computing-fundamentals/): an interactive, free, hands-on learning path. In these modules you will learn how to use the power of quantum computing and the Azure Quantum service to complete different tasks that are crucial for the space mission.
+ [Quantum Katas](xref:microsoft.quantum.tutorial-qdk.katas): a collection of self-paced Q# quantum programming tutorials.
+ [Q# code samples](/samples/browse/?languages=qsharp): start building your first quantum solution with this collection of ready-to-use code samples.
+ [Q# blog](https://devblogs.microsoft.com/qsharp/): a blog written by developers for developers. You can read about the lastest QDK and Q# insights, and quantum challenges and hackathons announcements.
+ [Research publications](https://www.microsoft.com/research/research-area/quantum-computing/?facet%5Btax%5D%5Bmsr-content-type%5D[]=3&facet%5Btax%5D%5Bmsr-research-area%5D[]=243138&sort_by=most-recent): read about the latest advancement in quantum hardware and algorithms developed by Microsoft researchers.

These and more quantum computing resources can be found in the [Microsoft's quantum learning page](https://azure.microsoft.com/resources/quantum-computing/).

## Q# community made content

The following sites are created and developed by the quantum community who is excited about quantum programming. 

+ [Awesome qsharp](https://github.com/ebraminio/awesome-qsharp/): an open source list of Q# code and resources.
+ [Quantum computing StackExchange](https://quantumcomputing.stackexchange.com/questions/tagged/q%23): an online community for quantum developers to learn, and share their knowledge.
+ [Subreddit for the Q# programming language](https://www.reddit.com/r/qsharp/): an online community in Reddit to discuss the latest news and developments of Q#.
+ [Subreddit for the quantum computing](https://www.reddit.com/r/quantumcomputing/): an online community in Reddit to discuss the latest news and developments of quantum computing.
+ [Q# Community](https://qsharp.community/): a community group that collects and maintains Q# programming language projects, including new libraries, algorithm implementations, and tutorials.


## Quantum computing online courses

Check out the following quantum computing learning courses.

+ [Quantum Computing - Brilliant Course](https://brilliant.org/courses/quantum-computing/): learn to build quantum algorithms from the ground up with a quantum computer simulated in your browser in this course, created in collaboration with quantum researchers and practitioners from Microsoft, X, and Caltech's IQIM.
+ [Introduction to Quantum Computing - LinkedIn Learning](https://www.linkedin.com/learning/introduction-to-quantum-computing):  a 1h25m video introduction to  quantum computing when you'll see some application cases of quantum computing, opportunities and risks. 
+ [Quantum Computing through Comics - HackadayU classes](https://hackaday.io/project/168554-introduction-to-quantum-computing): learn about quantum computing concepts and algorithm programming through classroom discussion and intuitive comics.

## Bibliography for beginners 

### Quantum Computing

If you are a quantum enthusiast and want to start learning the theory behind quantum computing, the following publications will instruct you in topics such as quantum physics, computer science and linear algebra. 

+ Nielsen, M. A. & Chuang, I. L. (2010). Quantum Computation and Quantum Information. Quantum Computation and Quantum Information, UK: Cambridge University Press, 2010.
+ Kaye, P., Laﬂamme, R., & Mosca, M. (2007). An introduction to quantum computing. Oxford University Press.
+ Rieﬀel, E. G., & Polak, W. H. (2011). Quantum computing: A gentle introduction. MIT Press.
+ Sarah C. Kaiser and Christopher E. Granade. [Learn Quantum Computing with Python and Q# - A hands-on approach](https://www.manning.com/books/learn-quantum-computing-with-python-and-q-sharp).

### Optimization 

The following publications might be good starting points to understand the mathematical principles behind the quantum-inspired optimization solvers:

+ Glover F., Kochenberger G., Du Y. (2019). A Tutorial on Formulating and Using QUBO Models.
+ Lucas, Andrew. (2014) Ising formulations of many NP problems. Frontiers in Physics.

## Advanced topics

If you want to go the extra mile, the following publications go deeper into more specific concepts and at a scientific research level.

### Elementary techniques for building controlled gates

+ Barenco, A., Bennett, C. H., Cleve, R., DiVincenzo, D. P., Margolus, N., Shor, P., ... & Weinfurter, H. (1995). Elementary gates for quantum computation. Physical Review A, 52(5), 3457.
+ Jones, C. (2013). Low-overhead constructions for the fault-tolerant Toﬀoli gate. Physical Review A, 87(2), 022328.

### Techniques for preparing quantum states

+ Shende, V. V., Markov, I. L., & Bullock, S. S. (2004). Minimal universal two-qubit controlled-NOT-based circuits. Physical Review A, 69(6), 062321.
+ Ozols, M., Roetteler, M., & Roland, J. (2013). Quantum rejection sampling. ACM Transactions on Computation Theory (TOCT), 5(3), 11.
+ Grover, L., & Rudolph, T. (2002). Creating superpositions that correspond to eﬃciently integrable probability distributions. arXiv preprint quant-ph/0208112.
+ Farhi, E., Goldstone, J., Gutmann, S., & Sipser, M. (2000). Quantum computation by adiabatic evolution. arXiv preprint quant-ph/0001106.

### Approaches for synthesizing circuits out of H, T and CNOT gates
+ Kliuchnikov, V., Maslov, D., & Mosca, M. (2013). Asymptotically optimal approximation of single qubit unitaries by Cliﬀord and T circuits using a constant number of ancillary qubits. Physical Review Letters, 110(19), 190502.
+ Ross, N. J., & Selinger, P. (2014). Optimal ancilla-free Cliﬀord+ T approximation of z-rotations. arXiv preprint arXiv:1403.2975.
+ Kliuchnikov, V. (2013). Synthesis of unitaries with Cliﬀord+ T circuits. arXiv preprint arXiv:1306.3200.
+ Jones, N. C., Whitﬁeld, J. D., McMahon, P. L., Yung, M. H., Van Meter, R., Aspuru-Guzik, A., & Yamamoto, Y. (2012). Faster quantum chemistry simulation on fault-tolerant quantum computers. New Journal of Physics, 14(11), 115023.

### Approaches for quantum arithmetic

+ Takahashi, Y., & Kunihiro, N. (2005). A linear-size quantum circuit for addition with no ancillary qubits. Quantum Information & Computation, 5(6), 440-448.
+ Draper, T. G. (2000). Addition on a quantum computer. arXiv preprint quant-ph/0008033.
+ Soeken, M., Roetteler, M., Wiebe, N., & De Micheli, G. (2017, March). Design automation and design space exploration for quantum computers. In 2017 Design, Automation & Test in Europe Conference & Exhibition (DATE) (pp. 470-475). IEEE.

### Methods for fast quantum sampling (amplitude amplification) and probability estimation

+ Brassard, G., Hoyer, P., Mosca, M., & Tapp, A. (2002). Quantum amplitude ampliﬁcation and estimation. Contemporary Mathematics, 305, 53-74.
+ Grover, L. K. (2005). Fixed-point quantum search. Physical Review Letters, 95(15), 150501.
+ Berry, D. W., Childs, A. M., & Kothari, R. (2015, October). Hamiltonian simulation with nearly optimal dependence on all parameters. In Foundations of Computer Science (FOCS), 2015 IEEE 56th Annual Symposium on (pp. 792-809). IEEE.

### Algorithms for quantum simulation

+ Lloyd, S. (1996). Universal Quantum Simulators. [Science (New York, NY), 273(5278), 1073](http://doi.org/10.1126/science.273.5278.1073).
+ Berry, D. W., Childs, A. M., Cleve, R., Kothari, R., & Somma, R. D. (2015). Simulating Hamiltonian dynamics with a truncated Taylor series. [Physical Review Letters, 114(9), 090502](http://doi.org/10.1103/PhysRevLett.114.090502).
+ Low, G. H., & Chuang, I. L. (2017). [Optimal Hamiltonian simulation by quantum signal processing](https://arxiv.org/abs/1606.02685). [Physical Review Letters, 118(1), 010501](http://doi.org/10.1103/PhysRevLett.118.010501).
+ Low, G. H., & Chuang, I. L. (2016). Hamiltonian simulation by qubitization. [arXiv preprint:1610.06546](https://arxiv.org/abs/1610.06546).
+ Reiher, M., Wiebe, N., Svore, K. M., Wecker, D., & Troyer, M. (2017). Elucidating reaction mechanisms on quantum computers. [Proceedings of the National Academy of Sciences, 201619152](http://doi.org/10.1073/pnas.1619152114).
+ Wiebe, N., Berry, D. W., Høyer, P., & Sanders, B. C. (2011). Simulating quantum dynamics on a quantum computer. [Journal of Physics A: Mathematical and Theoretical, 44(44), 445308](http://doi.org/10.1088/1751-8113/44/44/445308).
+ Peruzzo, A., McClean, J., Shadbolt, P., Yung, M. H., Zhou, X. Q., Love, P. J., ... & Obrien, J. L. (2014). A variational eigenvalue solver on a photonic quantum processor. [Nature communications, 5](http://doi.org/10.1038/ncomms5213).

### Procedures for quantum optimization

+ Durr, C., & Høyer, P. (1996). A quantum algorithm for ﬁnding the minimum. arXiv preprint quantph/9607014.
+ Farhi, E., Goldstone, J., & Gutmann, S. (2014). A quantum approximate optimization algorithm. arXiv preprint arXiv:1411.4028.
+ Brandao, F. G., Svore, K. M. (2017). Quantum Speed-ups for Semideﬁnite Programming. In Annual Symposium on Foundations of Computer Science (FOCS 2017).
