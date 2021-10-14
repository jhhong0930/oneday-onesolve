알고리즘

```java

private static int lenghtOfLastWord(String s) {

        s = s.trim(); //양쪽 빈값 자르기
        int len = s.length();

        if(len==0)
            return 0;

        int idx = s.lastIndexOf(' ');
        if(idx<0) // 빈값 없을 경우
            return s.length();
        return s.substring(idx, len-1).length();
 }
