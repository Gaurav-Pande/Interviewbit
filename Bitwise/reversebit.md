#Reverse bits

Reverse bits of an 32 bit unsigned integer

Example 1:

x = 0,

          00000000000000000000000000000000  
=>        00000000000000000000000000000000
return 0

Example 2:

x = 3,

          00000000000000000000000000000011 
=>        11000000000000000000000000000000
return 3221225472


#Solution
```java
public class Solution {
	public long reverse(long n) {
	long result =0;
	for(int i=0;i<32;i++){
	    result =result + (n&1);
	    n=n>>1;
	    if(i<31)
	       result=result<<1;
	}
	 return result;   
	}
 	
}



```
