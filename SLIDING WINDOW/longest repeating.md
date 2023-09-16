TOPIC : [[SLIDING WINDOW]]
`2023-07-19

## TOPIC INFO 
You are given a string `s` and an integer `k`. You can choose any character of the string and change it to any other uppercase English character. You can perform this operation at most `k` times.

Return _the length of the longest substring containing the same letter you can get after performing the above operations_.

here we can obvio brute force but no we will use a [[TWO POINTERS]] type thing for the sliding window where we init two pointers at the initial position and we use dictionary to store the frequence of each element and we substract the length of the string from the max frequency in the window to get the letters to be replaced if its less than < k then its a valid window or else we increment the left pointer and remove the previous element from the dictionary and if the window is valid then we increment the right pointer and keep track of the heighest length ... this is a 26n time complexity we can get it down to n by not finding the max frequency from the dictionary everytime and only keeping track of the max frequency thats ever been measured and solution will always have the max frequncy of elements posible in the array.

```python
class Solution:
    def characterReplacement(self, s: str, k: int) -> int:
        count = {}
        
        l = 0
        maxf = 0
        for r in range(len(s)):
            count[s[r]] = 1 + count.get(s[r], 0)
            maxf = max(maxf, count[s[r]])

            if (r - l + 1) - maxf > k:
                count[s[l]] -= 1
                l += 1

        return (r - l + 1)

```



### BRIEF



### CONCLUSION