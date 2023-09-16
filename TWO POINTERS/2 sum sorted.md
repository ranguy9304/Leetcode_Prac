TOPIC : [[TWO POINTERS]]
`2023-07-14

## TOPIC INFO 

Given a **1-indexed** array of integers `numbers` that is already **_sorted in non-decreasing order_**, find two numbers such that they add up to a specific `target` number. Let these two numbers be `numbers[index1]` and `numbers[index2]` where `1 <= index1 < index2 < numbers.length`.

Return _the indices of the two numbers,_ `index1` _and_ `index2`_, **added by one** as an integer array_ `[index1, index2]` _of length 2._

The tests are generated such that there is **exactly one solution**. You **may not** use the same element twice.

Your solution must use only constant extra space.
**Input:** numbers = [2,7,11,15], target = 9
**Output:** [1,2]
**Explanation:** The sum of 2 and 7 is 9. Therefore, index1 = 1, index2 = 2. We return [1, 2].

ok so first i thought thoda but i forgot everything that has been taught in the daa class because its taught so badly sooo basically what i did first is that i was going through each element and using binary search tried to find the oppostie element very innefficient only beats 3 percent of perople very ass code but apparently the best solution is to use the two pointer thing i should have knownnnsdfksdkfnsdfjasdfngi

MY CODE
```python
class Solution:

def twoSum(self, numbers: List[int], target: int) -> List[int]:

def find(start,end,res):

loco=floor((start+end)/2)

# print(loco ,numbers[loco])

# print(start,end)

  

if numbers[loco] == res:

return loco

elif start == end:

return -1

elif numbers[loco] > res:

return find(start,loco,res)

elif numbers[loco] < res:

return find(loco+1,end,res)

for i, n in enumerate(numbers):

f = target - n

raul=find(i+1,len(numbers)-1,f)

if raul != -1:

return [i+1,raul+1]
```
the two pointer trick

```python
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        l, r = 0, len(numbers) - 1

        while l < r:
            curSum = numbers[l] + numbers[r]

            if curSum > target:
                r -= 1
            elif curSum < target:
                l += 1
            else:
                return [l + 1, r + 1]

```



### BRIEF



### CONCLUSION