TOPIC : [[ARRAYS AND HASHING]]
`2023-07-08

## TOPIC INFO 
Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`_.

You may assume that each input would have **_exactly_ one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.

i tried brute force almost thought of this solution but then thought fuck it will do brute force 

```python

class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        prevMap = {}  # val -> index

        for i, n in enumerate(nums):
            diff = target - n
            if diff in prevMap:
                return [prevMap[diff], i]
            prevMap[n] = i

```



### BRIEF



### CONCLUSION