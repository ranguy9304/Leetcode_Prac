TOPIC : [[BINARY WHERE]]
`2023-07-15

## TOPIC INFO 
Koko loves to eat bananas. There are `n` piles of bananas, the `ith` pile has `piles[i]` bananas. The guards have gone and will come back in `h` hours.

Koko can decide her bananas-per-hour eating speed of `k`. Each hour, she chooses some pile of bananas and eats `k` bananas from that pile. If the pile has less than `k` bananas, she eats all of them instead and will not eat any more bananas during this hour.

Koko likes to eat slowly but still wants to finish eating all the bananas before the guards return.

Return _the minimum integer_ `k` _such that she can eat all the bananas within_ `h` _hours_.

ok so here we are told that k can be only as large as the largest element i the pile therefore we can brute force this by cheking all the digits from 1 to max(pile) the largest value will obviously satisfy but we need the least therefore there will be a index after which all will be valid therefore we can use binary search and find the element fast by checking if it still satisfies or not
answer


```python
class Solution:
    def minEatingSpeed(self, piles: List[int], h: int) -> int:
        l, r = 1, max(piles)
        res = max(piles)

        while l <= r:
            k = (l + r) // 2

            totalTime = 0
            for p in piles:
                totalTime += math.ceil(p / k)
            if totalTime <= h:
                res = min(res, k)
                r = k - 1
            else:
                l = k + 1
        return res

```





### BRIEF



### CONCLUSION