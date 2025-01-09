# Connected Components for Un-directed Graph using BFS

Finding connected components for an un-directed graph is an easier task. The following steps outline the approach to implement the idea using BFS (Breadth-First Search):

## Steps to Implement BFS for Connected Components:

1. **Initialize all vertices as not visited.**
2. **For every vertex `v`:**
   - If `v` has not been visited before, perform the BFS and print a newline character to separate each component on a new line.
   - Mark `v` as visited and print `v`.
   - For every adjacent vertex `u` of `v`, if `u` has not been visited, recursively call the BFS procedure for `u`.
