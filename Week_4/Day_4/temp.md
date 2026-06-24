1. Path Sum :-

bool hasPathSum(struct TreeNode* root, int targetSum) {
    if(root==NULL){
        return false;
    }
    if(root->left==NULL && root->right==NULL){
        return targetSum == root->val;
    }
    return hasPathSum(root->left, targetSum - root->val) ||
           hasPathSum(root->right, targetSum - root->val);
}

2. Diameter of Binary Tree :-

int maxDiameter=0;
int height(struct TreeNode* root) {
    if(root==NULL){
        return 0;
    }
    int left=height(root->left);
    int right=height(root->right);
    if(left+right>maxDiameter){
        maxDiameter=left+right;
    }
    return 1+(left>right?left:right);
}
int diameterOfBinaryTree(struct TreeNode* root) {
    maxDiameter=0;
    height(root);
    return maxDiameter;
}

3. Binary Tree Maximum Path Sum :-

int maxSum;
int dfs(struct TreeNode* root) {
    if(root==NULL){
        return 0;
    }
    int left=dfs(root->left);
    int right=dfs(root->right);
    if(left<0){
        left=0;
    }
    if(right<0){
        right=0;
    }
    int current=root->val+left+right;
    if(current>maxSum){
        maxSum=current;
    }
    return root->val+(left>right?left:right);
}
int maxPathSum(struct TreeNode* root) {
    maxSum=root->val;
    dfs(root);
    return maxSum;
}
