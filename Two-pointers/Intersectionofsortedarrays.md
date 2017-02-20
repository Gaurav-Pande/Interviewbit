#Intersection of two sorted arrays

Find the intersection of two sorted arrays.
OR in other words,
Given 2 sorted arrays, find all the elements which occur in both the arrays.

Example :

Input : 
    A : [1 2 3 3 4 5 6]
    B : [3 3 5]

Output : [3 3 5]

Input : 
    A : [1 2 3 3 4 5 6]
    B : [3 5]

Output : [3 5]


#Solution:

```java
public class Solution {
	// DO NOT MODIFY THE LISTS
	public ArrayList<Integer> intersect(final List<Integer> a, final List<Integer> b) {
    ArrayList<Integer> result = new ArrayList<Integer>();
    for(int i=0,j=0;i<a.size() && j<b.size();){
        if(a.get(i).intValue()==b.get(j).intValue()){
            result.add(a.get(i).intValue());
            i++;
            j++;
        }
        else if(a.get(i).intValue()<b.get(j).intValue()){
            i++;
        }
        else{
            j++;
        }
    }
    return result;
}
}
```
