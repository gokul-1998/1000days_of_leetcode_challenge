- question link : https://leetcode.com/problems/root-equals-sum-of-children/description/

![](2023-01-05-23-30-12.png)
![](2023-01-05-23-30-27.png)

- question 
    ```
    # Definition for a binary tree node.
    # class TreeNode:
    #     def __init__(self, val=0, left=None, right=None):
    #         self.val = val
    #         self.left = left
    #         self.right = right
    class Solution:
        def checkTree(self, root: Optional[TreeNode]) -> bool:
    ```
    - solution
    ```
    # Definition for a binary tree node.
    # class TreeNode:
    #     def __init__(self, val=0, left=None, right=None):
    #         self.val = val
    #         self.left = left
    #         self.right = right
    class Solution:
        def checkTree(self, root: Optional[TreeNode]) -> bool:
            
            return root.left.val+root.right.val==root.val
    ```