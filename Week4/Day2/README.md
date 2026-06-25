1) Biinary tree order traversal
   class Solution {
    List<Integer> ans=new ArrayList<>();
    public List<Integer> inorderTraversal(TreeNode root) {
      inorder(root);
      return ans;}
     private void inorder(TreeNode node){
        if(node==null){
            return;
        }
        inorder(node.left);
        ans.add(node.val);
        inorder(node.right);
      }  
    }

2) Binary tree level order traversal
   class Solution {
    public List<List<Integer>> levelOrder(TreeNode root) {
     List<List<Integer>> ans= new ArrayList<>();
     if(root==null){
        return ans;
     }  
     Queue<TreeNode> q=new LinkedList<>();
     q.offer(root);
     while(!q.isEmpty()){
        int size=q.size();
        List<Integer> level=new ArrayList<>();
        for(int i =0;i<size;i++){
            TreeNode curr=q.poll();
            level.add(curr.val);
            if(curr.left!=null){
                q.offer(curr.left);
            }
            if(curr.right!=null){
                q.offer(curr.right);
            }
        }
        ans.add(level);
     } 
     return ans;
    }
}

3) Binary tree zigzag level order traversal
   class Solution {
    public List<List<Integer>> zigzagLevelOrder(TreeNode root) {
     List<List<Integer>> ans = new ArrayList<>();
     if(root==null){
        return ans;
     }
     Queue<TreeNode> q =new LinkedList<>();
     q.offer(root);
     boolean leftToRight=true;
     while(!q.isEmpty()){
     int size=q.size();
     LinkedList<Integer> level =new LinkedList<>();
     for(int i=0;i<size;i++){
        TreeNode curr=q.poll();
        if(leftToRight){
            level.addLast(curr.val);
        }
        else{
            level.addFirst(curr.val);
        }
        if(curr.left!=null){
            q.offer(curr.left);
        }
        if(curr.right!=null){
            q.offer(curr.right);
        }
     }
     ans.add(level);   
     leftToRight =! leftToRight;
    }
    return ans;
    }
}
