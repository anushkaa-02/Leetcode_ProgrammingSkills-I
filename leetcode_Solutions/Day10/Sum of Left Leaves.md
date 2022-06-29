# Sum of Left Leaves
- ## Question:
>Given the `root` of a binary tree, return the sum of all left leaves.
>
>A leaf is a node with no children. A left leaf is a leaf that is the left child of another node.

- Example :

      Input: root = [3,9,20,null,null,15,7]
      Output: 24
      Explanation: There are two left leaves in the binary tree, with values 9 and 15 respectively.
      
- ## Solution:
```cpp
class Solution {
public:
    void solve(TreeNode*root,int &sum,bool a=true)
    {
        if(!root)
            return ;
        solve(root->left,sum,true);
        if(root->left==NULL&&root->right==NULL&&a)
            sum+=root->val;
        solve(root->right,sum,false);
    }
    int sumOfLeftLeaves(TreeNode* root) {
        
        if(!root)
            return 0;
        if(!root->left&&!root->right)
            return 0;
        int sum=0;
        solve(root,sum);
        return sum;
    }
};
```

## Tags
`Tree` `Depth first search`
