# IT5005-Assignment1
For a class project.

Assignment 1 Q1:

Breadth First Search (BFS) and Depth First Search (DFS) algorithms for solving a simple maze puzzle.

BFS and DFS algorithms can be extended to solve other problems with known discrete states and transition between states incurs a fixed cost. Such problems can be easily modelled with a graph, and then we can apply BFS/DFS algorithms.

Assignment 1 Q2:

Simulated Annealing Algorithm for solving Travelling Salesperson Problem.

Problem:

Given multiple (600) reads (small snippets) of a virus' RNA, piece them together to obtain the full RNA.

Solution:

1. Let each RNA read be the node of a graph. Model the graph with an adjacency matrix.

2. The weight of each edge is the length of the suffix/prefix overlap of each pair of snippets. Write a string suffix-prefix comparison function for this (typical leetcode style problem).

3. Define the NEGATIVE of the overlap length to be the weight of each edge on the graph.

4. The problem is now a Travelling Salesperson Problem. We want to visit all the nodes (snippets) while minimizing costs (so we want highest total overlap length).

5. Apply Simulated Annealing Algorithm to this problem. Simulated Annealing works as follows:
 
  5.1: Start with a random permutation of vertices to be visited in order.
  
  5.2: Define the 'Transport' and 'Reverse' operations on the vertices. 
  
    5.2.1: 'Transport' works by 'leaving out a set of nodes and save them for later in the trip'.
    
    5.2.2: 'Reverse' works by 'reversing the order a set of nodes is visited'.
    
  5.3: Calculate the total cost of travel of the new permutation after each operation is applied.
  
    5.3.1: If the new cost is lower, accept the move ('Transport' or 'Reverse')
    
    5.3.2: If the new cost is higher, accept the move with probability p, where p decays exponentially as total number of moves made increases.
    
  5.4: After some number of move attempts (100000 in the code for the problem instance), return the final permutation of vertices to be visited in order.
  
  
