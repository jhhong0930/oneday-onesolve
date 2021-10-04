문제: https://leetcode.com/problems/longest-common-prefix/

제대로 동작하지 않음 수정해야함
<br>
<br>

```java
class Solution {
    public String longestCommonPrefix(String[] strs) {
        if(strs.length == 0 || strs.length == 1) return "";
        
        //가장 짧은 문자열 길이 가져오기
        int shortest_str_length = strs[0].length();
        for(String str: strs) {
            int str_length = str.length();
            if(str_length < shortest_str_length)
            shortest_str_length = str_length;
        }
        
        String compare = strs[0];
        boolean is_same = true;
        int index = 0;
        for(String str: strs) {
            System.out.println("compare: " + compare + ", str: " + str);
            index = 0;
            if(compare.equals(str)) continue;
            while(index < shortest_str_length) {
                System.out.println("index: " + index);
                char char1 = compare.charAt(index);
                char char2 = str.charAt(index);
                System.out.println("char1: " + char1 + ", char2: " + char2);
                if(char1 == char2) {
                    System.out.println("if(char1 == char2)");
                    index++;
                    continue;
                } else {
                    System.out.println("else");
                    //첫번째문자열 두번째문자열 비교 시 공통인 문자열이 없을 때
                    //(첫번째 두번째에 공통인 부분이 없었으면 모든 문자열에서 공통인 부분이 없다는 뜻)
                    if(index == 0) return "";
                    
                    compare = compare.substring(0, index);
                    System.out.println("compare: " + compare);
                }
            }
        }
        return compare;
    } 
}
```