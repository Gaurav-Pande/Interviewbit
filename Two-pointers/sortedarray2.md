#Remove Duplicates from Sorted Array II

Remove Duplicates from Sorted Array

Given a sorted array, remove the duplicates in place such that each element can appear atmost twice and return the new length.

Do not allocate extra space for another array, you must do this in place with constant memory.

Note that even though we want you to return the new length, make sure to change the original array as well in place

For example,
Given input array A = [1,1,1,2],

Your function should return length = 3, and A is now [1,1,2].

#Solution:

```java
public class Solution {
	public int removeDuplicates(ArrayList<Integer> a) {
	int j=1;
	boolean flag =false;
	if(a.size()<=2){
	    return a.size();
	}
	int i=0;
	while(i<a.size()&&j<a.size()){
	    if(a.get(j).equals(a.get(j-1))){
	        if(flag==false){
	            i++;
	            a.set(i,a.get(j));
	            flag=true;
	        }
	        j++;
	    }
	    else{
	        i++;
	        a.set(i,a.get(j));
	        j++;
	        flag=false;
	    }
	}
	return i+1;
	    
	}
}

```
