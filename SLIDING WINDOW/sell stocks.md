TOPIC : [[SLIDING WINDOW]]
`2023-07-19
more of a [[TWO POINTERS]] question
## TOPIC INFO  
You are given an array `prices` where `prices[i]` is the price of a given stock on the `ith` day.

You want to maximize your profit by choosing a **single day** to buy one stock and choosing a **different day in the future** to sell that stock.

Return _the maximum profit you can achieve from this transaction_. If you cannot achieve any profit, return `0`.

ok so here we can use two pointers where the first and second one are initialised with the same index and the second one keeps on moving and if the value of the second pointer is less than first one its the first one is moved to the index of second and if the value at second pointer is greater than first we calculate the profit and keep track of the greatest

```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        res = 0
        
        lowest = prices[0]
        for price in prices:
            if price < lowest:
                lowest = price
            res = max(res, price - lowest)
        return res

```






### BRIEF



### CONCLUSION