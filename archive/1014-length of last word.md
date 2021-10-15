

문제링크: https://leetcode.com/problems/length-of-last-word/

```java

    public int solution(String s) {
        int answer;
        String[] words = s.split(" ");
        String lastWord = words[words.length-1];
        answer = lastWord.length();
        return answer;
    }


```
