### 1. 백트래킹(Backtracking) 알고리즘의 작동 원리를 설명하고, 상태 공간 트리(State Space Tree) 개념과 연관 지어 설명 해주세요. 주로 어떤 방식으로 구현되며(예: 재귀), 그 이유는 무엇인가요?

When we are conducting a search, there are two broad strategies people typically use.

1. Brute-force search : try every single possibility
2. Backtracking : more selective, pruning bad choices

The idea behind **backtracking** is :
 - start by trying possibilities one by one
 - As soon as you notice that <u>*the current partial choice cannot possibly lead to a valid solution*</u>, you **back up(undo)** and try a different path.
- **early rejection** of bad paths

In order to systematically manage and explore these possibilities, we use a structure called a **State Space Tree**.

Now what is **State Space Tree** ?

Every decision point in the problem creates a new "state". <br>
These states, organized in a tree structure, form a **State Space Tree**.


**Components**
- Node : A possible state (partial or complete solution)
- Root : Where search begins
- Edge(branch) : A decision from one state to another
- Leaf : A complete state(full search or dead-end)
- Path : A sequence of decisions (root -> node)

So why is "tree structure" important in backtracking?

A state space tree organizes all possible decision paths systematically.
This makes it easy to **explore**, **backtrack**, and **prune** when necessary.

To explore the state space tree effectively in code, we usually rely on **recursion**, which naturally mirrors the tree's branching and backtracking behavior.

Why does "recursion" fit so well for backtracking?

Recursion gives you a **natural "memory"** of where you came from, and lets you **return back** easily.

### 2. 백트래킹과 완전 탐색(Brute-force search)의 차이점은 무엇이며, 백트래킹이 완전 탐색에 비해 효율적인 이유는 무엇 인가요? 백트래킹이 특히 유용한 문제 유형의 예시를 들어 설명해주세요.









