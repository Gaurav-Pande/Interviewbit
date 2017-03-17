# Reverse Part II

## Problem:

Reverse a linked list from position m to n. Do it in-place and in one-pass.

For example:
Given 1->2->3->4->5->NULL, m = 2 and n = 4,

return 1->4->3->2->5->NULL.

 Note:
Given m, n satisfy the following condition:
1 ≤ m ≤ n ≤ length of list. Note 2:
Usually the version often seen in the interviews is reversing the whole linked list which is obviously an easier version 
of this question. 


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
	public ListNode reverseBetween(ListNode head, int m, int n) {
	  if ( head == null || m >= n) {
			return head;
		}
    ListNode start,last,temp;
	start=head;
	temp=head;
	last=head;
	int x=m;
	int y=n;
	while(m>2){
		m--;
		temp=temp.next;
		}
	start= temp;
	
	while(n>1){
		last=last.next;
		n--;
	}
	
	if(x==y){
		return head;
	}
//Need to check boundry condition always. Here what if we call reverseii(head, 1,n).
	if(x==1){
		ListNode first=start;
		ListNode second = first.next;
		temp = second;
		while(second.val!=last.val){
			second=second.next;
			temp.next=first;
			first=temp;
			temp=second;
		}
		start.next = last.next;
		last.next=first;
		
		head=last;
	}
	else{
		ListNode first=start.next;
		ListNode second = first.next;
		temp = second;
		while(second.val!=last.val){
			second=second.next;
			temp.next=first;
			first=temp;
			temp=second;
		}
	start.next.next = last.next;
	last.next=first;
	start.next = last;} 
	return head;
	



	}
	}




```
