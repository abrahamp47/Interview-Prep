2024-11-01 17:38

Status:

Tags:

# Union-Find

```python
class DSU:

    def __init__(self, n):
        self.par = {}
        self.rank = {}

        for i in range(n):
            self.par[i] = i
            self.rank[i] = 1

   a 
 b. c
d

    def find(self, n):

        if self.par[n] != n:
            par[n] = find(par[n]) //path compression
        return self.par[n]
    
    def union(self, n1, n2):
        p1, p2 = self.find(n1), self.find(n2)
        if p1 == p2:
            return False
        
        if self.rank[p1] > self.rank[p2]:
           self.par[p2] = p1
           self.rank[p1] += self.rank[p2]
        else:
            self.par[p1] = p2
            self.rank[p2] += self.rank[p1]

        return True
```
# References


