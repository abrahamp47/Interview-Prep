2024-11-09 15:21

Status:

Tags:

# Djikstra's Algorithm

It is the algorithm to find the shortest path in a weight graph

![[Screenshot 2024-11-09 at 3.30.33 PM.png]]

```python
import heapq

def dijkstra(matrix):
    rows, cols = len(matrix), len(matrix[0])
    directions = [(0, 1), (1, 0), (0, -1), (-1, 0)]  # Right, Down, Left, Up
    
    # Cost matrix to store minimum cost for each cell, initialized with infinity
    cost = [[float('inf')] * cols for _ in range(rows)]
    cost[0][0] = matrix[0][0]
    
    # Priority queue and visited set
    min_heap = [(matrix[0][0], 0, 0)]
    visited = set()
    
    while min_heap:
        current_cost, row, col = heapq.heappop(min_heap)
        
        # Skip if already visited
        if (row, col) in visited:
            continue
        visited.add((row, col))
        
        # Explore all four directions
        for dr, dc in directions:
            new_row, new_col = row + dr, col + dc
            if 0 <= new_row < rows and 0 <= new_col < cols:  # Within bounds
                new_cost = current_cost + matrix[new_row][new_col]
                
                # Only consider if not visited and new cost is lower
                if (new_row, new_col) not in visited and new_cost < cost[new_row][new_col]:
                    cost[new_row][new_col] = new_cost
                    heapq.heappush(min_heap, (new_cost, new_row, new_col))
    
    # Minimum cost to reach the bottom-right cell
    return cost[rows - 1][cols - 1]
```

# References


