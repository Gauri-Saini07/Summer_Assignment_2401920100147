1) Implement queue using stacks
   class MyQueue {
     Stack<Integer> input;
     Stack<Integer> output;
    public MyQueue() {
      input=new Stack<>();
      output= new Stack<>();  
    }
    
    public void push(int x) {
        input.push(x);
    }
    
    public int pop() {
        peek();
        return output.pop();
    }
    
    public int peek() {
        if(output.isEmpty()){
            while(!input.isEmpty()){
                output.push(input.pop());
            }
        }
        return output.peek();
    }
    
    public boolean empty() {
       return input.isEmpty()
            && output.isEmpty(); 
    }
}

2) Number of recent calls
   class RecentCounter {
      Queue <Integer> queue;
    public RecentCounter() {
        queue=new LinkedList<>();
    }
    
    public int ping(int t) {
        queue.offer(t);
        while(queue.peek()<t -3000){
            queue.poll();
        }
        return queue.size();
    }
}

3) Sliding window maximum
   class Solution {
    public int[] maxSlidingWindow(int[] nums, int k) {
        int n =nums.length;
        int[] ans= new int[n-k+1];
        Deque<Integer> deque=new LinkedList<>();
        int index=0;
        for(int i=0;i<n;i++){
            while(!deque.isEmpty() && deque.peekFirst()<=i-k){
                deque.pollFirst();
            }
            while(!deque.isEmpty()&& nums[deque.peekLast()]< nums[i]){
                deque.pollLast();
            }
            deque.offerLast(i);
            if(i>=k-1){
                ans[index++]=nums[deque.peekFirst()];
            }
        }
        return ans;
    }
}
