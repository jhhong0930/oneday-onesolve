
문제링크: https://leetcode.com/problems/longest-common-prefix/

내 풀이: faster than 30~60% 제출할때마다 달라지면 이게 의미가 있나?ㅋㅋ

```java

public class Solution {
    public String solution(String[] strs) { //["flower","flow","flight"]
        String prefix = strs[0];
        for(String str: strs){
            int shorterLen = Math.min(prefix.length(), str.length());
            StringBuilder tmp = new StringBuilder();

            for(int i=0; i<shorterLen; i++){
                if(prefix.charAt(i) == str.charAt(i)) tmp.append(prefix.charAt(i));
                else break;
            }

            prefix = tmp.toString();
        }
        return prefix;
    }

    public static void main(String[] args) {
        Solution T = new Solution();
        String[] strs = {"flower","flow","flight"};
        System.out.println(T.solution(strs));
    }
}

```



-------------
참고답안:
```java
    public String longestCommonPrefix(String[] strs) {
        if (strs == null || strs.length == 0)
            return "";
        
        Arrays.sort(strs);
        String first = strs[0];
        String last = strs[strs.length - 1];
        int c = 0;
        while(c < first.length())
        {
            if (first.charAt(c) == last.charAt(c))
                c++;
            else
                break;
        }
        return c == 0 ? "" : first.substring(0, c);
    }
}

```
