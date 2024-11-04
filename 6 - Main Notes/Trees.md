2024-10-24 11:47

Status:

Tags:

# Trees

DFS Traversal

Iterative Solution

Use Stack data structure

push each node to stack,
 check if stack is empty, if not pop top print it and then push it children in right left order to stack
 repeat till stack is empty
 
 Recursive Solution
    if root:
        # First print the data of node
        print(root.val),
 
        # Then recur on left child
       dfs(root.left)
 
        # Finally recur on right child
        dfs(root.right)

BFS Traversal

we use a queue, we add tree nodes in the rear and pop from the front.

  

def bfs_recursive(queue):

    if not queue:

        return

    # Process the current level nodes

    current_level = []

    for _ in range(len(queue)):

        node = queue.popleft()

        current_level.append(node.value)

        # Enqueue the child nodes

        if node.left:

            queue.append(node.left)

        if node.right:

            queue.append(node.right)

    # Print the current level or store it for further use

    print(current_level)

    # Recursive call for the next level

    bfs_recursive(queue)




# References


