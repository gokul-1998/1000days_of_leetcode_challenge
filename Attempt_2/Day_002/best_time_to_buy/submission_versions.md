# This document has different versions of the submission  for Day 2 problem.

## Submission 1:
```
class Solution:
    def maxProfit(self,prices):
        left=0
        right=1
        max_profit=0
        while right<len(prices):
            curr_profit=prices[right]-prices[left]
            if prices[right]>prices[left]:
                max_profit=max(max_profit,curr_profit)
            else:
                left=right
            right+=1
        return max_profit
```
    - left will be the minimum price that we will see.
    - The else is when the  right is less than the current  left