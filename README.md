# Connected Components for Un-directed Graph using BFS

Finding connected components for an un-directed graph is an easier task. The following steps outline the approach to implement the idea using BFS (Breadth-First Search):

## Steps to Implement BFS for Connected Components:

1. **Initialize all vertices as not visited.**
2. **For every vertex `v`:**
   - If `v` has not been visited before, perform the BFS and print a newline character to separate each component on a new line.
   - Mark `v` as visited and print `v`.
   - For every adjacent vertex `u` of `v`, if `u` has not been visited, recursively call the BFS procedure for `u`.

## Example

### Code:

```python
from collections import deque

def bfs(graph, start, visited):
    queue = deque([start])
    visited[start] = True
    print(start, end=" ")

    while queue:
        vertex = queue.popleft()
        for neighbor in graph[vertex]:
            if not visited[neighbor]:
                queue.append(neighbor)
                visited[neighbor] = True
                print(neighbor, end=" ")

def connected_components(graph):
    visited = {v: False for v in graph}
    for vertex in graph:
        if not visited[vertex]:
            bfs(graph, vertex, visited)
            print()  # Print newline after each component

# Example graph as an adjacency list
graph = {
    0: [1, 2],
    1: [0, 2],
    2: [0, 1],
    3: [4],
    4: [3],
    5: []
}

# Finding connected components
connected_components(graph)
