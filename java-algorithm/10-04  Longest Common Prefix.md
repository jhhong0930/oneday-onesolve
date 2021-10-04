```java
class Solution {
    public String longestCommonPrefix(String[] strs) {
        String compare = strs[0];
        int index = 0;
        boolean 
        String same_str = "";
        for(String str: strs) {
            System.out.println("compare: " + compare + ", str: " + str);
            char char1 = compare.charAt(index);
            char char2 = str.charAt(index);
            if(char1 == char2) {
                index++;
            } else {
                char1.substr();
            }
        }
        return "";
    }
}
```