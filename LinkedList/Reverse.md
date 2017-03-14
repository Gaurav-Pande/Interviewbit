# Reversing a Linked List


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
	public ListNode reverseList(ListNode a) {
	    ListNode first,second,temp;
	first=a;
	second=a.next;
	temp=second;
	while(second!=null){
	   second = second.next;
	   temp.next = first;
	   first = temp;
	   temp=second;
	    
	}
	a.next=null;
	a = first;
	return a;
	}
}


```
