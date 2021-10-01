```java
class Solution {
    public boolean isPalindrome(int x) {
        String x_str = Integer.toString(x);
        String x_str_reverse = "";
        int str_len = x_str.length();
        for(int i=0; i<str_len; i++) {
            x_str_reverse += x_str.charAt((str_len-1) - i);
        }
        if(x_str.equals(x_str_reverse)) {
            return true;
        }
        return false;
    }
}
```