##TWO POINTERS O(n)

```
[a, b, c, d, e]
 |           |

[e, b, c, d, a]
    |     |

[e, d, c, b, a]
       ||

Example
def reverseString(s):
    left = 0
    right = len(s) - 1
    while left < right:
        s[left], s[right] = s[right], s[left]
        left += 1
        right -= 1
    return

```

Если фраза палиндром

```

def isPalindrome(s):
    left = 0
    right = len(s) - 1
    while left < right:
        if s[left].lower() != s[right].lower()
            return False
        if s[left].isalnum()
            left += 1
        if s[right].isalnum()
            right -= 1

        left += 1
        right -= 1
    return True
```

```
def twoSum(nums, target):
    left = 0
    right = len(nums) - 1
    while left < right:
        current_sum == nums[left] + nums[right]
        if current_sum == target:
            return [left + 1, right + 1]
        if current_sum > target
            right -= 1
        else
            left += 1
    return []
```

```

def threeSum(nums):
    nums = sorted(nums) # O(n * logn)
    result = set()
    n = len(nums)

    for i in range(n):
        target = -nums[i]
        left = i + 1
        right = n - 1
        while left < right:
            current_sum = nums[left] + nums[right]
            if current_sum == target:
                result.add(nums[i], nums[left], nums[right])
            if current_sum > target:
                right -= 1
            else
                left += 1

    return result
```

```

def sortedSquares(nums):
    n = len(nums)
    result = [0] * n
    left = 0
    right = n - 1

    for i in range(n - 1, -1, -1):
        if asb(nums[left]) < asb(nums[right]):
            result[i] = nums[right] * nums[right]
            right -= 1
        else:
            result[i] = nums[left] * nums[left]
            left += 1

    return result
```
