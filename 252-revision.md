# COMP 252 - Final study 

## Important algorithms and their time complexities
- **Karatsuba** Multiplication (algorithm for multiplying two n-bit numbers): $O(n^{\log_2(3)})$
- chip testing DAC: $O(n)$
- Fast matrix exponentiation (bit model): $O(n^2)$
- **Binary search** (find a number in a sorted list) : $O(\log n)$
- Naive matrix multiplication : $O(n^3)$ 
- **Strassen's** Matrix Multiplication: $O(n^{\log_2(7)}) = O(n^{2.807..})$
- Find the **k^th order statistic** in an unsorted list: naive (sorting the list) is $O(n \log n)$, DAC: $O(n)$
- **Number of Binary trees** on n nodes is the catalan number $1/(n+1)\times ({{2n} \choose n})$. Taking the log gives us that the minimum number of bits to represent a binary tree on n nodes is $2n-o(n)$
- **TSP** (find the tour through all cities with the smallest length), naive is $O((n-1)!)$. DP solution is $O(n^2\times 2^n)$
- **Knapsack** (given n items of sizes x1, x2, ..., xn, and a Knapsack of size K, determine if there exists a subset of the item sizes such that their sum is equal to K): $O(nK)$
- **Assignment problem** DP : $O(n^2\times4^n)$
- Assignment problem **Hungarian** Method : $O(n^3)$
- **LCS** (Longuest common subsequence between 2 strings) DP: $O(nm)$, where n is the length of the first string, and m that of the second.
- **RB trees**. Inserting and deleting are both $O(\log n)$. There are at most $2\log(n+1)$ levels in the tree, so finding the place to insert/delete is $O(\log n)$, then fixing the tree is $O(\log n)$ for case 1, $O(1)$ for cases 2,3.
- Construction of **RB tree** from sorted list is $O(n)$
- **KMP** for pattern matching: building magic table O(m) where m is the size of the pattern we're searching, KMP is $O(n)$, where n is the length of the string in which we're searching the pattern. 
- **Hu-tucker** (Greedy to find Huffman code): $O(n \log n)$

### Graph algorithms:
- **DFS**: $O(|V| + |E|)$
- Find **Euler Tour**: $O(|V| + |E|)$
- **BFS**: $O(|V| + |E|)$
- Successor in **BST**: $O(h)$, where h is the height 
- Browsing in **BST**: $O(h+k)$, where k is the number of steps to browse
- **Dijkstra's** for shortest path: $O(|E| + |V| \log|V|)$
- **Prim-Dijkstra's** for **MST**: $O(|E| + |V| \log|V|)$
- **Kruskal's** for **MST**: $O(|E|\log|E|)$
- **Boruval-Choquet** for **MST**: $O(|E|\log |V|)$ 
- **Floyd-Warshall** DP solution for all pairs shortest distance: $O(|V|^3)$
- **2-Approximation of TSP**: find the MST, then DFS through it and order the nodes in their discovery time. Complexity is $O(|E| + |V|) + O(\text{time to find MST})$ 
- **Find SCCs**: run DFS, save finishing times of each node $O(|V| +|E|)$. Compute $G^T$ by reversing all edges, $O(|V| +|E|)$. Run DFS on $G^T$, in decreasing order of the finishing times found above, save the SCC's $O(|V| +|E|)$ 
- **Ford-Fulkerson** (find max flow): finding an augmenting path is $O(|E|\times val(f))$ if the weights are integers.
- **Edmonds-Karp** (find max flow using BFS to find augmenting paths): O(|E|^2 * |V|)


### Sorting algorithms
- **MergeSort**: $T(n) = (n-1) + 2 T(n/2) ~= n + 2 T(n/2) = O(n \log n)$
- **QuickSort** (equivalent to building a BST): $O(2n\times \ln(n)) \approx O(1.39 n \log n)$
- **HeapSort**: BUILDHEAP is $O(4n)$, DELETEMIN is $O(\log n)$, as it performs at most $2 \log n$ comparisons, so the overall time complexity is $O(n \log n)$, as we must fix the heap n times. The number of comparisons is $4n+ 2n\log n$.
- **Tournament Tree Sort**: BUILDTOURNAMENT takes n-1 comparisons on an array of length n. Accessing smallest element in the tournament tree is O(1), as root has a pointer to it. Then, set smallest element key to infinity and fix the tree, this takes $O(\log n)$. The overall number of comparisons is therefore less than $n + n \log(2n-1)$, as a tournament tree has 2n-1 nodes. This is much better than HeapSort.

### things 
- Kraft's inequality says that in an alphabet of size r, the sum of r raised to the negative power of each code word length is less than 1. If this fact holds with strict inequality, the code is reduntant, if equality it is optimal, if not, then it is not uniquely decodable
- If $E = \sum p_i \log_2 (1/p_i)$ is the entropy, then $E\leq \text{avg length in Huffman code}\leq 1 + E$
- **Fibonacci Heap**: Insert $O(1)$, DeleteMin $O(\log_2 n)$, GetMin $O(1)$, DecreaseKey $O(1)$

## To Do:
- Review KMP algorithm (lecture 18)
- Review Fibonacci heap
- understand this (p.4 lecture 18): 
If we want to make changes to T after constructing a suffix tree, then adding one element to the front at most affects one path, since this element will be added to a leaf. However, adding an element
at the end means it will have to be added to every leaf. The way to build a suffix tree or trie, then, is to insert suffixes from right to left.
- Transitive Closure Problem


