TOPIC : [[STACKS]]
`2023-07-13

## TOPIC INFO 
Given an array of integers `heights` representing the histogram's bar height where the width of each bar is `1`, return _the area of the largest rectangle in the histogram_.

![[Pasted image 20230713161223.png]]



```python
class Solution:

def largestRectangleArea(self, heights: List[int]) -> int:

endr=1

endl=1

count=1

ans=0

for i , n in enumerate(heights):

# print("enter ")

  

# print(heights[i])

  

while (not (i+endr)>(len(heights)-1)) and heights[i+endr]>=n :

endr=1+endr

count=1+count

# print(endr)

# print("ex")

while (not (i-endl)<0) and heights[i-endl]>=n :

# print(endl)

endl=1+endl

count=1+count

# print("ex1")

area=count*n

if area > ans:

ans =area

area = 0

count =1

endr =1

endl =1

return ans
```

ok so first i honestly could not think of anything so i tried to brute force it by just checking neighbours till i find a smaller one but that obviously not the answer sooo the answer is to use a stack that holds index and height if we have an element which is smaller than the top of stack we pop the top and check what the max area we could have gotten is we check that by checking the index of the element we are popping and substracting it from the current index and multiplying it with the height of the pop now we add the element if we poped an elemetn before it we shift the index of the current back by one as the last one would have been larger 
by the end if there are elements left in the stack that just means that they reached the end of the graph uninterupted there for we just take their position and substract the length by that much and multiply the height till the stack is empty.
```python
class Solution:
    def largestRectangleArea(self, heights: List[int]) -> int:
        maxArea = 0
        stack = []  # pair: (index, height)

        for i, h in enumerate(heights):
            start = i
            while stack and stack[-1][1] > h:
                index, height = stack.pop()
                maxArea = max(maxArea, height * (i - index))
                start = index
            stack.append((start, h))

        for i, h in stack:
            maxArea = max(maxArea, h * (len(heights) - i))
        return maxArea

```



### BRIEF



### CONCLUSION