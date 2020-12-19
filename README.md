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

below are some common orders of growth along with descriptions and examples where possible.

#### O(1)

O(1) describes an algorithm that will always execute in the same time (or space) regardless of the size of the input data set.Here are the examples of Algorithms/Group of Statements with Time complexity O(1):

Following works gives `O(1)` time complexity:

   - Accessing Array Index (arr[0]).
   - Inserting a node in Linked List.
   - Pushing and Poping on Stack.
   - Insertion and Removal from Queue.
   - Finding out the parent or left/right child of a node in a tree stored in Array.
   - Jumping to Next/Previous element in Doubly Linked List.
   
    int IsFirstElementNull(IList<string> elements)
    {
        return elements[0];
    }
   
#### O(N)

`O(N)` describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set.`All Brute Force Algorithms`,which require linearity, are based on O(n) time complexity.

Following works gives `O(N)` time complexity:


   - Traversing an array
   - Traversing a linked list
   - Linear Search
   - Deletion of a specific element in a Linked List (Not sorted)
   - Comparing two strings
   - Checking for Palindrome
   - Counting/Bucket Sort and here too you can find a million more such examples....

    bool ContainsValue(IList<string> elements, string value)
    {
        foreach (var element in elements)
        {
            if (element == value) return true;
        }

        return false;
    }
    
#### O(N^2)    

O(N^2) represents an algorithm whose performance is directly proportional to the square of the size of the input data set. This is common with algorithms that involve nested iterations over the data set. Deeper nested iterations will result in O(N^3), O(N^4) etc.

Following works gives `O(N^2)` time complexity:


   - Bubble Sort
   - Insertion Sort
   - Selection Sort
   - Traversing a simple 2D array

    bool ContainsDuplicates(IList<string> elements)
    {
        for (var outer = 0; outer < elements.Count; outer++)
        {
            for (var inner = 0; inner < elements.Count; inner++)
            {
                
                if (outer == inner) continue;

                if (elements[outer] == elements[inner]) return true;
            }
        }

        return false;
    }

#### O(log N)

The best example of having this complexity is Binary Search algorithm.To read more about Binary Search algorithm [click here](https://en.wikipedia.org/wiki/Binary_search_algorithm).

### Properties of Big-O Notation

While analyzing algorithm using big-O, there are a few properties that will help to determine the upper bound of the running time of algorithm.

#### Property 1(Coefficients):

If `f(n)` is `x * g(n)` then `f(n)` is `O(g(n))`.This allow the coefficient (x) to be dropped.

Example:

    f(n) = 100*g(n)
    then f(n) is O(n)
    
#### Property 2(Sum):

If `f1(n)` is `O(g(n))` and `f2(n)` is `O(g(n))` then `f1(n) + f2(n)` is `O(g(n))`

This property is useful when an algorithm contains several loops of the same order.

Example:

    f1(n) is O(n)
    f2(n) is O(n)
    then f1(n) + f2(n) is O(n) + O(n), Which is O(n).
    
#### Property 3(Sum):

If `f1(n)` is `O(g1(n))` and `f2(n)` is `O(g2(n))` then `f1(n) + f2(n)` is `O(max(g1(n),g2(n)))`. This property works because we are only concerned with the term of `highest growth rate`.

Example:

    f1(n) is O(n^2)
    f2(n) is O(n)
    so f1(n) + f2(n) = n^2 + n is O(n^2)
    
#### Property 4(Multiply):

If `f1(n)` is `(g1(n))` and `f2(n)` is `O(g2(n))` then `f1(n) * f2(n)` is `O(g1(n)) * O(g2(n))`.This property is useful for analyzing segments of an algorithm with nested loops.

Example:

    f1(n) is O(n^2)
    f2(n) is O(n)
    then f1(n) * f2(n) is O(n^2) * O(n), Which is O(n^3)
