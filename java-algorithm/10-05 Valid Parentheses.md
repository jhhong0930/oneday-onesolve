문제: https://leetcode.com/problems/valid-parentheses/
<br>
<br>
```java
class Solution {
    public boolean isValid(String s) {
        Stack<Character> stack = new Stack<>();
        
        if(s.length() == 0) return false; 

        for(int i=0; i<s.length(); i++) {
            char bracket_char = s.charAt(i);
            if(bracket_char == '(' || bracket_char == '{' || bracket_char == '[') {
                stack.push(bracket_char);
            } else if(bracket_char == ')' || bracket_char == '}' || bracket_char == ']') {
                if(stack.size() == 0) {
                    return false;
                } else {
                    if(stack.peek() == '(' && bracket_char == ')') stack.pop();
                    else if(stack.peek() == '{' && bracket_char == '}') stack.pop();
                    else if(stack.peek() == '[' && bracket_char == ']') stack.pop();
                    else {   // "({)" 처럼 여는괄호 닫는괄호 이어져있지만 짝이 안 맞을 경우
                        return false;
                    }
                }
            }
        }

        //위 과정을 다 거쳤는데도 스택에 남아있다면 짝을 못찾은 것
        if(stack.size() != 0) {
            return false;
        } else {
        //모두 짝을 찾은 것
            return true;
        }
    } 
}
```