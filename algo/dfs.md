## DFS

Depth First Search

```

type Node struct {
    Value int
    Left *Node
    Right *Node
}

def dfs(node):
    if not node:
        return
    print(node) # pre order
    dfs(node.left)
    print(node) # in order
    dfs(node.right)
    print(node) # post order
    return


recursion variant
def maxDepth(node):
    if not node:
        return 0
    l = maxDepth(node.left)
    r = maxDepth(node.right)
    return max(l, r) + 1


iteration variant
def maxDepth(node):
    stack = [(node, 1)]
    result = 0
    while stack:
        node, depth = stack.pop()
        if not node:
            continue
        result = max(result, depth)
        stack.append((node.left, depth + 1))
        stack.append((node.right, depth + 1))
    return result

def reverseTree(node):
    if not node:
        return
    node.left, node.right = node.right, node.left
    reverseTree(node.left)
    reverseTree(node.right)

    return node

def isSameTree(node):
    if not node:
        return
    stack = [node.left, node.right]
    while stack:
        right = stack.pop()
        left = stack.pop()

        if not left and not right:
            continue
        if not left or not right:
            return False
        if left.val != right.val:
            return False
        stack.append(left.left)
        stack.append(right.right)
        stack.append(left.right)
        stack.append(right.left)

    return True


def hashPathSum(node, target):
    stack = [(node, 0)]
    while stack:
        node, current_sum = stack.pop()
        if not node:
            continue

        if not node.left and node.right and current_sum == targetSum:
            return True

        stack.append((node.left, current_sum + node.val))
        stack.append((node.right, current_sum + node.val))

    return False
```

45:00

## Recursion

```
def f(n):
    if n == 0
        return
    f(n-1)
    print(n)

f(5) // 1 2 3 4 5
и

def f(n):
    if n == 0
        return
    print(n)
    f(n-1)

f(5) // 5 4 3 2 1 <- так как до того как войдем в рекурсивный вызов
```
