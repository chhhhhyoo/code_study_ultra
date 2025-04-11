### 개념 문제

1. **BFS(너비 우선 탐색)** 알고리즘의 작동 원리를 설명하고, 어떤 자료구조를 사용하는지, 그리고 그 이유는 무엇인지 설명해주세요.

BFS stands for Breadth First Search where the search will explore all neighbors in the same level before going on to the nodes in the next depth level.

BFS mechanism can be explained with the following steps :
    1) Start with the root node, insert root node to the queue. 
    2) Pop a node from the queue, if the node is the target, search is completed.
    3) Else, insert child nodes of the node to the queue.
    4) Until you find the target or the queue is empty, repeat 2 & 3.

Queue is used in BFS. This is mainly because of the FIFO characteristic of the queue.
FIFO characteristic makes sure that we visit all the neighboring nodes in the same level before going on to the next depth level. 


2. **BFS와 DFS(깊이 우선 탐색)**의 차이점은 무엇이며, 각각 어떤 종류의 문제에 더 적합한지 예시를 들어 설명해주세요.




3. **BFS 알고리즘의 시간 복잡도는 O(V+E)**인데, 그래프의 형태(예: 밀집 그래프 vs 희소 그래프)가 실제 수행 시간에 어떤 영향을 미칠 수 있을지 설명해주세요.
