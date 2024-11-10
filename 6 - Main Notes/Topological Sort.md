2024-11-10 12:50

Status:

Tags:

# Topological Sort

Only works on DAGs

DFS

```python
# Given a directed acyclical graph, return a valid
# topological ordering of the graph. 
def topologicalSort(edges, n):
    adj = {}
    for i in range(1, n + 1):
        adj[i] = []
    for src, dst in edges:
        adj[src].append(dst)

    topSort = []
    visit = set()
    for i in range(1, n + 1):
        dfs(i, adj, visit, topSort)
    topSort.reverse()
    return topSort

def dfs(src, adj, visit, topSort):
    if src in visit:
        return
    visit.add(src)
    
    for neighbor in adj[src]:
        dfs(neighbor, adj, visit, topSort)
    topSort.append(src)
```

BFS

```python
from collections import deque, defaultdict

def topological_sort_bfs(vertices, edges):
    # Step 1: Create an adjacency list and initialize in-degree of each node
    adj_list = defaultdict(list)
    in_degree = {i: 0 for i in range(vertices)}
    
    # Build the graph and compute in-degrees
    for u, v in edges:
        adj_list[u].append(v)
        in_degree[v] += 1

    # Step 2: Find all vertices with in-degree of 0 and add them to the queue
    queue = deque([node for node in in_degree if in_degree[node] == 0])
    topo_order = []

    # Step 3: Process nodes with BFS
    while queue:
        node = queue.popleft()
        topo_order.append(node)

        # Decrease in-degree for neighbors
        for neighbor in adj_list[node]:
            in_degree[neighbor] -= 1

            # If in-degree becomes 0, add neighbor to queue
            if in_degree[neighbor] == 0:
                queue.append(neighbor)

    # If topological order contains all nodes, return it
    if len(topo_order) == vertices:
        return topo_order
    else:
        return "Graph has a cycle, topological sort not possible."

# Example usage:
vertices = 6
edges = [(5, 2), (5, 0), (4, 0), (4, 1), (2, 3), (3, 1)]
print(topological_sort_bfs(vertices, edges))

```
# References


