# Min Stack

Design a stack that supports push, pop, top, and retrieving the minimum element in constant time.

push(x) – Push element x onto stack.
pop() – Removes the element on top of the stack.
top() – Get the top element.
getMin() – Retrieve the minimum element in the stack.
Note that all the operations have to be constant time operations.

Questions to ask the interviewer :

Q: What should getMin() do on empty stack? 
A: In this case, return -1.

Q: What should pop do on empty stack? 
A: In this case, nothing. 

Q: What should top() do on empty stack?
A: In this case, return -1



## Solution

```java
class Solution {
    Stack<Integer> A = new Stack<Integer>();
     int min=-1;
    public void push(int x) {
       if(A.empty()||min>=x){
           A.push(min);
           min =x;
       }
       A.push(x);
    }

    public void pop() {
        if(!A.empty() && min == A.pop()){
            min = A.pop();
        }
    }

    public int top() {
        if(A.empty()){
            return -1;
        }
        else{
        return A.peek();    
        }
        
    }

    public int getMin() {
        if(A.empty()){
            return -1;
        }
        else{
            return min;
        }
    }
}




```
