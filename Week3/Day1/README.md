1) Linked list cycle
   public class Solution {
    public boolean hasCycle(ListNode head) {
       ListNode slow=head;
       ListNode fast=head;
       while(fast!=null && fast.next!=null){
        slow=slow.next;
        fast=fast.next.next;
        if(slow==fast){
            return true;
        }
       }
       return false; 
    }
}


2) Reverse linked list
   class Solution {
    public ListNode reverseList(ListNode head) {
      ListNode prev=null;
      ListNode curr=head;
      while(curr!=null){
         ListNode next= curr.next;
         curr.next=prev;
         prev=curr;
         curr=next;
      }
     return prev;
    }
}

3) Middle of the linked list
   class Solution {
    public ListNode middleNode(ListNode head) {
    ListNode slow=head;
    ListNode fast= head;
    while(fast!= null && fast.next!=null){
        slow=slow.next;
        fast=fast.next.next;
    } 
    return slow;   
    }
}
