# DAA

# Unit IV

👋 Intractable Problems and NP Completeness

## Tractable Problems

1. Solved in Polynomial Time
2. Worst case Time Complexity is O(n^k)
3. Sequential search : O(n), Binary Search : O(logn), Insertion Sort : O(n^2), Product of Two Matrices : O(n^3), Quick Sort : O(nlogn)

## Intractable Problems

1. Cannot be solved in Polynomial Time
2. Worst case time complexity is O(k^n)
3. 0-1 Knapsack: O(2^n), Traveling Salesperson Problem : O(n^2 * 2^n)

## Deterministic v Non-Deterministic

|  | Deterministic Algorithms | Non-Deterministic Algorithms |
| --- | --- | --- |
| Output | Produces a single output for every input | Can produce multiple outputs for the same input |
| Consistency | The output is always the same for a given input | The output can be different for the same input |
| Time Complexity | The time complexity can be calculated with certainty | The time complexity is not always known |
| Verification | The algorithm can be verified easily | The algorithm cannot be easily verified |

Examples of deterministic algorithms include binary search, linear search, and bubble sort.

Examples of non-deterministic algorithms include the traveling salesman problem, the knapsack problem, and the Boolean satisfiability problem. 

The general time complexity of deterministic algorithms is usually lower than that of non-deterministic algorithms.

## Decision v Optimization

|  | Decision Problems | Optimization Problems |
| --- | --- | --- |
| Goal | Determine whether a solution exists | Find the best solution |
| Output | Yes or No | Optimal Solution |
| Examples | Boolean Satisfiability, Hamiltonian Cycle Problem | Traveling Salesman Problem, Knapsack Problem |
| Time Complexity | Can be solved in polynomial time | Typically cannot be solved in polynomial time |

Decision problems require a binary (yes or no) answer, whereas optimization problems require finding the best solution from a set of possible solutions. Decision problems can often be solved in polynomial time, while optimization problems are typically NP-hard and cannot be solved in polynomial time.

Examples of decision problems include the Boolean satisfiability problem and the Hamiltonian cycle problem. Examples of optimization problems include the traveling salesman problem and the knapsack problem.

The time complexity of decision problems can often be calculated with certainty, while the time complexity of optimization problems is typically unknown.

## P vs NP

|  | P Class Problems | NP Class Problems |
| --- | --- | --- |
| Definition | Problems that can be solved in polynomial time | Problems whose solutions can be verified in polynomial time |
| Example | Sorting, Shortest Path, Minimum Spanning Tree | Traveling Salesman, Knapsack, Vertex Cover |
| Time Complexity | O(n^k) | O(2^n), O(n^2 * 2^n), O(3^n) |
| Solution | Solutions can be found efficiently | Solutions cannot be found efficiently |

While solutions to NP class problems can be verified in polynomial time, finding the solutions themselves is generally considered intractable. In other words, there is no known algorithm that can solve an NP class problem in polynomial time.

Any P class problem can be solved using NP class algorithm. Therefore P is contained in NP class

## P v NP v NP Complete v NP Hard

|  | P Class Problems | NP Class Problems | NP Complete Problems | NP Hard Problems |
| --- | --- | --- | --- | --- |
| Definition | Problems that can be solved in polynomial time | Problems whose solutions can be verified in polynomial time | NP problems that are also in P class | NP problems that are at least as hard as NP Complete problems |
| Example | Sorting, Shortest Path, Minimum Spanning Tree | Traveling Salesman, Knapsack, Vertex Cover | Boolean satisfiability problem, Hamiltonian path problem | 3-SAT, Subset sum, Graph colouring |
| Time Complexity | O(n^k) | O(2^n), O(n^2 * 2^n), O(3^n) | O(2^n), O(n^2 * 2^n), O(3^n) | O(2^n), O(n^2 * 2^n), O(3^n) |
| Solution | Solutions can be found efficiently | Solutions cannot be found efficiently | Solutions cannot be found efficiently, but can be verified efficiently | Solutions cannot be found efficiently, and may be difficult to verify |
| Implication | Efficient algorithms exist | Efficient algorithms may not exist | NP Complete problems are the most difficult problems in NP class | NP Hard problems are at least as hard as NP Complete problems |

While P class problems can be solved in polynomial time, NP class problems are generally considered intractable. NP complete problems are the most difficult problems in the NP class, as they are both NP problems and NP hard. NP hard problems are at least as hard as NP complete problems, but may not necessarily be part of the NP class.

**NP hard problems are basically the optimization versions of the problems in NP complete class**

## Satisfiability Problem

- The Satisfiability Problem is about finding whether a Boolean formula is true for some values of truth for the variables.
- CNF-Satisfiability is the Satisfiability Problem for a CNF formula.
- The time complexity for Satisfiability and CNF-Satisfiability (for a deterministic algorithm) is O(2^n), where ‘n’ is the total number of Boolean variables in the formula.
- A non-deterministic algorithm can be easily developed that can run in polynomial time and finish successfully if the given propositional formula E(x1,x2, …,xn) is satisfiable.
- This algorithm can simply pick (in a non-deterministic manner) one of the (2^n) possible truth value assignments to (x1,x2, …,xn) and then verify if E(x1,x2, …,xn) is true for that assignment.

## **Non-deterministic Algorithm to Solve Satisfiability Problem**

```
**Algorithm:** Eval(E,n)
**//** Determine whether the propositional formula E is satisfiable
for i = 1 to n do
    xi = choice(false, true);
    if E(x1, x2, ..., xn) then success()
    else failure();
```

### **Analysis:**

Time complexity = O(n), i.e. polynomial time. Therefore, "Satisfiability is in NP"

Hence, **Satisfiability is NP-Complete.**

## ****NP-Hard Problems : Reduction of Problem****

To demonstrate that a problem L2 is NP-hard, we can follow the following strategy:

1. Select a problem L1 that is already known to be NP-hard.
2. Show how to transform any instance I of L1 into an instance I' of L2 in polynomial deterministic time.
3. Demonstrate that given the solution to I', we can determine the solution to I in polynomial deterministic time.
4. Conclude that L1 α L2 (L1 is polynomial-time reducible to L2) based on steps 2 and 3.
5. Since L1 is NP-hard and L1 α L2, we can use the transitivity of α to conclude that L2 is also NP-hard.

It is worth noting that all NP-hard decision problems discussed in this context are NP-complete, which means a polynomial-time non-deterministic algorithm can be provided for L2.

## Clique Decision Problem:

The Clique Decision Problem (CDP) is concerned with finding maximal complete sub-graphs, known as cliques, in a given graph G = (V, E). The size of a clique is determined by the number of vertices it contains. The Maximum Clique Problem is an optimization problem that aims to determine the size of the largest clique in G.

Here are the applications of graph theory in various fields

- Patterns in telecommunications traffic
- Design of error-correcting codes
- Fault diagnosis on large multiprocessor systems
- Tiling geometry problems (Keller's conjecture)
- Computer Vision and Pattern Recognition
- Graph theoretic approaches in modern Biological Research

![Screenshot 2023-05-20 at 8.27.48 PM.png](DAA%2060123486700c43d5b131c652d5370df3/Screenshot_2023-05-20_at_8.27.48_PM.png)

Create a logical expression using three variables of SAT

![Screenshot 2023-05-20 at 8.31.53 PM.png](DAA%2060123486700c43d5b131c652d5370df3/Screenshot_2023-05-20_at_8.31.53_PM.png)

Group them as clauses

![Screenshot 2023-05-20 at 8.35.17 PM.png](DAA%2060123486700c43d5b131c652d5370df3/Screenshot_2023-05-20_at_8.35.17_PM.png)

Rules for Vertex and Edge

- We can’t connect a vertex (V) with another vertex (W) in the same clause.
- We can’t connect a vertex (v) with another vertex (~v)

![Screenshot 2023-05-20 at 8.33.58 PM.png](DAA%2060123486700c43d5b131c652d5370df3/Screenshot_2023-05-20_at_8.33.58_PM.png)

Connect the edges and complete the graph

![Screenshot 2023-05-20 at 8.35.49 PM.png](DAA%2060123486700c43d5b131c652d5370df3/Screenshot_2023-05-20_at_8.35.49_PM.png)

As we had taken 3 variables we decide clique (k = 3)

![Screenshot 2023-05-20 at 8.36.15 PM.png](DAA%2060123486700c43d5b131c652d5370df3/Screenshot_2023-05-20_at_8.36.15_PM.png)

Lastly we label the selected vertices and assign them a value and cross-check by substituting these values in the logical expression.

Hence we can say that SAT α CDP and therefore, CDP is NP HARD.

## CDP: Non-Deterministic Algorithm

```java
Algorithm CDP(G, n, k) {
    // G is an adjacency matrix, |V| = n, and clique size is k
    // The algorithm determines whether there exists a clique of size ≥ k in graph G

        S = Ø;                        // initially, S is empty
        for (i = 1; i ≤ k; i++) {
            t = Choice(1, n);
            if (t ∈ S)
                Failure();
            S = S ∪ {t};               // add t to S
        }

        // At this point, S contains k distinct vertices
        for (all pairs (i, j) such that vertices i and j ∈ S and i ≠ j) {
            if ((i, j) is not an edge of G)
                Failure();
        }

        Success();
    }

// In general, if k = (n/2),
// Time Complexity is O((n/2) + (n/2)^2) = O(n^2) = O(m), m = input length.
```

## Node Cover Decision Problem (Vertex Cover Problem)

**The Clique Decision Problem (CDP) α Node Cover Decision Problem or the vertex cover problem is NP-Complete.**

1. The Clique Decision Problem (CDP) involves determining whether a given graph G contains a clique of size at least k.
2. The Node Cover Decision Problem (NCDP) or the Vertex Cover Problem requires finding the smallest set of vertices that covers all the edges in a given graph G.
3. We need to show that we can transform an instance of CDP into an instance of NCDP in polynomial time, and the solution to the transformed instance of NCDP can be used to determine the solution to the original instance of CDP.
4. Given an instance of CDP, we construct an instance of NCDP as follows:
    - For each vertex v in G, create a corresponding vertex v' in the new graph.
    - For each edge (u, v) in G, create a new edge (u', v') in the new graph.
5. By construction, the size of the maximum clique in G is equivalent to the complement of the size of the minimum vertex cover in the new graph.

![Screenshot 2023-05-20 at 9.13.45 PM.png](DAA%2060123486700c43d5b131c652d5370df3/Screenshot_2023-05-20_at_9.13.45_PM.png)

![Screenshot 2023-05-20 at 9.14.20 PM.png](DAA%2060123486700c43d5b131c652d5370df3/Screenshot_2023-05-20_at_9.14.20_PM.png)

Therefore, if we can solve NCDP for the transformed instance, we can determine the solution to the original CDP instance.

Since the NCDP is known to be NP-complete, by demonstrating the reduction from CDP to NCDP, we establish that CDP is also NP-complete.

In summary, by showing the polynomial-time reduction from CDP to NCDP and utilising the NP-completeness of NCDP, we can conclude that the Clique Decision Problem is NP-complete.

# UNIT V

👋 Approximation and Randomisation

A video that explains TSP, NN and `Cristofides` Algorithm.

[https://www.youtube.com/watch?v=GiDsjIBOVoA](https://www.youtube.com/watch?v=GiDsjIBOVoA)

## Approximation Algorithms

- An approximation algorithm aims to find a feasible solution to a given problem P that has a value F^(I) that is less than the optimal solution's value F*(I), assuming P is a maximisation problem.
- An "Absolute Approximation" algorithm A satisfies the condition |F*(I) - F^(I)| ≤ k, where k is a constant.
- An "f(n)-approximation algorithm" A guarantees that for every instance I of size n, the ratio |F*(I) - F^(I)| / F*(I) ≤ f(n) holds, given that F*(I) > 0.
- An "∈-approximate algorithm" is an approximation algorithm for which f(n) ≤ ∈, where ∈ is a small positive constant.
- Most approximate algorithms fall into the category of absolute approximation algorithms, ensuring that the generated feasible solution falls within a constant difference from the optimal solution's value.
- Approximate algorithms are heuristics that guarantee generating feasible solutions with values that are close to the optimal solution, typically within a specific constant difference or ratio.

## Approximate Solution for (TSP) using MST and Triangle Inequality:

1. The Traveling Salesman Problem (TSP) is a classic optimization problem where the objective is to find the shortest possible route that visits each given city exactly once and returns to the starting city.
2. The TSP is known to be an NP-hard problem, meaning there is no known efficient algorithm to solve it optimally in polynomial time.
3. However, there are approximation algorithms that can provide reasonably good solutions within a certain factor of the optimal solution.

### MST-Based Approximation Algorithm:

- The algorithm starts with vertex 1 as the starting and ending point for the tour.
- It constructs an MST using Prim's Algorithm, considering vertex 1 as the root.
- The MST represents a tree that connects all the cities with the minimum total edge weight.
- The algorithm performs a preorder walk on the MST, listing the visited vertices in the order they are encountered.
- Vertex 1 is added at the end of the list to complete the tour by returning to the starting city.
- The resulting list of vertices represents an approximate solution to the TSP.

### Triangle Inequality Property:

1. The Triangle Inequality property states that the shortest path between any two cities is always the straight line connecting them or a direct edge between them.
2. In the TSP, this means that if we have three cities A, B, and C, the direct path from A to B plus the direct path from B to C will always be shorter than or equal to the path from A to C.
3. The Triangle Inequality property holds for most real-world scenarios, making it a valuable property to exploit in approximation algorithms.

### Notes:

- The MST-based approximation algorithm for the TSP guarantees a tour length that is at most twice the length of the optimal solution.
- The algorithm relies on constructing an MST, which can be efficiently done using algorithms like Prim's or Kruskal's algorithm.
- The Triangle Inequality property is crucial in ensuring that the obtained tour length is not excessively larger than the optimal solution.
- While the MST-based approximation algorithm provides a reasonable solution, it is not guaranteed to find the optimal solution in all cases.
- Various refinements and heuristics can be applied to improve the performance and accuracy of the approximate solutions for the TSP.
- The cost of the best possible TSP tour is never less than the cost of the MST. (MST is a minimum cost tree that connects all vertices).
- The total cost of the full walk (a walk that lists all vertices in preorder, including when they are returned after visiting a subtree) is at most twice the cost of the MST. (Every edge of the MST is visited at most twice).

![Untitled](DAA%2060123486700c43d5b131c652d5370df3/Untitled.png)

![Untitled](DAA%2060123486700c43d5b131c652d5370df3/Untitled%201.png)

[https://www.geeksforgeeks.org/approximate-solution-for-travelling-salesman-problem-using-mst/](https://www.geeksforgeeks.org/approximate-solution-for-travelling-salesman-problem-using-mst/)

## Las Vegas v Monte Carlo

| Monte Carlo Problem | Las Vegas Problem |
| --- | --- |
| Based on statistical sampling and randomisation. | Based on deterministic algorithms with random inputs. |
| The output is probabilistic and may contain errors. | The output is deterministic, either correct or undefined. |
| Solutions are typically obtained through sampling and statistical analysis. | Solutions are obtained by executing the algorithm multiple times and checking for correctness. |
| The algorithm provides an approximate solution with a certain level of confidence. | The algorithm provides an exact solution if it terminates. |
| Examples include Monte Carlo integration, Monte Carlo simulation, and probabilistic algorithms. | Examples include Las Vegas algorithms, randomisation-based algorithms, and randomised algorithms. |
| Typically used for optimization problems where an exact solution is not required. | Typically used for decision problems where an exact solution is required. |
| The running time of Monte Carlo algorithms can vary depending on the desired level of accuracy. | The running time of Las Vegas algorithms can vary depending on the input and the number of repetitions. |
| Can handle problems with large solution spaces efficiently. | May have higher time complexity compared to deterministic algorithms. |
| Useful when the problem is computationally intractable or when an exact solution is not feasible. | Useful when it is important to guarantee the correctness of the solution. |

## Analysis

The given problem involves grading a class of students, assigning them grades A or D based on their performance in an exam. The problem makes several assumptions, including the number of students in the class (s) and the number of questions on the exam (q).

The problem provides two algorithms for grading the students, each with its own analysis.

### Algorithm 1:

This algorithm assumes that Aces (top-performing students) solve all q questions correctly, while Duds (poor-performing students) solve less than q/2 questions correctly. The algorithm checks at most the first q/2 questions of each student's paper. If any wrong answer is found, the student is given a grade D. If all q/2 questions are answered correctly, the student is given a grade A.

### Analysis of Algorithm 1:

The algorithm will always give the correct answer for grading.
The time complexity of the algorithm is O(sq/2), as it needs to check at most q/2 questions for each of the s students.

### Algorithm 2:

This algorithm takes a different approach. It selects a random set of 10 questions for each student and grades them based on their performance on those questions. If any wrong answer is found, the student is given a grade D. If all 10 questions are answered correctly, the student is given a grade A.

### Analysis of Algorithm 2:

The algorithm will always give the correct answer for grading.
The running time of the algorithm may vary greatly, as it depends on the performance of the students and the randomly selected questions.
The expected running time can be defined as E[RT(p)], where RT(p) is the time for grading paper "p" and E[RT(p)] is the maximum expected running time among all papers of length q.
The expected running time, T(q), will not grow as fast as O(sq/2).

The problem also **highlights** the advantages of randomised algorithms:

1. Simplicity: Randomised algorithms are generally simpler than their deterministic counterparts for the same problem.
2. Speed: Randomised algorithms can be faster, and there is a possibility of achieving polynomial time complexity.
3. De-randomisation: Some randomised algorithms can be "de-randomised" to obtain deterministic algorithms.
4. Different approaches: Randomised algorithms provide different paradigms for designing algorithms, allowing for innovative solutions.

In summary, the problem discusses two algorithms for grading students, their analysis, and the advantages of randomised algorithms in terms of simplicity, speed, and design approaches.

## Randomised Quick Sort

- Randomised Quick Sort is a variation of the Quick Sort algorithm designed to address the worst-case time complexity of O(n^2) that can occur in regular Quick Sort.
- The algorithm starts by randomly selecting an element 'y' from the input set S, which will serve as the pivot for partitioning.
- The set S is then split into two subsets: S1, containing elements smaller than 'y', and S2, containing elements larger than 'y'.
- If S1 is not empty, the Randomised Quick Sort algorithm recursively applies the same process to sort S1 in increasing order.
- Once S1 is sorted, the pivot 'y' is outputted.
- If S2 is not empty, the algorithm recursively applies the same process to sort S2 in increasing order, independent of S1 and 'y'.
- The algorithm concatenates the sorted S1, 'y', and the sorted S2 to obtain the final sorted elements of S.
- The algorithm utilises a helper function called `RANDOMIZED_PARTITION`, which randomly selects an index 'i' and swaps the element at index 'p' with the element at index 'i'.
- The `RANDOMIZED_QUICKSORT` function serves as the entry point for the algorithm and recursively applies the Randomised Quick Sort process to subarrays.
- By introducing randomisation in the pivot selection, the Randomised Quick Sort algorithm reduces the likelihood of encountering the worst-case scenario and improves the average time complexity to O(n log n).

## Evolutionary Algorithms

Evolutionary Computing and Evolutionary Algorithms are computational methods inspired by the principles of natural evolution. They are used to solve optimization and search problems in various domains.

1. Evolutionary Computing:
    - Evolutionary Computing is a field of study that draws inspiration from biological evolution to develop computational techniques.
    - It encompasses a broad range of algorithms and methods that mimic the natural evolutionary processes, such as selection, reproduction, and mutation.
    - The goal of Evolutionary Computing is to solve complex problems by iteratively improving a population of candidate solutions over generations.
    - It is a heuristic, population-based search approach that can handle complex, non-linear, and multi-modal optimization problems.
2. Evolutionary Algorithms (EAs):
    - Evolutionary Algorithms are a class of algorithms that fall under the umbrella of Evolutionary Computing.
    - They are widely used in optimization and search problems, as they can efficiently explore large search spaces and find near-optimal solutions.
    - EAs employ a population of individuals (candidate solutions) that undergo selection, reproduction, and variation processes to evolve and adapt to the problem at hand.
    - The key components of an EA are the representation of individuals, a fitness function to evaluate their quality, and genetic operators (e.g., mutation and crossover) to generate new individuals.
    - EAs iteratively generate new populations by selecting individuals with higher fitness values and applying genetic operators to create offspring.
    - The population evolves over generations, and the algorithm continues until a stopping criterion is met or a satisfactory solution is found.
3. Popular Evolutionary Algorithms:
    - Genetic Algorithm (GA): One of the most well-known evolutionary algorithms that uses selection, crossover, and mutation operators.
    - Genetic Programming (GP): Similar to GA, but evolves computer programs or mathematical expressions instead of fixed-length strings.
    - Evolutionary Strategies (ES): Focuses on self-adaptation and uses mutation-based search with strategy parameters.
    - Particle Swarm Optimization (PSO): Inspired by the behaviour of bird flocks or fish schools, it optimises a population of particles using social and cognitive influences.
    - Ant Colony Optimization (ACO): Inspired by the behaviour of ants, it simulates the foraging behaviour of ants to find optimal paths in a graph.
    - Differential Evolution (DE): Utilises a mutation and crossover strategy to generate new solutions and improve the population.

![Screenshot 2023-05-21 at 5.40.20 PM.png](DAA%2060123486700c43d5b131c652d5370df3/Screenshot_2023-05-21_at_5.40.20_PM.png)

## Genetic Algorithm (GA)

- A genetic algorithm is a search heuristic inspired by Charles Darwin's theory of natural evolution.
- It reflects the process of natural selection, where the fittest individuals are selected for reproduction to produce the next generation's offspring.
- Genetic algorithms are used for problem-solving, particularly in optimization and search tasks.
- The algorithm operates on a population of candidate solutions.
- Each candidate solution is represented as a set of parameters or genes.
- The algorithm uses probabilistic mechanisms inspired by natural genetics and evolution to iteratively improve the population.
- Selection is based on the fitness of individuals, with fitter individuals having a higher chance of being selected for reproduction.
- Reproduction involves combining genetic information from selected parents through genetic operators such as crossover and mutation.
- The offspring replace some individuals in the population, and the process continues until a termination condition is met.
- Genetic algorithms are flexible and can be applied to a wide range of problem domains.
- They have been successfully used for optimization, parameter tuning, and machine learning tasks.
- However, genetic algorithms do not guarantee finding the global optimum and their performance can be influenced by factors such as genetic operators and problem representation.

![Screenshot 2023-05-21 at 6.17.04 PM.png](DAA%2060123486700c43d5b131c652d5370df3/Screenshot_2023-05-21_at_6.17.04_PM.png)

## Steps involved in GA

1. Initialisation:
    - Define the problem's representation: Determine how to encode potential solutions into a chromosome or genotype, such as a binary string or a real-valued vector.
    - Generate an initial population: Create a set of random candidate solutions, with each solution represented as an individual in the population.
2. Evaluation:
    - Evaluate the fitness: Assign a fitness value to each individual in the population based on their performance in the problem domain. The fitness function measures how well a solution solves the problem.
3. Selection:
    - Select parents: Choose individuals from the current population for reproduction based on their fitness. Individuals with higher fitness are more likely to be selected, using methods like roulette wheel selection, tournament selection, or rank-based selection.
4. Reproduction:
    - Crossover: Create new offspring by combining genetic material from selected parents. Crossover involves swapping or combining segments of the parent chromosomes to produce one or more offspring.
    - Mutation: Introduce random changes in the offspring's genetic material. Mutation helps maintain genetic diversity in the population and allows for exploration of new regions in the search space.
5. Replacement:
    - Create a new population: Combine the offspring with the existing population, either by replacing some individuals or by using elitism (keeping the best individuals) to ensure that the best solutions persist across generations.
6. Termination:
    - Check termination condition: Determine if the algorithm should stop based on some predefined criterion. This could be reaching a maximum number of generations, finding a satisfactory solution, or not making significant progress over several iterations.
7. Repeat:
    - If the termination condition is not met, go back to step 2 and continue the iteration process.
    - Repeat steps 2 to 6 until the termination condition is satisfied.

## GA Operators

1. Encoding: Determining how to represent a solution within the framework of the genetic algorithm.
2. Convergence: Establishing the termination criterion to decide when the algorithm has reached a satisfactory solution.
3. Mating pool: Generating the set of potential solutions for the next generation through selection and reproduction.
4. Fitness Evaluation: Assessing the quality or fitness of each solution based on its performance in the problem domain.
5. Crossover: Creating diverse offspring by combining genetic material from selected parent solutions.
6. Mutation: Introducing random changes to explore different solutions and avoid getting stuck in local optima.
7. Inversion: Facilitating movement between different optima by altering the genetic material within a solution.

## Types of Encoding

1. Binary Encoding:
    - Binary encoding represents solutions as strings of binary digits (0s and 1s).
    - Each variable or gene is encoded using a fixed number of bits.
    - Well-suited for problems with discrete or categorical variables.
    - Genetic operators like crossover and mutation are applied to the binary strings.
    - Example Problem: The Knapsack Problem, where each bit represents whether an item is included or not.
2. Integer Encoding:
    - Integer encoding represents solutions as sequences of integers.
    - Each variable or gene is encoded as an integer within a predefined range.
    - Useful for problems with a finite set of possible integer values.
    - Genetic operators can manipulate the integer values to create new solutions.
    - Example Problem: The Job Scheduling Problem, where integers represent the order of job execution.
3. Real-Value Encoding:
    - Real-value encoding represents solutions as real numbers within a specific range.
    - Variables are encoded using floating-point or fixed-point representations.
    - Suitable for problems with continuous variables or a large search space.
    - Genetic operators are designed to work with real numbers, enabling exploration of the continuous search space.
    - Example Problem: The Function Optimization Problem, where real values represent variables to optimise a function.
4. Permutation Encoding:
    - Permutation encoding is used when the order or arrangement of elements matters.
    - Solutions are represented as permutations or orderings of a set of elements.
    - Applicable to problems like traveling salesman or scheduling where the sequence matters.
    - Genetic operators must preserve the order of elements during reproduction.
    - Example Problem: The Traveling Salesman Problem, where permutations represent the order of cities to visit.
5. Tree Encoding:
    - Tree encoding represents solutions as hierarchical structures or trees.
    - Well-suited for problems that involve hierarchical relationships or complex representations.
    - Each node in the tree corresponds to a variable or gene, and the tree structure captures the solution's relationships.
    - Genetic operators manipulate the tree structure through subtree crossover and mutation.
    - Example Problem: The Genetic Programming Problem, where trees represent mathematical expressions or programs.
6. Order Encoding:
    - Order encoding is used when the relative order of elements is important in the solution.
    - Solutions are represented as a fixed-length string, where each element corresponds to a position in the order.
    - Suitable for problems where the order of elements matters, such as sequence alignment or job scheduling.
    - Genetic operators, such as crossover and mutation, operate on the order of elements to generate new solutions while maintaining the order constraints.
    - Example Problem: The Traveling Salesman Problem, where the order of cities to visit is crucial.

## Different Selection Strategies in Genetic Algorithms:

1. Canonical Selection (Proportionate-Based Selection):
    - Also known as Proportional Selection.
    - Selection probability of an individual is proportional to its fitness value.
    - Individuals with higher fitness have a higher chance of being selected.
    - Commonly used with fitness scaling techniques like Roulette Wheel selection.
2. Roulette Wheel Selection (Proportionate-Based Selection):
    - Each individual is assigned a slice on a roulette wheel based on their fitness.
    - The size of the slice is proportional to their fitness value.
    - Selection is done by spinning the wheel and selecting the individual where the pointer lands.
    - Individuals with higher fitness have larger slices and are more likely to be selected.
3. Rank-Based Selection (Ordinal-Based Selection):
    - Individuals are ranked based on their fitness, from best to worst.
    - Selection is based on the rank rather than the fitness value.
    - Higher-ranked individuals have a higher probability of being selected.
    - Helps in maintaining diversity by giving a chance to less fit individuals.
4. Tournament Selection:
    - Individuals are randomly chosen in groups (tournaments) of fixed size.
    - The fittest individual from each tournament is selected.
    - Tournament size influences the selection pressure (larger size increases pressure).
5. Steady-State Selection:
    - Selects individuals in each generation to form the next population.
    - Typically, a fixed number of individuals are selected and replaced.
    - Often used in conjunction with other selection strategies.
6. Boltzmann Selection:
    - Selection probability is based on the Boltzmann distribution formula.
    - Selection pressure decreases over time, allowing exploration in the early stages.
    - Useful when searching for global optima in complex landscapes.
7. Elitism 
    
    Elitism is a strategy commonly used in the selection phase of genetic algorithms to preserve the best individuals from one generation to the next. Here are three key points about elitism in genetic algorithm selection:
    
    - Preservation of Elite Individuals: Elitism involves selecting a certain number of the best individuals, also known as the elite individuals, from the current generation and directly transferring them to the next generation without any changes. By doing so, the best solutions found so far are preserved across generations.
    - Promoting Genetic Diversity: While elitism preserves the best individuals, it also allows for the introduction of new genetic material into the next generation through other selection mechanisms, such as tournament selection or roulette wheel selection. This helps maintain genetic diversity within the population, preventing premature convergence to suboptimal solutions.
    - Ensuring Steady Progress: The primary purpose of elitism is to ensure steady progress in the optimization process. By preserving the best individuals, elitism guarantees that the overall quality of solutions does not deteriorate from one generation to the next. It acts as a mechanism to anchor the population around promising solutions and provides a strong foundation for further exploration and improvement.

## Different Crossover Operators in Genetic Algorithms

1. Single-Point Crossover:
    - Involves selecting a random point along the parent chromosomes.
    - The genetic material is exchanged between the parents at that point.
    - Generates two offspring by combining the genetic material before and after the crossover point.
2. Two-Point Crossover:
    - Similar to single-point crossover, but involves selecting two random points.
    - The genetic material between the two points is exchanged between the parents.
    - Generates two offspring with a segment from one parent and the remaining segments from the other parent.
3. Multi-Point Crossover (N-Point Crossover):
    - Involves selecting multiple random points along the parent chromosomes.
    - The genetic material between the points is exchanged between the parents.
4. Uniform Crossover (UX):
    - Each bit or gene is independently selected from one of the parents.
    - The selection is done randomly with equal probability for each parent.
5. Half-Uniform Crossover (HUX):
    - Similar to uniform crossover, but ensures that at least half of the genes come from each parent.
6. Shuffle Crossover:
    - Randomly shuffles the genetic material of both parents.
7. Matrix Crossover (Two-Dimensional Crossover):
    - Primarily used for problems where the solutions are represented as matrices or grids.
    - Involves exchanging sub-matrices or sub-grids between the parents.
    - Maintains the structure and patterns present in the parent solutions.
8. Three-Parent Crossover:
    - Involves selecting genetic material from three parents.
    - The genetic material is combined in a specific manner to generate offspring.
9. Partially Mapped Crossover (PMX):
    - PMX is a crossover operator used in genetic algorithms for permutation-based problems.
    - It involves selecting a random section from one parent and mapping the corresponding section from the other parent while maintaining the order of the elements outside the section.
10. Position-Based Crossover (PBC):
    - PBC is a crossover operator commonly used for permutation-based problems.
    - It involves selecting random positions in the parents' chromosomes and swapping the elements at those positions to create offspring.
11. Precedence-Preservation Crossover (PPX):
    - PPX is a crossover operator specifically designed for scheduling problems where tasks have precedence constraints.
    - It ensures that the offspring maintains the precedence relationships of tasks inherited from both parents.
    - PPX is useful in optimization problems where the order of task execution is crucial, ensuring that the offspring remains feasible and respects the task dependencies.
12. Edge Recombination Crossover (ERX):
    - ERX is a crossover operator used for graph-based problems, particularly the traveling salesman problem (TSP).
    - It creates offspring by merging the edge sets of the parents while ensuring that each city is connected to at least one other city.
    - ERX promotes exploration of different paths in the TSP by combining the edge information from multiple parents.

## Simulated Annealing

1. Initialisation: Start with an initial solution to the optimization problem.
2. Define an objective function: Establish a function that evaluates the quality or cost of a given solution.
3. Set initial temperature: Assign an initial temperature that controls the acceptance of worse solutions.
4. Iterative process:
    - Perturbation: Make a small random change to the current solution, generating a new candidate solution.
    - Evaluation: Evaluate the objective function for the new candidate solution.
    - Acceptance criteria:
        - If the new solution is better (lower cost), accept it as the new current solution.
        - If the new solution is worse (higher cost), calculate a probability of acceptance based on the temperature and the degree of worsening.
        - Accept the worse solution with a certain probability (higher probability for higher temperature).
    - Cooling: Reduce the temperature according to a cooling schedule, typically a geometric or exponential function.
5. Termination condition: Repeat the iterative process until a stopping criterion is met (e.g., a maximum number of iterations or reaching a desired solution quality).
6. Return the best solution found throughout the iterations as the approximate global optimum.

Simulated annealing gradually explores the search space, allowing for the possibility of accepting worse solutions early on when the temperature is high. As the temperature decreases, the algorithm becomes more selective and converges towards better solutions. This stochastic acceptance mechanism helps simulated annealing escape local optima and discover the global optimum or a good approximation of it.

By utilising this iterative process and the concept of annealing, simulated annealing offers a powerful optimization technique for solving complex problems with large search spaces. It strikes a balance between exploration and exploitation, providing a flexible and effective approach to finding good solutions in various domains.

# Unit VI

👋 Parallel and Concurrent Algorithms

## Parallel v Concurrent

| Criteria | Parallel Algorithms | Concurrent Algorithms |
| --- | --- | --- |
| Execution Approach | Divide a task into subtasks that can be executed simultaneously | Manage multiple tasks simultaneously with overlapping execution |
| Goal | Improve performance by utilising multiple processors or cores | Handle multiple tasks concurrently without maximising performance |
| Dependency Handling | Typically independent tasks with minimal or no interdependencies | Tasks may have dependencies and need coordination or synchronisation |
| Communication and Synchronisation | Communication and synchronisation between tasks may be required | Communication and synchronisation between tasks is necessary |
| Resource Utilisation | Maximise utilisation of multiple processors or cores | Efficiently utilise available resources for multiple tasks |
| Scalability | Scalability is a significant factor as adding more processors can speed up execution | Scalability is essential to handle increasing task loads or concurrency |
| Granularity | Tasks can be fine-grained or coarse-grained based on the problem | Granularity depends on the concurrency requirements and task nature |
| Shared Memory Usage | Shared memory is commonly used for data sharing among tasks | Shared memory may be used for data sharing and communication |
| Example | Computing matrix multiplication using multiple cores simultaneously | Processing multiple user requests concurrently in a web server |

It is important to note that parallel and concurrent algorithms are not mutually exclusive, and a concurrent algorithm may also utilise parallelism to achieve efficient execution. The choice between parallel and concurrent algorithms depends on the specific problem, available resources, and desired performance characteristics.

## RAM v PRAM

| Criteria | RAM (Random Access Machine) | PRAM (Parallel Random Access Machine) |
| --- | --- | --- |
| Memory Model | Single shared memory | Multiple shared memories, one per processor |
| Processor Model | Single processor | Multiple processors executing in parallel |
| Communication | No explicit communication between processors | Explicit communication between processors through shared memory |
| Synchronisation | No explicit synchronisation between processors | Explicit synchronisation mechanisms (e.g., barriers, locks) |
| Concurrency | Limited concurrency due to a single processor | High degree of concurrency with multiple processors |
| Scalability | Limited scalability as it relies on a single processor | High scalability as it allows multiple processors |
| Complexity Management | Simpler to design and implement | More complex due to the need for communication and synchronisation |
| Parallelism Efficiency | Lower parallelism efficiency due to limited concurrency | Higher parallelism efficiency with multiple concurrent processors |
| Examples | Sequential algorithms executed on a single processor | Parallel algorithms executed on multiple processors |

## Fixed connection machine

A fixed connection machine is a parallel computing model where processors are connected in a specific network topology. In this model, each processor has a fixed set of connections to communicate with neighbouring processors, and the connections remain constant throughout the computation.

Here's a tabular comparison of three commonly used network topologies in fixed connection machines: Mesh, Hypercube, and Butterfly

| Network Topology | Mesh | Hypercube | Butterfly |
| --- | --- | --- | --- |
| Connectivity | Each processor is connected to its adjacent neighbours in a grid structure | Each processor is connected to log(n) other processors in a hypercube  | Each processor is connected to log(n) other processors in a mesh structure |
| Scalability | Easily scalable with additional processors | Scalable with logarithmic growth in the number of processors | Scalable with logarithmic growth in the number of processors |
| Routing Algorithm | Simple and localised routing algorithms | Efficient and direct routing algorithms based on binary representations | Efficient and direct routing algorithms based on connectivity |
| Fault Tolerance | Vulnerable to single link failures and limited redundancy | Highly fault-tolerant with logarithmic redundancy and alternate paths | Moderate fault tolerance with alternate paths |

## PRAM Variants

| Criteria | EREW (Exclusive Read Exclusive Write) | CREW (Concurrent Read Exclusive Write) | ERCW (Exclusive Read Concurrent Write) | CRCW (Concurrent Read Concurrent Write) |
| --- | --- | --- | --- | --- |
| Read Operations | Only one processor can read a memory location at a time | Multiple processors can read independently | Only one processor can read, but multiple can write | Multiple processors can read and write concurrently |
| Write Operations | Only one processor can write to a memory location at a time | Only one processor can write at a time | Multiple processors can write concurrently | Multiple processors can write concurrently |
| Read-Write Conflict Resolution | No conflict resolution required as only one read/write operation at a time | No conflict resolution required as only one write operation at a time | Conflict resolution required for concurrent writes | Conflict resolution required for concurrent writes |
| Concurrency | Limited concurrency due to exclusive read/write access | Limited concurrency due to exclusive write access | High concurrency due to concurrent write access | High concurrency due to concurrent read/write access |
| Synchronisation | No explicit synchronisation required | No explicit synchronisation required | Synchronisation required for concurrent writes | Synchronisation required for concurrent writes |
| Parallelism Efficiency | Lower parallelism efficiency due to limited concurrency | Lower parallelism efficiency due to limited concurrency | Higher parallelism efficiency with concurrent writes | Higher parallelism efficiency with concurrent operations |
| Complexity Management | Simpler to manage and avoid conflicts in algorithms | Simpler to manage and avoid conflicts in algorithms | More complex due to the need for synchronisation | More complex due to the need for synchronisation |
| Examples | Binary tree traversal algorithms | Exclusive locking mechanisms | Producer-consumer problem | Database concurrency control mechanisms |

## Types of CRCW

| Feature | Common CRCW PRAM | Arbitrary CRCW PRAM | Priority CRCW PRAM |
| --- | --- | --- | --- |
| Write Conflicts | All processors must write the same value | Only one processor can write arbitrarily | Highest priority processor writes |
| Write Operation | Concurrent writes from all processors | Only one processor can write at a time | Only highest priority processor can write |
| Conflict Resolution | Automatic resolution (by common value) | Arbitrary selection (one processor chosen) | Priority-based selection (highest priority) |
| Synchronisation | Not required (No write conflicts) | Required (Write conflicts must be resolved) | Required (Write conflicts must be resolved) |

## Amdahl’s Law

- Amdahl's Law is a fundamental principle in parallel computing that quantifies the potential speedup achievable by parallelizing a computation.
- The formula for Amdahl's Law is Speedup = 1 / [(1 - p) + (p / n)], where p is the proportion of the computation that can be parallelized, and n is the number of processors used.
- It provides insight into the limitations of parallelization when certain portions of a program cannot be parallelized.
- The speedup represents the improvement in execution time achieved by parallelizing the computation.
- Amdahl's Law highlights that the maximum achievable speedup is limited by the non-parallelizable portion of the computation.
- Even with an infinite number of processors, the non-parallelizable portion will always take the same amount of time.
- The formula shows that as the proportion of the computation that can be parallelized (p) increases or the number of processors (n) increases, the speedup improves.
- However, there is a diminishing return in speedup as p approaches its maximum value, indicating that the non-parallelizable portion becomes the bottleneck.
- Amdahl's Law emphasizes the importance of identifying and optimizing the parallelizable portion of a computation to achieve significant speedup.
- In practice, additional factors such as overhead, communication costs, and load balancing can impact the actual speedup achieved compared to the theoretical maximum calculated using Amdahl's Law.

Let's consider a program that consists of two parts:

1. Part A: Takes up 30% of the total execution time and is parallelizable.
2. Part B: Takes up the remaining 70% of the time and cannot be parallelized.

If we parallelize Part A on multiple processors, we can calculate the potential speedup using Amdahl's Law. Let's assume we have 10 processors.

Given:
p = 0.3 (30% can be parallelized)
n = 10 (number of processors)

Using the formula, we can calculate the speedup:

Speedup = 1 / [(1 - 0.3) + (0.3 / 10)]
= 1 / [0.7 + 0.03]
= 1 / 0.73
≈ 1.37

Therefore, by parallelizing Part A on 10 processors, we can achieve a speedup of approximately 1.37 times compared to the sequential execution.

## Brent’s Law

- Brent's Theorem, proposed by Richard P. Brent, provides a bound on the time complexity of parallel algorithms based on their sequential time complexity and the number of processors used.
- The theorem states that for a parallel algorithm with a sequential time complexity of T(n), the same problem can be solved on a parallel computer with p processors in a time complexity of at most T(n)/p + log(p) rounds.
- The time complexity reduction in the parallel algorithm is achieved by a factor of p, the number of processors, compared to the sequential time complexity.
- An additive term of log(p) is introduced in the parallel time complexity to account for the overhead of communication and synchronization between processors.
- The theorem allows estimation of the potential speedup achievable in parallel computation.

Here's an example to illustrate Brent's Theorem:

Suppose we have a problem that can be solved sequentially in O(n^2) time complexity, where n is the size of the problem. Using Brent's Theorem, we can estimate the time complexity of solving the same problem on a parallel computer with p processors.

Let's say we have p = 4 processors available for parallel execution. According to Brent's Theorem, the parallel algorithm's time complexity would be at most O(n^2/4 + log(4)).

The sequential algorithm requires O(n^2) operations, and when executed on a parallel computer with 4 processors, the time complexity becomes O(n^2/4 + 2) since log(4) = 2.

Therefore, using Brent's Theorem, we can conclude that the parallel algorithm would require at most O(n^2/4 + 2) time complexity, which is a significant improvement compared to the sequential time complexity of O(n^2).

## Tabular Format

| Difference | Amdahl's Law | Brent's Law |
| --- | --- | --- |
| Formula | Speedup = 1 / [(1 - p) + (p / n)] | Time complexity ≤ T(n)/p + log(p) |
| Focus | Measures speedup achieved by parallelization | Provides an upper bound on parallel time complexity |
| Considerations | Takes into account the proportion of parallelizable workload and the number of processors | Considers the sequential time complexity and the number of processors |
| Limitations | Assumes fixed problem size and proportion of parallelizable workload | Assumes fixed sequential time complexity and logarithmic overhead |
| Speedup Interpretation | Indicates the improvement in execution time achieved by parallelization | Indicates the factor by which the time complexity can be reduced in parallel computation |
| Proportion | Considers the fraction of the program that can run in parallel (p) | Doesn't explicitly consider the proportion of parallelizable workload |
| Processor Dependency | Considers the number of processors (n) used for parallel execution | Considers the number of processors (p) used for parallel execution |
| Maximum Speedup | Provides an upper bound on the achievable speedup | Provides an upper bound on the achievable time complexity reduction |
| Practical Considerations | May not fully account for factors like overhead, communication costs, and load balancing | Accounts for the overhead of communication and synchronization between processors |
| Example | Consider a program with 70% non-parallelizable workload. Speedup = 1 / [(1 - 0.7) + (0.7 / n)] | Consider a problem solved sequentially in O(n^2) time complexity. Brent's Law gives time complexity ≤ O(n^2/p + log(p)) |

## Parallel Algorithms Techniques

### Complete Binary Tree:

- The algorithm calculates the sum of elements T(n) + T(n+1) + ... + T(2n-1) in a complete binary tree.
- It utilises a parallel approach, with each iteration of the outer loop executed in parallel by multiple processors.
- The algorithm requires θ(logn) time complexity for n/2 processors.
- The total work done is O(nlogn/2), and the speedup is θ(n/logn).
- However, the algorithm is not work-optimal.

### Prefix Computation:

- Prefix computation involves performing a specific operation (e.g., addition) on a list of numbers, generating a sequence of cumulative results.
- The algorithm divides the input list among processors and recursively computes prefix sums in parallel.
- The time complexity is O(logn) for n processors, and the total work done is O(nlogn).
- The speedup is O(n/logn), and the efficiency is O(1/logn).
- The algorithm is not work-optimal.

### Work Optimal Prefix Computation:

- To achieve work optimality, the algorithm uses n/logn processors.
- Each processor computes prefix sums on a subset of numbers in parallel.
- The locally computed results are then updated using the prefix sum algorithm.
- The algorithm has a time complexity of O(logn) for n/logn processors and achieves work optimality.
- The speedup is O(n/logn), and the efficiency is O(1).

### Parallel Evaluation of an Expression Tree:

- The algorithm aims to evaluate an expression tree in parallel, utilising multiple processors.
- Each internal node of the tree represents an operator, and the values of the children nodes are used to compute the value of the internal node.
- The algorithm repeats the evaluation process until only one node is left, which represents the final result of the expression.
- The time complexity for 'n' processors is θ(logn), and the total work done is θ(nlogn).
- The speedup is θ(n/logn), indicating the potential improvement in execution time with increasing processor count.
- However, the algorithm is not work-optimal.

### Work Optimal Parallel Evaluation of an Expression Tree:

- To design a work-optimal algorithm, we can use n/logn processors.
- The algorithm distributes the evaluation of internal nodes among the processors in a way that minimises the work performed by each processor.
- By carefully assigning the evaluation tasks, the algorithm achieves work optimality while maintaining a time complexity of θ(logn) for n/logn processors.
- The speedup remains θ(n/logn), but the efficiency improves to O(1/logn).

## Dining Philosophers Problem (DPP)

[B1_22010878_Prathamesh Araikar_Assignment6.pdf](DAA%2060123486700c43d5b131c652d5370df3/B1_22010878_Prathamesh_Araikar_Assignment6.pdf)

## Matrix Multiplication using Multi-Threading

[B1_22010878_Prathamesh Araikar_Assignment7.pdf](DAA%2060123486700c43d5b131c652d5370df3/B1_22010878_Prathamesh_Araikar_Assignment7.pdf)