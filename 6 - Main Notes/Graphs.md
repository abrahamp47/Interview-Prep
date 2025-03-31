2025-03-25 22:02

Status: 

Tags:

# Graphs

Graphs mainly consists of two components - vertice and edge. Where E < V^2
Where it can be mainly represented in three formats
1.Matrix
2.Adjacency Matrix
3.Adjacency List

## Matrix

Matrix method is where the matrix is shown as grid with 0s to represent free space and 1s to represent blocked space. We can traverse throughs 0s.

![[Screenshot 2025-03-25 at 10.09.53 PM.png]]

## Adjacency Matrix

Adjacency Matrix is another way to represent a graph, It is a square matrix of N x N size where N is the number of nodes in the graph and it is used to represent the connections between the vertices of a graph.

![[Screenshot 2025-03-25 at 10.11.58 PM.png]]

It is very space heavy so the use of a Adjacency matrix is discouraged.

### Adjacency Matrix DFS

```python
# Matrix (2D Grid)
grid = [[0, 0, 0, 0],
        [1, 1, 0, 0],
        [0, 0, 0, 1],
        [0, 1, 0, 0]]

# Count paths (backtracking)
def dfs(grid, r, c, visit):
    ROWS, COLS = len(grid), len(grid[0])
    if (min(r, c) < 0 or
        r == ROWS or c == COLS or
        (r, c) in visit or grid[r][c] == 1):
        return 0
    if r == ROWS - 1 and c == COLS - 1:
        return 1

    visit.add((r, c))

    count = 0
    count += dfs(grid, r + 1, c, visit)
    count += dfs(grid, r - 1, c, visit)
    count += dfs(grid, r, c + 1, visit)
    count += dfs(grid, r, c - 1, visit)

    visit.remove((r, c))
    return count

```

### Adjacency Matrix BFS
```python
from collections import deque

# Matrix (2D Grid)
grid = [[0, 0, 0, 0],
        [1, 1, 0, 0],
        [0, 0, 0, 1],
        [0, 1, 0, 0]]

# Shortest path from top left to bottom right
def bfs(grid):
    ROWS, COLS = len(grid), len(grid[0])
    visit = set()
    queue = deque()
    queue.append((0, 0))
    visit.add((0, 0))

    length = 0
    while queue:
        for i in range(len(queue)):
            r, c = queue.popleft()
            if r == ROWS - 1 and c == COLS - 1:
                return length

            neighbors = [[0, 1], [0, -1], [1, 0], [-1, 0]]
            for dr, dc in neighbors:
                if (min(r + dr, c + dc) < 0 or
                    r + dr == ROWS or c + dc == COLS or
                    (r + dr, c + dc) in visit or grid[r + dr][c + dc] == 1):
                    continue
                queue.append((r + dr, c + dc))
                visit.add((r + dr, c + dc))
        length += 1
```


## Adjacency List

![[Pasted image 20250331130501.png]]



# References


