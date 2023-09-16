TOPIC : [[ARRAYS AND HASHING]]
`2023-07-08

## TOPIC INFO 
here the question in question was 
Given two strings `s` and `t`, return `true` _if_ `t` _is an anagram of_ `s`_, and_ `false` _otherwise_.

An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

sooo now learning from the pervious naiveness from the duplicate question i used hashmaps to keep track of the elements and a dictionary to keep track of the repeating elements soo we get

```python
class Solution:
def isAnagram(self, s: str, t: str) -> bool:
	hashset=set()	
	rep={}	
	for i in s:	
		if i not in hashset:		
		hashset.add(i)		
		rep[i]=1		
		else:		
		rep[i]=rep[i]+1	
	for i in t:	
	# print(rep)	
		if i not in hashset:		
			return False		
		else:		
			if rep[i] != 1:		
				rep[i]=rep[i]-1		
			else:		
				hashset.remove(i)	
	if len(hashset) == 0:	
		return True	
	return False
```
this solution gave results 
![[Pasted image 20230708135032.png]]
the one given by the yt guy beats only 43% and he only uses dictionary lets see what the comments have

apparenty the best solution is just sorting both the string and equating them beating 70% people 

```python
sorted(s)==sorted(t)
```
