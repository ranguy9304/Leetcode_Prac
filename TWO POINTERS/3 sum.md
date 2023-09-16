TOPIC : [[TWO POINTERS]]
`2023-07-14

## TOPIC INFO 
Given an integer array nums, return all the triplets `[nums[i], nums[j], nums[k]]` such that `i != j`, `i != k`, and `j != k`, and `nums[i] + nums[j] + nums[k] == 0`.

Notice that the solution set must not contain duplicate triplets.

**Example 1:**

**Input:** nums = [-1,0,1,2,-1,-4]
**Output:** ([-1,-1,2],[-1,0,1] )
ok so the first obvious way is to do brute force which will be n^3 so we first sort the array and loop through one by one now to avoid duplicates we just check if the current first element of the was there before if yes then we continue done.

bbbbbut luckly i figured out this one correctly as we can solve this using 2 sum question for sorted [[2 sum sorted]] here we just itirate through first element and find the 2 sum for the target as negative of the current element and for duplicate we do the same thing as the above brute force method basically check if the current first element has appeared before if yes then skip


MY CODE ABSOLUTE ASS 30 percent beats
```python
class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        def twoSum(numbers, target) :
            l, r = 0, len(numbers) - 1
            resarr=[]
            rprev=None
            lprev=None

            while l < r:

                curSum = numbers[l] + numbers[r]
                # print(curSum)
                if l==r:
                    # print(l)
                    return []
                if curSum > target or numbers[r]==rprev:
                    rprev=numbers[r]
                    r -= 1

                elif curSum < target or numbers[l]==lprev:
                    lprev=numbers[l]
                    l += 1
                else:
                    print("rnd")
                    resarr.append( [numbers[l ], numbers[r ]])
                    rprev=numbers[r]
                    lprev=numbers[l]
                    l += 1
                    r -= 1
            # print("end")
            return resarr
        go=sorted(nums)
        # print(go)
        re=[]
        prev =None
        for i,n in enumerate(go):
            
            # print('-----')
            # print(-n)
            # print('------')
            arr =twoSum(go[i+1:],-n)
            # print(arr)
            
            if n==prev or arr is None or arr == []:

                continue
            else:
                prev=n
                for i in arr:
                    i.append(n)
                re+=arr
        return re


```
EXACTLY SAME SHIT BUT BETTER 93 % beats
```python
class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        res = []
        nums.sort()

        for i, a in enumerate(nums):
            # Skip positive integers
            if a > 0:
                break

            if i > 0 and a == nums[i - 1]:
                continue

            l, r = i + 1, len(nums) - 1
            while l < r:
                threeSum = a + nums[l] + nums[r]
                if threeSum > 0:
                    r -= 1
                elif threeSum < 0:
                    l += 1
                else:
                    res.append([a, nums[l], nums[r]])
                    l += 1
                    r -= 1
                    while nums[l] == nums[l - 1] and l < r:
                        l += 1
                        
        return res

```



### BRIEF



### CONCLUSION