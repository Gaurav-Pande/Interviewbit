# Generate all ParenthesesBookmark Suggest Edit

Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

The brackets must close in the correct order, "()" and "()[]{}" are all valid but "(]" and "([)]" are not.

Return 0 / 1 ( 0 for false, 1 for true ) for this problem


## Solutions

```
java

public class Solution {
	public int isValid(String a) {
	   Stack<String> A = new Stack<String>(); 
	   for(int i=0;i<a.length();i++){
	       if(a.charAt(i)=='{' || a.charAt(i)=='(' || a.charAt(i)=='[' ){
	            A.push(Character.toString(a.charAt(i)));
	       }
	       else if(a.charAt(i)=='}' || a.charAt(i)==')' || a.charAt(i)==']'){
	           if(A.empty()){
	               return 0;
	           }
	           else{
	              A.pop(); 
	           }
	           
	       }
	   }
	   if(A.empty()){
	       return 1;
	   }
	   else{
	       return 0;
	   }
	   
	   
	   
	}
}



``



## One more elegant solution which includes the hashmap is:

```
java

ort java.util.Map;
import java.util.HashMap;
import java.util.Stack;
 
public class Solution {
    
    @SuppressWarnings("serial")
    private Map<Character, Character> map = new HashMap<Character, Character>(){{
       put(')', '(');
       put(']', '[');
       put('}', '{');
    }};
    
    public int isValid(String A) {
        Stack<Character> stack = new Stack<>();
        for (char ch : A.toCharArray()) {
            if (map.containsKey(ch)) {
                // we met with ], }, )
                if (stack.isEmpty() || stack.pop() != map.get(ch)) {
                    // no right counterpart to cancel
                    return 0;
                }
            } else {
                // {, [, (
                stack.push(ch);
            }
        }
        return stack.isEmpty() ? 1 : 0;
    }
    
}




```
