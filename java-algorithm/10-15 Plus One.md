문제: https://leetcode.com/problems/plus-one/submissions/<br>
드디어 됐다...0ms 나왔다...
<br>
```java
class Solution {
    public int[] plusOne(int[] digits) {
        int digits_length = digits.length;
        if(digits[digits_length-1] == 9) {
            for(int i=digits_length-1; i>=0; i--) {
                if(digits[i] == 9) {
                    digits[i] = 0;
                } else {
                    digits[i] = digits[i] + 1;
                    break;
                }
            }
        }else {
            digits[digits_length-1] = digits[digits_length-1] + 1;
        }
        
        if(digits[0] == 0) {
            int[] int_arr = new int[digits_length+1];
            int_arr[0] = 1;
            return int_arr;
        }
        
        return digits;
    }
}
```
