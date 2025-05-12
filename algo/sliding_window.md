##Sliding Window

```
alg pattern
def name():
    begin = 0
    window_state

    for end in range(len(nums)):
        end - begin + 1 #window size
        if #window_condition
            begin += 1 #shrink window
```

```
def maxAverageSumArray(nums, k):
    begin = 0
    window_state = 0
    result = float('-inf')

    for end in range(len(nums)):
        window_state += nums[end]
        if end - begin + 1 == k:
            result = max(result, window_state)
            begin += 1

    return result / k
```

```
    def minSubArray(target, nums):
        begin = 0
        window_state = 0
        result = float('-inf')

        for end in range(len(nums)):
            window_state += nums[end]

            if window_state >= target:
                window_size = end - begin + 1
                result = min(result, window_size)
                window_state -= nums[begin]
                begin += 1

        return result
```
