# 설명

앞에서 읽을 때나 뒤에서 읽을 때나 같은 문자열을 회문 문자열이라고 합니다.

문자열이 입력되면 해당 문자열이 회문 문자열이면 "YES", 회문 문자열이 아니면 “NO"를 출력하는 프로그램을 작성하세요.

단 회문을 검사할 때 대소문자를 구분하지 않습니다.


## 입력
첫 줄에 길이 100을 넘지 않는 공백이 없는 문자열이 주어집니다.


## 출력
첫 번째 줄에 회문 문자열인지의 결과를 YES 또는 NO로 출력합니다.


## 예시 입력 1 
gooG

## 예시 출력 1

YES

---

### 나의 풀이

```java
package study;

import java.util.Scanner;

public class Palindrome1026 {

    public static String solution(String input) {

        int start = 0;
        int end = input.length() - 1;

        String input_lower = input.toLowerCase();

        char[] input_char = input_lower.toCharArray();

        while(start < end) {
            if(input_char[start] == input_char[end]) {
                start++;
                end--;
            } else {
                return "NO";
            }
        }

        return "YES";
    }

    public static void main(String[] args){
//        String input = "goABoG";
//        System.out.println(solution(input));


        Scanner in=new Scanner(System.in);
        String input = in.nextLine();
        System.out.println(solution(input));
    }
}

```

<br><br>

## 강의 풀이1
   내 머리에선 생각할 수도 없었던 풀이였다.   
   회문이기 때문에 반만 돌면서 비교하면 된다.   

```java
    public String solution(String str) {
        String answer = "YES";

        str = str.toUpperCase();

        int len = str.length();
        for(int i=0; i<len/2; i++) {
            if(str.charAt(i) != str.charAt(len-1-i)) answer = "NO";
        }

        return answer;
    }
```

<br>

## 강의 풀이2
이것도 내 머리에선 나올 수 없는 풀이였다..   
원래 문자열과 뒤집은 문자열 비교   
equalsIgnoreCase : 대소문자 구분안함   

```java
    public String solution(String str) {
        String answer = "NO";

        String tmp = new StringBuilder(str).reverse().toString();

        if(str.equalsIgnoreCase(tmp)) answer = "YES";

        return answer;
    }
```
