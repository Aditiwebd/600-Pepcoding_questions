# Q3. [Right View of The Tree](https://leetcode.com/problems/binary-tree-right-side-view/)
```
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    vector<int> rightSideView(TreeNode* root) {
        vector<int> ans;
        if(root==NULL)
            return ans;
        deque<TreeNode*> q;
        q.push_back(root);
        
        while(q.size()>0){
            TreeNode* temp=q.back();
            
            ans.push_back(temp->val);
            int t=q.size();
            //cout<<t<<endl;
            while(t--){
                TreeNode* anoTemp=q.front();
                q.pop_front();
                if(anoTemp->left != NULL)
                    q.push_back(anoTemp->left);
            
                if(anoTemp->right != NULL)
                    q.push_back(anoTemp -> right);
            }
        }
        return ans;
    }
};
```
