TOPIC : [[ARRAYS AND HASHING]]
`2023-07-08

## TOPIC INFO 
bruhh ok so the question was to find duplicates in an array and by general approach i brute forced it and forgot about hashing idk why so my solution was 
```python
class Solution:

def containsDuplicate(self, nums: List[int]) -> bool:

	for i in range(0,len(nums)) :
	
		if nums[i] in nums[i+1:len(nums)]:
	
			return True

	return False
```
buttttt apparently this was O(n^2) and the compiler kept showing timeout error because duhhh
soo a better way to solve this problem is to use a hashset its basically a hash map wait lemme see properly how it works
ok its the same as hash maps in c taught in class ahem taught myself
so the solution for this question using hashset is 


```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        hashset = set()

        for n in nums:
            if n in hashset:
                return True
            hashset.add(n)
        return False
```
```


