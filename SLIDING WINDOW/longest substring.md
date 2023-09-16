TOPIC : [[SLIDING WINDOW]]
`2023-07-19

## TOPIC INFO 
Given a string `s`, find the length of the **longest**
**substring**
without repeating characters.
more of a [[TWO POINTERS]] question
ok here also we use two pointer to go through the string we start with both a and b at index 0 and we add the element at b to a set and keep on incrementing b  and check if the current element of b is in the set or not if the element is not in the set that means its not repeating therefore we increment the local count and increment b and add the current element of b to the set and if the element isnt present in the set we remove the element of a from the set and incremnt a and reduce the local counter by and before decrementing we check if that was the largest string count recored 
```python
class Solution:

def lengthOfLongestSubstring(self, s: str) -> int:

# s=s.replace(" ","1")

# print(s)

# print(len(s))

a=0

b=0

maxi=0

ref=set()

temp=0

while b<len(s):

if s[b] not in ref:

ref.add(s[b])

b+=1

temp+=1

else :

ref.remove(s[a])

a+=1

if temp>maxi:

maxi=temp

temp-=1

if temp>maxi:

maxi=temp

return maxi
```



### BRIEF



### CONCLUSION