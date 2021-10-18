문제: https://leetcode.com/problems/sqrtx/submissions/   
input을 2로 나누었을 때 몫을 가져온 다음   
1부터 몫까지 매번 제곱을 하면서 input과 비교를 하는걸로 했지만
큰 수에서 걸린다...
   
https://bcp0109.tistory.com/275 여기를 참고해서 다시 공부해야할 것 같다.
   
   

```java
class Solution {
    public int mySqrt(int x) {
        if(x == 0) return 0;

        int result = 0;

        long maxOutput = x / 2 ; // 8/2 = 3

        for(int i=0; i<=maxOutput; i++) {
            int squared = i * i;
            if(squared > x) {
                result = i-1;
                break;
            }
            result = i;
        }


        return result;
        //NOT ALLOWED...어쩐지...
        //return (int)(Math.floor(Math.pow(x, 0.5)));
    }
}
```
   
