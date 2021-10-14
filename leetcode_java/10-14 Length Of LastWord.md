알고리즘

```java

private static int lenghtOfLastWord(String s) {

        s = s.trim();
        int len = s.length();

        if(len==0)
            return 0;

        int idx = s.lastIndexOf(' ');
        if(idx<0)
            return s.length();
        return s.substring(idx, len-1).length();
 }
