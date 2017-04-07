# Reverse a string using stack

```
java

public class Solution {
	public String reverseString(String a) {
	    Stack<String> A = new Stack<String>();
	    for(int i=0;i<a.length();i++){
	       String temp = Character.toString(a.charAt(i) );
	       A.push(temp);
	    }
	    String result = "";
	    while(!A.empty()){
	        result = result + A.pop();
	    }
	    return result;
	}
}



```
