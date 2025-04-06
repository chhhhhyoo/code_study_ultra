## 개념 문제

1. **DFS를 구현하는 대표적인 두 가지 방법은 재귀 호출을 이용하는 것과 명시적인 스택(Stack) 자료구조를 사용하는 것입니다.**  
   각 구현 방식의 장단점을 비교 설명해주세요.

DFS is a graph traversal algorithm. So from the source node, it will explore as deep as possible before backtracking.
Because of this, it needs to remember where it has been, and track where to go next.

With this as the fundamental, let's dive deeper into two approaches : 1. Recursion 2. Stack.

**Recursive DFS**

With Recursive DFS, when you explore a neighbor(recursive call), the current state is preserved on the call stack.
This will include
- The node you are on
- local variables
- The sequence of neighbors yet to be visited
When a recursive call is finished, it returns to the previous call, which effectively "backtracks" to the prior node. Thus it backtracks automatically, remembering everything for you.

**limitations**
1) If the graph is very deep, because of the call stack has limited size, it will cause a RecursionError. [Not safe for graphs with high depth - long chain, skewed trees]

2) It can be hard to track what is going on.

**Stack**
With explicit stack, you will be managing the traverse manually. This provides full control and visibility.

This will benefit in several ways :
1) There will be no stack overflow(Recursion limit x) : We are no longer using call stack, be managing our own stack.

2) More Transparent & Control : We can see and interact during the flow of traversal logic.

**Limitations**
1) More control, meaning you have to manually manage the flow.

2) Code can be lengthy with low readability.


2. **방향 그래프(Directed Graph)에서 사이클(Cycle) 존재 여부를 판별하기 위해 DFS를 어떻게 활용할 수 있는지**  
   구체적인 알고리즘을 설명해주세요.

**Background - Question**
Starting with understanding the problem.
We are dealing with Directed Graph here, and in directed graph, we have to consider
directional flow and path dependency.
Thus, the node has to be revisited within the same DFS path in order to be in a cycle.

**Background - DFS tracking**
To detect cycles in a directed graph, we need to track
1) visited : nodes we have fully explored(= all descendant processed)
2) on_path : nodes currently on the recursion stack(= part of the current path)

Here, the **on_path** is crucial!!!

Going through the traverse, if you encounter a neighbor that is already in on_path(current path), then you found a cycle.


3. **재귀를 활용한 DFS에서 가장 최근의 노드로 돌아가는 백트래킹 동작이 어떤 방식으로 동작하는지**  
   하나의 예를 들어 설명해주세요.


