#Binary Search Tree
node слева все что меньше node, справа то что больше

```
def searchBST(node, val):
    if not node:
        return None

    if node and node.val == val:
        return node

    if val < node.val:
        return searchBST(node.left, val)
    else:
        return searchBST(node.right, val)


def insertIntoBSF(node, val):
     if not node:
        return TreeNode(val)

    if val < node.val:
        node.left = insertIntoBSF(node.left, val)
    else:
        node.right = insertIntoBSF(node.right, val)

    return node

def isValidBST(root):
    stack = [(root, float('-inf'), float('int'))]
    while stack:
        node, min_range, max_range = stack.pop()
        if not node:
            continue
        if node.val <= min_range or node.val >= max_range:
            return False
        stack.append([node.left, min_range, node.val])
        stack.append([node.range, node.val, max_range])

    return True

def isBalanced(root):
    def height(root):
        if not root:
            return 0
        else:
            return 1 + max(height(root.left), height(root.right))

    if not root:
        return True

    left_h = height(root.left)
    right_h = height(root.right)
    if abs(left_h - right_h) > 1:
        return False

    return isBalanced(root.left) and isBalanced(root.right)
```
