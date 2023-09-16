TOPIC : [[ARRAYS AND HASHING]]
`2023-07-09

## TOPIC INFO 
Given an integer array `nums`, return _an array_ `answer` _such that_ `answer[i]` _is equal to the product of all the elements of_ `nums` _except_ `nums[i]`.

The product of any prefix or suffix of `nums` is **guaranteed** to fit in a **32-bit** integer.

You must write an algorithm that runs in `O(n)` time and without using the division operation.

the problem is that the have told not to use division operator sooo thoda f hogaya now i was thinking a yes or no tree but that also wont be linear time so what to dooooo.... 

actually its pretty simple u just calculate the prefix and post fix multiplications of the array therefore 

![[Pasted image 20230709173642.png]]


this requires two runs through the array soo 2n complexity ie n only sooo very simple question par nahi hua fffff


```python
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        res = [1] * (len(nums))

        prefix = 1
        for i in range(len(nums)):
            res[i] = prefix
            prefix *= nums[i]
        postfix = 1
        for i in range(len(nums) - 1, -1, -1):
            res[i] *= postfix
            postfix *= nums[i]
        return res
```
