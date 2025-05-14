## BFS

Breadth First Search O(log n)

```
   1
  /\
  2 3
 /| |\
4 5 6 7

[1] -> [3, 2] -> [7,6,5,4]
```

```
def bfs(root):
    q = [root]
    while q:
        level_size = len(q)
        for _ in range(level_size):
            node = q.pop()
            q.append(node_left)
            q.append(node_right)
    return

def levelOrder(root):
    if not root:
        return []

    result = []
    q = deque([root])
    while q:
        level_size = len(q)
        current_level = []

        for _ in range(level_size):
            node = q.popleft()
            current_level.append(node.val)

            if node.left:
                q.append(node.left)
            if node.right:
                q.append(node.right)

            result.append(current_level)

    return result

def largestValues(root):
    if not root:
        return []

    result = []
    q = deque([root])
    while q:
        level_size = len(q)
        level_max = float('-inf')

        for _ in range(level_size):
            node = q.popleft()
            level_max = max(level_max, node.val)

            if node.left:
                q.append(node.left)
            else:
                q.append(node.right)

            result.append(level_max)

    return result


def levelOrder(root):
    if not root:
        return []

    result = []
    q = deque([root])
    while q:
        level_size = len(q)
        current_level = []

        for _ in range(level_size):
            node = q.popleft()
            current_level.append(node.val)

            if node.left:
                q.append(node.left)
            if node.right:
                q.append(node.right)

            result.append(current_level[-1])

    return result


def removeLeafNodes(root, target):
    if not root:
        return None

    root.left = removeLeafNodes(root.left, target)
    root.right = removeLeafNodes(root.right, target)

    if not root.left and not root.right and root.val == target:
        return None

    return root

def diameterOfBinaryTree(root):
    d = 0

    def dfs(node):
        if not node:
            return 0
        l = dfs(node.left)
        r = dfs(node.right)
        self.d = max(self.d, l + r)
        return max(l,r) + 1

    dfs(root)
    return self.d
```
