문제링크: https://leetcode.com/problems/roman-to-integer/

내 답안:  faster than 99.83%    

특별한 스킬보다는 문제지시대로 구현하는 게 중요했음.

```java
class Solution {
    public int romanToInt(String s) {
        char[] char_arr = s.toCharArray();
        int sum = 0;
        for(int i =0; i<char_arr.length; i++){
            boolean isNotOutOfBound = (i < char_arr.length-1);

            if(char_arr[i] == 'I'){
                if(isNotOutOfBound&&(char_arr[i+1] == 'V' || char_arr[i+1] == 'X')) sum-=1;
                else sum+=1;
            }
            if(char_arr[i] == 'V') sum+=5;
            if(char_arr[i] == 'X') {
                if(isNotOutOfBound && (char_arr[i+1] == 'L' || char_arr[i+1] == 'C')) sum-=10;
                else sum+=10;
            }
            if(char_arr[i] == 'L') sum+=50;
            if(char_arr[i] == 'C') {
                if(isNotOutOfBound && (char_arr[i+1] == 'D' || char_arr[i+1] == 'M')) sum-=100;
                else sum+=100;
            }
            if(char_arr[i] == 'D') sum+=500;
            if(char_arr[i] == 'M') sum+=1000;
//            System.out.println(char_arr[i]+":"+ sum);
        }
        return sum;
    }
}

```

