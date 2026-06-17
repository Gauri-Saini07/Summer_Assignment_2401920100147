1) Valid paranthesis
   class Solution {
    public boolean isValid(String s) {
       Stack<Character> stack=new Stack<>();
       for(char ch:s.toCharArray()) {
        if(ch=='(' || ch=='{' || ch=='['){
  stack.push(ch);}
else{
 if(stack.isEmpty()){
  return false;
}
char top=stack.pop();
 if((ch==')' && top!='(')||
 (ch=='}' && top!='{') ||
 (ch==']' && top!= '[')){
                    return false;
                }
        }
       }
       return stack.isEmpty();
    }
}

2) Min stack
   class MinStack {
    Stack<Integer> stack;
    Stack<Integer> minStack;
    public MinStack() {
      stack= new Stack<>();
      minStack=new Stack<>();  
    }
    
    public void push(int value) {
        stack.push(value);
        if(minStack.isEmpty()||value<=minStack.peek()){
            minStack.push(value);
        }
    }
    
    public void pop() {
        if(stack.peek().equals(minStack.peek())){
            minStack.pop();
        }
        stack.pop();
    }
    
    public int top() {
        return stack.peek();
    }
    
    public int getMin() {
        return minStack.peek();
    }
}

3) Next greater element 1
   class Solution {
    public int[] nextGreaterElement(int[] nums1, int[] nums2) {
      Stack<Integer> stack=new Stack<>();
      HashMap<Integer,Integer> map=new HashMap<>();
      for(int num: nums2){
       while(!stack.isEmpty() && num>stack.peek()){
        map.put(stack.pop(),num);
       }
       stack.push(num);
      } 
      while(!stack.isEmpty()){
        map.put(stack.pop(),-1);
      } 
      int[] ans=new int[nums1.length];
      for(int i =0;i<nums1.length;i++){
      ans[i]=map.get(nums1[i]);
      }
      return ans;
    }
}
