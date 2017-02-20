#3 Sum Zero


Given an array S of n integers, are there elements a, b, c in S such that a + b + c = 0? 
Find all unique triplets in the array which gives the sum of zero.

Note:

 Elements in a triplet (a,b,c) must be in non-descending order. (ie, a ≤ b ≤ c)
The solution set must not contain duplicate triplets. For example, given array S = {-1 0 1 2 -1 -4}, A solution set is:
(-1, 0, 1)
(-1, -1, 2) 

#Solution

```java
public class Solution {
	public ArrayList<ArrayList<Integer>> threeSum(ArrayList<Integer> a) {
	    ArrayList<ArrayList<Integer>> res = new ArrayList<>();
	    Collections.sort(a);
	    int len=a.size()-1;
	    for(int i=0;i<len-1;i++){
	          if (i > 0 && a.get(i).equals(a.get(i - 1))) {
                continue;
            }
	        int left=i+1;
	        int right=len;
	        while(left<right){
	        int sum = a.get(i) + a.get(left) + a.get(right);
	        if(sum==0){
	            res.add(new ArrayList<>(Arrays.asList(a.get(i), a.get(left), a.get(right))));
	            int leftV = a.get(left);
	            while(left<right && leftV==a.get(left)){
	                left++;
	            }
	            int rightV=a.get(right);
	            while(left<right && a.get(right)==rightV){
	                right--;
	            }
	        }
	        else if(sum<0){
	            left++;
	        }
	        else{
	            right--;
	        }
	        
	    }
	    }
	    return res;
	}
}

```
