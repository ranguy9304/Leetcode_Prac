TOPIC : [[STACKS]]
`2023-07-12

## TOPIC INFO 
Given an array of integers `temperatures` represents the daily temperatures, return _an array_ `answer` _such that_ `answer[i]` _is the number of days you have to wait after the_ `ith` _day to get a warmer temperature_. If there is no future day for which this is possible, keep `answer[i] == 0` instead.
**Input:** temperatures = [73,74,75,71,69,72,76,73]
**Output:** [1,1,4,2,1,1,0,0]



here i dont remember what i was thinking but i was indeed going in the direction of using two stacks but apparently it was simpler than that as we just had to use one stack where where we push elements and check if the top of the stack is less than the current in question if it is less than it then we pop or something
```python

class Solution:
    def dailyTemperatures(self, temperatures: List[int]) -> List[int]:
        res = [0] * len(temperatures)
        stack = []  # pair: [temp, index]

        for i, t in enumerate(temperatures):
            while stack and t > stack[-1][0]:
                stackT, stackInd = stack.pop()
                res[stackInd] = i - stackInd
            stack.append((t, i))
        return res

```

### BRIEF



### CONCLUSION