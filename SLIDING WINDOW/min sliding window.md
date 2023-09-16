TOPIC : [[SLIDING WINDOW]]

`2023-07-20

## TOPIC INFO 
Given two strings `s` and `t` of lengths `m` and `n` respectively, return _the **minimum window**_

**_substring_**

_of_ `s` _such that every character in_ `t` _(**including duplicates**) is included in the window_. If there is no such substring, return _the empty string_ `""`.

The testcases will be generated such that the answer is **unique**.

**Example 1:**

**Input:** s = "ADOBECODEBANC", t = "ABC"
**Output:** "BANC"
**Explanation:** The minimum window substring "BANC" includes 'A', 'B', and 'C' from string t.


we use two hashmaps one for t and one for s where in the hashmap for t we store (lets call hashmap for t as t and window as w ) ok so in t we count the frequency of each charater and in w map we have a sliding window in s where we start with a charater and check if that character is in W ( W map has only the characters in t) we increment the frequency of that particular element 
and we have a global variable "have " which keeps track of how many frequencies we have satisfied therefore after incrementing the frequency we check if its == to the equivalent in T map if it is we increment the value in "have " by one and it should only be done when == and not >= 
have will be  compared to the length of T and if its matched we store the indices and length into a dict or an array and then we start incrementing left pointer till HAVE unmatches and in the process store the indices and length for each step then after it unmatches we again repeat the process and start incrementing the right pointer til the HAVE matches again and again we store the indices and  we increment the left pointer

```python
class Solution:
    def minWindow(self, s: str, t: str) -> str:
        if t == "":
            return ""

        countT, window = {}, {}
        for c in t:
            countT[c] = 1 + countT.get(c, 0)

        have, need = 0, len(countT)
        res, resLen = [-1, -1], float("infinity")
        l = 0
        for r in range(len(s)):
            c = s[r]
            window[c] = 1 + window.get(c, 0)

            if c in countT and window[c] == countT[c]:
                have += 1

            while have == need:
                # update our result
                if (r - l + 1) < resLen:
                    res = [l, r]
                    resLen = r - l + 1
                # pop from the left of our window
                window[s[l]] -= 1
                if s[l] in countT and window[s[l]] < countT[s[l]]:
                    have -= 1
                l += 1
        l, r = res
        return s[l : r + 1] if resLen != float("infinity") else ""

```





### BRIEF



### CONCLUSION