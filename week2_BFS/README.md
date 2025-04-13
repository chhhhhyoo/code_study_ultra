### 개념 문제

1. **BFS(너비 우선 탐색)** 알고리즘의 작동 원리를 설명하고, 어떤 자료구조를 사용하는지, 그리고 그 이유는 무엇인지 설명해주세요.

**Breadth-First Search(BFS)** is a fundamental graph traversal algorithm that explores all nodes at the current depth level before moving on to nodes in the next depth level.

The BFS algorithm proceeds as follows :
    1) Initialize a queue and insert the starting node.
    2) Mark the starting node as visited to avoid revisiting.
    3) While the queue is not empty:
        a) Dequeue a node N from the front of the queue.
        b) If N is the target, the search terminates.
        c) Else, enqueue all unvisited neighbors of N and mark them as visited.
    4) Repeat until queue is empty or the target is found.

BFS uses a queue(First-In-First-Out). This ensures that nodes are explored in the exact order they are discovered.
Because of the queue's FIFO nature, BFS will guarantee that all nodes at a particular depth are visited before any nodes at the next depth level are visited.

2. **BFS와 DFS(깊이 우선 탐색)**의 차이점은 무엇이며, 각각 어떤 종류의 문제에 더 적합한지 예시를 들어 설명해주세요.

| Feature             | **BFS**                                  | **DFS**                                    |
|---------------------|-------------------------------------------|-------------------------------------------|
| Traversal Strategy  | Level-order traversal                     | Depth-wise traversal                      |
| Data Structure      | Queue (FIFO)                              | Stack (LIFO) or recursive call stack      |
| Discovery Order     | Closest neighbors first                   | Deepest branch first                      |
| Shortest Path?      | Yes (in unweighted graphs)                | Not guaranteed                            |
| Space Complexity    | High (stores many nodes at a time)        | Lower (depends on path depth)             |
| Common Applications | Shortest path, level-order traversal      | Topological sort, cycle detection, backtracking |


```
    A
   / \
  B   C
 /     \
D       E
```
BFS Traversal : A -> B -> C -> D -> E

DFS Traversal : A -> B -> D -> C -> E

**Use Case Comparison**

[BFS]

When to use?
- shortest path(minimum number of edges) in unweighted graph
- level-order relationships
- early discovery(solution is closer to the root)

Sample use case
- Shortest path in a maze
- Minimum number of moves
- Finding connected components(Socaial Networking graphs)

[DFS]

When to use?
- graph/tree is deep
- require backtracking & exhaustive search  
- need to explore all possible path/combinations

Sample use case
- Topological sorting
- Cycle detection
- Sudoku/subset/permutation




3. **BFS 알고리즘의 시간 복잡도는 O(V+E)**인데, 그래프의 형태(예: 밀집 그래프 vs 희소 그래프)가 실제 수행 시간에 어떤 영향을 미칠 수 있을지 설명해주세요.

Before going on to answering the question, I would like to touch on the background of the concept.

[**BFS 알고리즘의 시간 복잡도는 O(V+E)**]

V : number of vertices(nodes)

E : number of edges (connections between nodes)

In BFS,
 - Each vertex is visited once
 - Each edge is checked once

Thus we get,
- Touching all the nodes, O(V)
- Scanning all connections, O(E)

which sums up to : O(V+E)

[Dense graph / Sparse graph]

Dense graph : Nearly fully connected `(E ≈ V²)`
 
Sparse graph : Few connections `(E ≪ V²)`

- In a **sparse graph**, nodes have only a few edges:
  - `E ≈ V`, so `O(V + E)` behaves more like `O(V)`
  - BFS runs efficiently due to fewer neighbor checks

- In a **dense graph**, each node connects to many others:
  - `E` can approach `V²`, especially in directed graphs
  - BFS takes longer due to processing many more edges

Example :  you have a graph with `V = 1,000` nodes:

- In a **sparse graph**, maybe `E ≈ 2,000` → `O(1,000 + 2,000)` = `O(3,000)`
- In a **dense graph**, `E ≈ 1,000,000` → `O(1,000 + 1,000,000)` = `O(1,001,000)`

=> Even though both graphs have the same number of vertices, **BFS on the dense graph performs significantly more work**.