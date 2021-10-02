```java
class Solution {
    public int romanToInt(String s) {
        String roman = "IVXLCDM";
        int[] integer_arr = {1,5,10,50,100,500,1000};
        int start = 0;
        int end = 1;
        int result = 0;
        while(end < s.length()) {
            int integer_current_index = roman.indexOf(s.charAt(start)); //로마 -> 숫자
            int integer_next_index = roman.indexOf(s.charAt(end));
            if(integer_current_index < integer_next_index) {
                result -= integer_arr[integer_current_index];
            } else {
                result += integer_arr[integer_current_index];
            }
            start++;
            end++;
        }
        int s_last_index = roman.indexOf(s.charAt(s.length()-1)); //마지막 로마숫자 계산
        result += integer_arr[s_last_index];
        return result;
    }
}
```