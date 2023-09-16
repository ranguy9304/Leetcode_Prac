TOPIC : [[ARRAYS AND HASHING]]
`2023-07-08

## TOPIC INFO 
the question was 
Given an array of strings `strs`, group **the anagrams** together. You can return the answer in **any order**.

An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

ok so the first approach was to just use the previous anagram solution is sorted one to brute force through but obviously its not fast enough sooo i was thinking of hashmaps and how to use them in this because obvio we have to use hashmaps everywhere to make it faster sooo i planned to use hashmaps to store the copy of everynew string with unique letters found using the sorted function that was also used as a solution in the og anagram question sooo now i am storing the sorted strings in a hashmap and using the is in thingi to find anagrams and also i have a dictionary to keep track of all the same anagrams this i thought was enough buttt 
```python

class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        hashset=set()
        dick={}
        for n,i in enumerate(strs):
            # print(i)
            # print(n)
            if tuple(sorted(i)) not in hashset:
                hashset.add(tuple(sorted(i)))
                dick[tuple(sorted(i))]=[n]
            else:
                dick[tuple(sorted(i))].append(n)
        anstot=[]
        for key in dick:
            an=[]
            for i in dick[key]:
                an.append(strs[i])
            print(an)
            anstot.append(an)
        return anstot
```

![[Pasted image 20230708183815.png]]
bruh



apparenty this is the sol
```python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        ans = collections.defaultdict(list)

        for s in strs:
            count = [0] * 26
            for c in s:
                count[ord(c) - ord("a")] += 1
            ans[tuple(count)].append(s)
        return ans.values()
```
imma learn this after coming back hold up
### BRIEF



### CONCLUSION