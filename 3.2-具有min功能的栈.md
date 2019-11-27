## 双栈思路
```java
import java.util.Stack;

public class Solution {
    Stack<Integer> dataStack = new Stack<>();
    Stack<Integer> minStack = new Stack<>();
    int min = Integer.MAX_VALUE;
    
    public void push(int node) {
        dataStack.push(node);
        if (node <= min) {
            minStack.push(node);
            min = node;
        }
    }
    
    public void pop() {
        int val = dataStack.pop();
        if (val == minStack.peek()) {
            minStack.pop();
        }
    }
    
    public int top() {
        return dataStack.peek();
    }
    
    public int min() {
        return minStack.peek();
    }
}
```

## 单栈思路
```java
import java.util.Stack;

public class Solution {
    Stack<Integer> stack = new Stack<>();
    int min = Integer.MAX_VALUE;
    
    public void push(int node) {
        if (node <= min) {
            stack.push(min);
            min = node;
        }
        stack.push(node);
    }
    
    public void pop() {
        if (stack.pop() == min) {
            min = stack.pop();
        }
    }
    
    public int top() {
        return stack.peek();
    }
    
    public int min() {
        return min;
    }
}
```