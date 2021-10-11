문제:&nbsp;https://leetcode.com/problems/implement-strstr/<br>
너무 느리다 약 600ms 걸린다
<br>

```java
class Solution {
    public int strStr(String haystack, String needle) {
        if(haystack.length() == 0 && needle.length() == 0) return 0;
        if(needle.length() == 0) return 0;
        if(haystack.length() == 0) return -1;
        
        return haystack.indexOf(needle);    
    }
}
```
