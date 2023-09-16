TOPIC : [[ARRAYS AND HASHING]]
`2023-07-09

## TOPIC INFO 
Given an unsorted array of integers `nums`, return _the length of the longest consecutive elements sequence._

You must write an algorithm that runs in `O(n)` time.


ok so first i was thinking way too much for this problem should have just vised a bit 

so my first approach was to use to hashsets the first one to store all the nebighouring values also for example if we encounter 5 in a list we add 4,5 and 6 to the set and the second set we only add 5 and everytime we encounter an element we check if it exists in the first list we then check which of its neibhour exists in the second list we add one to the counter for each neibhour present and so on i was thinking in this direction the below is a representation of how i was thinking butttt actually its much more simple 



![[Pasted image 20230709224133.png]]



ok so for the solution what we basically have to do is to find the starting element of each thread for example

![[Pasted image 20230709224948.png]]


in the image the starting of the threads are 1 100 and 200 we find that by checking the presence of the element before current in the hashset if that exisits we move on if it dosent we check the elements +1 and do it till the next element isnt present in the hashset and after completing every thread we update the global counter to find the maximum


code :
```python
class Solution:
    def longestConsecutive(self, nums: List[int]) -> int:
        numSet = set(nums)
        longest = 0

        for n in nums:
            # check if its the start of a sequence
            if (n - 1) not in numSet:
                length = 1
                while (n + length) in numSet:
                    length += 1
                longest = max(length, longest)
        return longest

```

### BRIEF



### CONCLUSION