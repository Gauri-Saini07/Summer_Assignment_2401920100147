1) Symmetric tree
   class Solution {
    public boolean isSymmetric(TreeNode root) {
        if(root==null){
            return true;}
    return isMirror(root.left,root.right);
        }
    private boolean isMirror(TreeNode left, TreeNode right){
        if(left==null && right==null){
            return true;
        }
        if(left==null || right==null){
            return false;
        }
        if(left.val!= right.val){
            return false;
        }
        return isMirror(left.left,right.right)&&
        isMirror(left.right,right.left);
    }  
    }

2) Construct binary tree form preoder
   class Solution {
    int preIndex=0;
      HashMap<Integer,Integer> map=new HashMap<>(); 
    public TreeNode buildTree(int[] preorder, int[] inorder) {
       for(int i =0;i<inorder.length;i++){
           map.put(inorder[i],i);
       }
       return build(preorder,0,inorder.length-1);
    }
    private TreeNode build(int[]preorder,int start,int end){
      if(start>end){
        return null;
      }
      TreeNode root =new TreeNode(preorder[preIndex++]);
      int index=map.get(root.val);
      root.left= build(preorder,start,index-1);
      root.right=build(preorder, index+1,end);
      return root;
    }
}

3) Serialise and deserialise binary
   public class Codec {

    // Encodes a tree to a single string.
    public String serialize(TreeNode root) {
      StringBuilder sb =new StringBuilder();
      preorder(root,sb);
      return sb.toString();  
    }
    private void preorder(TreeNode root, StringBuilder sb){
        if(root==null){
            sb.append("N,");
                 return;
        }
        sb.append(root.val).append(",");
        preorder(root.left,sb);
        preorder(root.right,sb);
    }
    int index=0;
    public TreeNode deserialize(String data) {
        String[]arr= data.split(",");
        index=0;
        return build(arr);
    }
    private TreeNode build(String[] arr){
        if(arr[index].equals("N")){
            index++;
            return null;
        }
        TreeNode root=new TreeNode(Integer.parseInt(arr[index++]));
        root.left=build(arr);
        root.right=build(arr);
        return root;
    }
}

