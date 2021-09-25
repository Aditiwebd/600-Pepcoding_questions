# Q1.
[Question_Link](https://leetcode.com/problems/path-sum-iii/)
```class Solution {
public:
    int pathSum_A(TreeNode* root,int targetSum){
        if(root==NULL)
            return 0;
        int res=0;
        if(root->val==targetSum)
            res++;
        res+=pathSum_A(root->left,targetSum-root->val);
        res+=pathSum_A(root->right,targetSum-root->val);
        
        return res;
    }
    int pathSum(TreeNode* root, int targetSum) {
        if(root==NULL)
            return 0;
        
        return pathSum(root->left,targetSum)+pathSum(root->right,targetSum)
            +pathSum_A(root,targetSum);
    }
};

```
I am not sure about the time complexity but I think its O(n^2)
Well for each node we check whether to include it or not. So it's like a subsequence but in a tree. It may be exponential also.
Well the space complexity is O(n+n) function stack for each of the function.
