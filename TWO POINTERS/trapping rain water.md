TOPIC : [[TWO POINTERS]]
`2023-07-15

## TOPIC INFO 

![[Pasted image 20230715165943.png]]

ok so one way is simulating it dropping water at every location till height somewhere dosent change but very complex

so a very easy way to do is just to keep trackk of the max on the left and the right for each unit and then to check the number of water blocks at the specific unit by doing min(lmax,rmax)-height[i]

we do this for each unit ie go through the array twice and do a cumulative max check once from left side and one from right side

like this 
![[Pasted image 20230715181419.png]]


there is a way to do this in a constant time but i am too lazy to figure that rn so here the code

```python
class Solution:
    def trap(self, height: List[int]) -> int:
        if not height:
            return 0

        l, r = 0, len(height) - 1
        leftMax, rightMax = height[l], height[r]
        res = 0
        while l < r:
            if leftMax < rightMax:
                l += 1
                leftMax = max(leftMax, height[l])
                res += leftMax - height[l]
            else:
                r -= 1
                rightMax = max(rightMax, height[r])
                res += rightMax - height[r]
        return res

```

### BRIEF



### CONCLUSION