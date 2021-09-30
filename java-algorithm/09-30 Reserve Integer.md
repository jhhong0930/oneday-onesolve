```
class Solution {
    public int reverse(int x) {
        System.out.println("x: " + x);
        int divide = 0;
        int remainder = 0;
        int result = 0;
        int x_abs = Math.abs(x);
        String x_str = Integer.toString(x_abs);
        if(!(result >= Integer.MIN_VALUE && result <= Integer.MAX_VALUE)) {
            result = 0;
        }
        for(int i=0; i<x_str.length(); i++) {
            divide = x_abs / 10;
            System.out.println("divide: " + divide);
            remainder = x_abs % 10;
            System.out.println("remainder: " + remainder);
            x_abs = divide;
            System.out.println("x_abs: " + x_abs);
            result = (result * 10) + remainder;
            System.out.println("result: " + result);
        }
        if(x < 0) {
            result = -result;
        }
        return result;
    }
}
```