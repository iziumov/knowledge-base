##Stack
LIFO -> Last in First out

##Queue
FIFO -> First in First Out

```
def removeDuplicates(s):
    stack = []
    for c in s:
        if c == stack[-1]:
            stack.pop()
        else:
            stack.append(c)
    return "".join(stack)

def isValid(s):
    pair = {
        "(": ")",
        "[": "]",
        "{": "}",
    }

    stack = []

    for c in s:
        if c in pair:
            stack.append(c)
        else:
            if not stack:
                return False
            prev = stack.pop()
            if c != pair[prev]:
                return False

    return len(stack) == 0
```
