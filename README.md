# Complexity_Of_Algorithm

### Analysis of Algorithms

There are a number of important practical reasons for `analyzing algorithms`. The most straigntforward reason for analyzing
an algorithm is to discover it characteristics `in order to evaluate its suitability` for various applications or compare it with other algorithms for the same application.Moreover, the analysis of an algorithms can help us understand it better, and can suggest informed improvements.

#### Algorithm

An algorithm is a `set of instructions that can be executed in finite amount of time to perform some task`.Several Properties may be considered to determine if one algorithm is better than another.Which are as follows:

- Time taken by the algorithm to run.
- Space or memory it consumes while it runs.

#### Algorithm Efficiency

Efficiency of an algorithm can be measured in terms of execution time that is time complexity and the amount of memory required that is space complexity.
Computer Scientists use different notations to characterize the runtime of an algorithm.The three notations are `O(n)`,  `Ω(n)`,  `Θ(n)` are pronounced `big-O`, `big-Omega`, `big-Theta` respectively.

- The `big-O` measurement represents the upper bound on the runtime of an algorithm, the algorithm will never run slower than the specified time.
- The `big-Omega` is symmetric to `big-O`.It is lower bound on the running time of an algorithm, the algorithm wil never run faster than the specified time.
- The `big-Theta` is the tighest bound that can be established for the runtime of an algorithm.It occurs When the `big-O` and `big-Omega` running times are the same, therefore it is known that the algorithm will never run faster or slower then the time specified.

### Computational Complexity
Complexity refers to the rate at which the required storage or consumed time grows as a function of the problem size.The absolute growth depends on the `machine` used to execute the program, the `complier` used to construct the program and many other factors.

#### Time Complexity

Time complexity is a measure of the amount of time required to execute an algorithm.Time complexity analysis for an algorithm is independent of programming language, machine used.Factor that should not affect time complexity analysis are:

- The programming language chosen to implement the algorithm.
- The quality of the complier.
- The speed of the computer on which the algorithm to be executed.

#### Space Complexity

The space complexity of an algorithm or a computer program is the amount of memory space required to solve an instance of the computational problem as a function of characteristics of the input. It is the memory required by an algorithm to execute a program and produce output.

Similar to time complexity, `space complexity` is often expressed asymptotically in big O notation,Whenever a solution to a problem is written some memory is required to complete. For any algorithm memory may be used for the following:

- Variables (This include the constant values, temporary values).
- Program Instruction.
- Execution.

Sometime `Auxiliary Space` is confused with `Space Complexity`. But `Auxiliary Space` is the extra space or the temporary space used by the algorithm during it's execution.

    Space Complexity = Auxiliary Space + Input space

### Asymptotic Notations:

The main idea of asymptotic analysis is to have a measure of `efficiency of algorithms` that doesn’t depend on machine specific constants, and doesn’t require algorithms to be implemented and `time taken by programs to be compared`. Asymptotic notations are mathematical tools to represent time complexity of algorithms for asymptotic analysis. The following 3 asymptotic notations are mostly used to represent time complexity of algorithms.

####  Big O Notation:

<img src="https://github.com/khageshwor/Complexity_Of_Algorithm/blob/main/img/BigO.png" width="700" height="500">

    O(g(n)) = { f(n): there exist positive constants c and 
                  n0 such that 0 <= f(n) <= c*g(n) for 
                  all n >= n0}
