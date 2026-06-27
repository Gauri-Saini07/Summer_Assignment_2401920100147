1) Path sum
class Solution {
    public boolean hasPathSum(TreeNode root, int targetSum) {
        if(root==null){
            return false;
        }
        if(root.left==null && root.right==null){
          return targetSum == root.val;  
        }
        return hasPathSum(root.left, targetSum-root.val)||
        hasPathSum(root.right, targetSum-root.val);

    }
}

2) Diameter of binary tree
   class Solution {
    int diameter=0;
    public int diameterOfBinaryTree(TreeNode root) {
        height(root);
        return diameter;
    }
    private int height(TreeNode root){
        if(root==null){
            return 0;
        }
        int left= height(root.left);
        int right= height(root.right);
        diameter=Math.max(diameter,left+right);
        return 1+ Math.max(left,right);
    }
}

3) Binary tree maximum path sum
   class Solution {
    int maxSum= Integer.MIN_VALUE;
    public int maxPathSum(TreeNode root) {
        dfs(root);
        return maxSum;}
        private int dfs(TreeNode root){
            if(root==null){
                return 0;
            }
            int left= Math.max(0,dfs(root.left));
            int right= Math.max(0,dfs(root.right));
            maxSum =Math.max(maxSum,left + root.val+ right);
            return root.val+ Math.max(left,right);
        }
    }
