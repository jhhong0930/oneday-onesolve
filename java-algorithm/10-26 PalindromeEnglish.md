# 유효한 팰린드롬

## 설명

앞에서 읽을 때나 뒤에서 읽을 때나 같은 문자열을 팰린드롬이라고 합니다.

문자열이 입력되면 해당 문자열이 팰린드롬이면 "YES", 아니면 “NO"를 출력하는 프로그램을 작성하세요.

단 회문을 검사할 때 알파벳만 가지고 회문을 검사하며, 대소문자를 구분하지 않습니다.

알파벳 이외의 문자들의 무시합니다.


### 입력
첫 줄에 길이 100을 넘지 않는 공백이 없는 문자열이 주어집니다.


### 출력
첫 번째 줄에 팰린드롬인지의 결과를 YES 또는 NO로 출력합니다.


### 예시 입력 1 

found7, time: study; Yduts; emit, 7Dnuof

### 예시 출력 1

YES

---

### 나의 풀이   
문제가 이해되지 않았었다. 알파벳 이외의 문자들은 무시를 하라는 말이 건너뛰라는건지 뭔지 이해가 안 되었다.   
결국 강의를 봤는데, 강의에서는 알파벳 이외의 문자들은 제외시켜서 풀었다.   
강의에서 알려준 방법을 썼다.
정규식, 알고 있었지만 문제에서 쓸 생각은 해보지 않았었다.

```java
package study;

import java.util.Scanner;

public class PalindromeEnglish1026 {

    public static String solution(String input) {

        String input_lower = input.toLowerCase();

        String input_replace = input_lower.toUpperCase().replaceAll("[^A-Z]", "");

        int start = 0;
        int end = input_replace.length() - 1;

        char[] input_char = input_replace.toCharArray();

        while(start < end) {

            if((input_char[start] == input_char[end])) {
                start++;
                end--;
            } else {
                return "NO";
            }
        }

        return "YES";
    }

    public static void main(String[] args){
        String input = "found7, timk: study; Yduts; emit, 7Dnuof";
        System.out.println(solution(input));

        //found7, timk: study; Yduts; emit, 7Dnuof   :   NO
        //Tae,aba;e#%a*T : NO
        //a sd fg #%hjkl; %#$@! lkj&*hgfd s ##a  :  YES
//        Scanner in=new Scanner(System.in);
//        String input = in.nextLine();
//        System.out.println(solution(input));
    }
}

```
<br><br>

### 강의 풀이
```java
    public String solution(String input) {
        String answer = "NO";
        input = input.toUpperCase().replaceAll("[^A-Z]", "");
        String tmp = new StringBuilder(input).reverse().toString();
        if(input.equals(tmp)) answer = "YES";

        return answer;
    }
```
