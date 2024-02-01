- https://leetcode.com/problems/two-sum/description/

```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        dict={} # this  dict is  used to store the target-n (complement), so as soon as we find the complement, we shall return t
        for i,n in enumerate(nums):
            if n in dict: # 
                return dict[n],i
            else:
                dict[target-n]=i


```