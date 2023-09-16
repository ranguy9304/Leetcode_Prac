TOPIC : [[STACKS]]
`2023-07-12

## TOPIC INFO 

Given `n` pairs of parentheses, write a function to _generate all combinations of well-formed parentheses_.
**Example 1:**

**Input:** n = 3
**Output:** ["((()))","(()())","(())()","()(())","()()()"]

**Example 2:**

**Input:** n = 1
**Output:** ["()"]

ohk i dont know what i was thinking on this one but i think i almost reached the answer but i was too sleepy and just slept thinking about it sooooo ya 

here you basically do the permutation wala thing calling the recursive function till the desired length is reached but here you keep count of the number of open brackets and closed brackets and stop when both of those equate to n or else if open > closed you can either add closed or open if open count != n
```python

class Solution:
    def generateParenthesis(self, n: int) -> List[str]:
        stack = []
        res = []

        def backtrack(openN, closedN):
            if openN == closedN == n:
                res.append("".join(stack))
                return

            if openN < n:
                stack.append("(")
                backtrack(openN + 1, closedN)
                stack.pop()
            if closedN < openN:
                stack.append(")")
                backtrack(openN, closedN + 1)
                stack.pop()

        backtrack(0, 0)
        return res

```
easy hai bro nahi samagh aya to bhencod vid dekh  le



### BRIEF



### CONCLUSION