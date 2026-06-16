1) Merge two sorted list
   class Solution {
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        ListNode dummy=new ListNode(0);
        ListNode current = dummy;
        while(list1!=null && list2!=null){
            if(list1.val<=list2.val){
                current.next=list1;
                list1=list1.next;
            }
            else{
                current.next=list2;
                list2=list2.next;
            }
            current=current.next;
        }
       if(list1!= null){
        current.next=list1;
       }
       if(list2!= null){
        current.next=list2;
       }
       return dummy.next;
    }
}

2) Remove nth node from end of list
   class Solution {
    public ListNode removeNthFromEnd(ListNode head, int n) {
       ListNode dummy=new ListNode(0);
       dummy.next=head;
       ListNode slow= dummy;
       ListNode fast=dummy;
       for(int i =0;i<=n;i++){
        fast=fast.next;
       }
       while(fast!=null){
        slow=slow.next;
        fast=fast.next;
       }
       slow.next=slow.next.next;
       return dummy.next; 
    }
}

3) Palindrome linked list
   class Solution {
    public boolean isPalindrome(ListNode head) {
    ListNode slow=head;
    ListNode fast=head;
    while(fast!=null && fast.next!=null){
        slow=slow.next;
        fast=fast.next.next;
    } 
    ListNode prev=null;
    while(slow!=null){
        ListNode next=slow.next;
        slow.next=prev;
        prev=slow;
        slow=next;
    } 
    ListNode first=head;
    ListNode second=prev;
    while(second!=null){
        if(first.val!=second.val){
            return false;
        }
        first=first.next;
        second=second.next;
    }  
    return true;
    }
}
