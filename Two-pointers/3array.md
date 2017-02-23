You are given 3 arrays A, B and C. All 3 of the arrays are sorted.

Find i, j, k such that :
max(abs(A[i] - B[j]), abs(B[j] - C[k]), abs(C[k] - A[i])) is minimized.
Return the minimum max(abs(A[i] - B[j]), abs(B[j] - C[k]), abs(C[k] - A[i]))

**abs(x) is absolute value of x and is implemented in the following manner : **

      if (x < 0) return -x;
      else return x;
Example :

Input : 
        A : [1, 4, 10]
        B : [2, 15, 20]
        C : [10, 12]

Output : 5 
         With 10 from A, 15 from B and 10 from C. 
         
#Solution:

```java
public class Solution {
	// DO NOT MODIFY THE LISTS
	public int minimize(final List<Integer> a, final List<Integer> b, final List<Integer> c) {
    int i=0;
    int j=0;
    int k=0;
    int result = Integer.MAX_VALUE;
	while(i<a.size()&&j<b.size()&&k<c.size()){
	    int max = Math.max(Math.max(a.get(i),b.get(j)),c.get(k));
	    int min = Math.min(Math.min(a.get(i),b.get(j)),c.get(k));
	    result = Math.min(result,max-min);
	    if(i<a.size() && a.get(i)==min){
	        i++;
	    }
	    if(j<b.size() && b.get(j)==min){
	        j++;
	    }
	    if(k<c.size() && c.get(k)==min){
	        k++;
	    }
	    
	}
	return result;
	    
	    
	}
}

```
