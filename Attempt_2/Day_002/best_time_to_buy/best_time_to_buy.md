- https://leetcode.com/problems/best-time-to-buy-and-sell-stock/submissions/1164107137/


## Solution 0
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


## Solution 1
```
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        res=0
        left=prices[0]
        for right in prices:
            diff=right-left
            if diff>0 :
                if  diff>res:
                     res=diff
                    # we are doing it like this because we should  go to 
                    # else only when diff <= 0
            else:
                left=right
        return res
                

```


## Solution 2
```
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        max_diff = 0
        current_max = float("-inf")
        current_min = float("inf")

        for p in prices:
            if p < current_min:
                current_min = p
                current_max = p
            if p > current_max:
                current_max = p
                max_diff = max(max_diff,current_max-current_min)

        return(max_diff)
```

## Solution 3
```
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        min_price = prices[0]
        max_profit = 0

        for price in prices:

            if price < min_price:
                min_price = price

            current_profit = price - min_price

            if current_profit > max_profit:
                max_profit = current_profit
            
        return max_profit
```

## Solution 4
```
class Solution:
    def maxProfit(self,prices):
        left = 0 #Buy
        right = 1 #Sell
        max_profit = 0
        while right < len(prices):
            currentProfit = prices[right] - prices[left] #our current Profit
            if prices[left] < prices[right]:
                max_profit =max(currentProfit,max_profit)
            else:# if the  right  is less than left update the left , and move right to 1 step, Note left is always the minimum  value
                left = right
            right += 1
        return max_profit
```
aliter solution 4
```
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        first_day,second_day=0,1
        maxP=0
        no_of_days=len(prices)
        while second_day<no_of_days:
            if  prices[first_day]<prices[second_day]:
                profit=prices[second_day]-prices[first_day]
                maxP=max(maxP,profit)
            else:# if the  right  is less than left update the left , and move right to 1 step
                first_day=second_day
            second_day+=1
        return maxP
```
