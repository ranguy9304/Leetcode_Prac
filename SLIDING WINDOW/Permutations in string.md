TOPIC : [[SLIDING WINDOW]]
`2023-07-19

## TOPIC INFO 
Given two strings `s1` and `s2`, return `true` _if_ `s2` _contains a permutation of_ `s1`_, or_ `false` _otherwise_.

In other words, return `true` if one of `s1`'s permutations is the substring of `s2`.

basicaly use a dictionary to store the frequency of elements in the s1 and go through the second string using [[TWO POINTERS]] and check if all the elements in the window have only the elements in the dictionary by checking if the dictionry is empty or not ...basically  standard sliding window approach hai bhai get good

```python
class Solution:

def checkInclusion(self, s1: str, s2: str) -> bool:

ref={}

for i in s1:

if i in ref:

ref[i]+=1

else:

ref[i]=1

a=0

b=0

while b<len(s2):

  

if s2[b] in ref:

if ref[s2[b]]>1:

ref[s2[b]]-=1

else:

ref.pop(s2[b])

b+=1

else:

if s2[a] in ref:

ref[s2[a]]+=1

else:

ref[s2[a]]=1

a+=1

if len(ref)==0:

return True

return False
```

![[Pasted image 20230719131337.png]]


### BRIEF



### CONCLUSION