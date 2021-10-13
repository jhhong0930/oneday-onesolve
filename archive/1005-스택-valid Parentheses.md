
문제링크: https://leetcode.com/problems/valid-parentheses/


```java
public boolean solution(String s) {
        Stack<Character> charStack = new Stack<>();
        char[] chars = s.toCharArray();
        int i=0;
        for(char c : chars){
            //여는 애들이 나오면 일단 넣어준다
           if(c =='(' || c=='[' || c=='{'){
               charStack.push(c);
           }else{
               //스택이 빈경우
               if(charStack.isEmpty()) return false;

               //같은 종류가 아닌애가 닫으면 그건 틀린 것임
               if(c == ')' && charStack.peek()=='(') charStack.pop();
               else if(c == '}' && charStack.peek()=='{') charStack.pop();
               else if(c == ']' && charStack.peek()=='[') charStack.pop();
               else {
                   return false;
               }
           }
        }
        //최종적으로 스택이 깨끗이 비었다면 성공
        return charStack.size() == 0;
    }

```
