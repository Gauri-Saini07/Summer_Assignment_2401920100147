1) Maximum depth of binary tree
   class Solution {
    public int maxDepth(TreeNode root) {
        if(root==null){
            return 0;
        }
        int leftDepth=maxDepth(root.left);
        int rightDepth=maxDepth(root.right);
        return 1+ Math.max(leftDepth,rightDepth);
    }
}

2) Invert Binary Tree
   class Solution {
    public TreeNode invertTree(TreeNode root) {
        if(root==null){
            return null;
        }
        TreeNode temp=root.left;
        root.left=root.right;
        root.right=temp;
        invertTree(root.left);
        invertTree(root.right);
        return root;
    }
}

3) Same Tree
   class Solution {
    public boolean isSameTree(TreeNode p, TreeNode q) {
      if(p==null && q==null){
        return true;
      } 
      if(p==null || q==null){
        return false;
      } 
      if(p.val != q.val){
        return false;
      }
      return isSameTree(p.left,q.left)
       && isSameTree(p.right,q.right);
    }
}
