1) Search in a binary search tree
   class Solution {
    public TreeNode searchBST(TreeNode root, int val) {
        if(root==null || root.val==val){
            return root;
        }
        if(val<root.val){
            return searchBST(root.left,val);
        }
        return searchBST(root.right,val);
    }
}

2) Validate binary search tree
   class Solution {
    public boolean isValidBST(TreeNode root) {
       return validate(root, Long.MIN_VALUE, Long.MAX_VALUE); 
    }
    private boolean validate(TreeNode node, long min, long max){
        if(node==null){
            return true;
        }
        if(node.val <=min ||node.val>=max){
            return false;
        }
        return validate(node.left,min,node.val)
               && validate(node.right,node.val,max);
    }
}

3) Lowset common ancestor of a binary search tree
   class Solution {
    //bst
    public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        if(p.val<root.val && q.val<root.val){
            return lowestCommonAncestor(root.left,p,q);
        }
        if(p.val>root.val && q.val>root.val){
            return lowestCommonAncestor(root.right,p,q);
        }
        return root;
    }
}
