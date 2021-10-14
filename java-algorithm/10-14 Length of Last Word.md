문제: https://leetcode.com/problems/length-of-last-word/  
<br>

```java
class Solution {
    public int lengthOfLastWord(String s) {
        String s_trim = s.trim();
        String[] s_split = s_trim.split(" ");
        int s_split_last_index = s_split.length-1;
        return s_split[s_split_last_index].length();
    }
}
```
<br>
<br>
반복문을 거꾸로 돌려 공백을 만나면 개수를 반환하는 코드도 있었다.
  
  
```java
class Solution {
    public int lengthOfLastWord(String s) {
        s=s.trim();
        int x=s.length()-1,i;
        for(i=x;i>=0;i--)
        {
            if(s.charAt(i)==' ')
                break;
        }
        return x-i;
    }
}
```
