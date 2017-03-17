# Cycle Detection in  a Linked List

## Problem:

Given a linked list, return the node where the cycle begins. If there is no cycle, return null.

Try solving it using constant additional space.

Example :

Input : 

                  ______
                 |     |
                 \/    |
        1 -> 2 -> 3 -> 4

Return the node corresponding to node 3. 


## Solution:

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
	public ListNode detectCycle(ListNode head) {
	    ListNode first,second;
	    first=head;
	    second = head;
	    
	   
	        while(second != null && second.next !=null){
	            first= first.next;
	            second = second.next.next;
	            if(second==first){
	                first = head;
	                while(first.val!=second.val){
	                    first= first.next;
	                    second = second.next;
	                }
	                return first;
	            }
	        }
	      
	    return null;
	 
	}
}





```
