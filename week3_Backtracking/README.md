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

**Brute-force search** tries all possibilities exhaustively without early stopping, while **backtracking** selectively abandons paths that are already known to be invalid.

**Why is backtracking more efficient?**<br>
Brute-force explores all of them, even doomed paths. <br>
In contrast, backtracking reduces the number of explored nodes by detecting failures early and pruning unnecessary branches.

**When is Backtracking especially useful?** <br>
Characteristics of Backtrack *effective* problems are:
- Partial solutions can be validated easily
- Early detection of invalid paths is possible

Some examples are :
- Maze
- Sudoku

### 3. 백트래킹 알고리즘의 시간 복잡도는 일반적으로 어떻게 표현되며, 실제 수행 시간에 가장 큰 영향을 미치는 요소는 무엇인가요? 가지치기(Pruning) 기법이 백트래킹의 효율성을 어떻게 개선하는지 실제 문제 예시를 들어 설명해주세요.

Time Complexity of Backtracking :
<div align="center">
$O(b^d)$
</div>

- b : branching factor(# of choices available)
- d : depth of the search tree

Factors affecting Actual Running Time : <br>
Two main factors :
- Branching factor (b):
- Depth (d)

Reducing either *b* or *d* can improve performance, but **reducing the branching factor** typically has a much larger impact because it shrinks the search space exponentially.

How pruning improves Efficiency :<br>
Pruning improves backtracking by :
- Detecting invalid path early
- Cutting off unnecessary branches
- **Reducing** the effective **branching factor**

Even though the theoretical worst-case remains exponential, effective pruning can significantly reduce the number of nodes actually explored.

Examples of pruning in real problems:

- Maze Solving:
    - Abandon paths that hit a wall or revisit the same cell.

- Sudoku Solving:
    - Stop exploring further when a number placement violates Sudoku rules.












