```java
class Solution {
    public int reverse(int x) {
        long input = x;
        if(input == 0) {
            return 0;
        }
        long divide = 0;
        long remainder = 0;
        long result = 0;
        
        while(input != 0) {
            divide = input / 10;
            remainder = input % 10;
            input = divide;
            result = (result * 10) + remainder;
        }
        
        if (!(-Integer.MAX_VALUE <= result && result <= Integer.MAX_VALUE)) {
            return 0;
        }

        return (int)result;
    }
}
```