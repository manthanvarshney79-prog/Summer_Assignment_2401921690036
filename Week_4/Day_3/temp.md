1. Search in a Binary Search Tree :-

struct TreeNode* searchBST(struct TreeNode* root, int val) {
    if(root==NULL || root->val==val){
        return root;
    }
    if(val<root->val){
        return searchBST(root->left,val);
    }
    return searchBST(root->right,val);
}

2. Validate Binary Search Tree :-

bool check(struct TreeNode* root, long min, long max) {
    if(root==NULL){
        return true;
    }
    if(root->val<=min || root->val>=max){
        return false;
    }
    return check(root->left, min, root->val) &&
           check(root->right, root->val, max);
}
bool isValidBST(struct TreeNode* root) {
    return check(root, LONG_MIN, LONG_MAX);
}

3. Lowest Common Ancestor of a BST :-

struct TreeNode* lowestCommonAncestor(struct TreeNode* root, struct TreeNode* p, struct TreeNode* q) {
    if(root==NULL ||root==p || root==q){
        return root;
    }
    struct TreeNode* left = lowestCommonAncestor(root->left, p, q);
    struct TreeNode* right = lowestCommonAncestor(root->right, p, q);
    if(left!=NULL && right!=NULL){
        return root;
    }
    if(left!=NULL){
        return left;
    }
    return right;
}
