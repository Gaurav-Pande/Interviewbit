# Sort a linked list in O(n log n) time using constant space complexity.

Example :

Input : 1 -> 5 -> 4 -> 3

Returned list : 1 -> 3 -> 4 -> 5


## Solution


```
java
/**
 * Definition for singly-linked list.
 * class ListNode {
 *     public int val;
 *     public ListNode next;
 *     ListNode(int x) { val = x; next = null; }
 * }
 */
public class Solution {
    
    public ListNode sortList(ListNode head) {
    if(head ==null || head.next == null){
        return head;
    }      
    ListNode slow = head;
    ListNode fast = head.next;
    
    while(fast != null && fast.next != null){
        fast = fast.next.next;
        slow = slow.next;
    }
    
    
    ListNode sec_head = slow.next;
    slow.next = null;
    
    ListNode first = sortList(head);
    ListNode Last = sortList(sec_head);
    
    ListNode new_head;
    ListNode temp = new ListNode(-1);
    new_head = temp;
    
    while(first!=null && Last!=null){
      if(first.val< Last.val){
        temp.next = first;
        first = first.next;
    }
    else{
        temp.next = Last;
        Last = Last.next;
    }  
    temp = temp.next;
    }
    
    
    while(first != null){
        temp.next = first;
        temp = temp.next;
        first = first.next;
    }
    
    while(Last !=null){
        temp.next = Last;
        temp = temp.next;
        Last = Last.next;
        
    }
    
    
    return new_head.next;

}
}







```
