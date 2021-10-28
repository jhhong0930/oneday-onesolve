# 문자열 압축

## 설명

알파벳 대문자로 이루어진 문자열을 입력받아 같은 문자가 연속으로 반복되는 경우 반복되는

문자 바로 오른쪽에 반복 횟수를 표기하는 방법으로 문자열을 압축하는 프로그램을 작성하시오.

단 반복횟수가 1인 경우 생략합니다.


## 입력
첫 줄에 문자열이 주어진다. 문자열의 길이는 100을 넘지 않는다.


## 출력
첫 줄에 압축된 문자열을 출력한다.


## 예시 입력 1 

KKHSSSSSSSE

## 예시 출력 1

K2HS7E

## 예시 입력 2 

KSTTTSEEKFKKKDJJGG

## 예시 출력 2

KST3SE2KFK3DJ2G2

---

## 나의 풀이

```java
package study;

import java.util.Scanner;

public class CompressString1028 {

    public static String solution(String s) {
        int start = 0;
        int end = 1;

        s += " ";   //OutOfIndex 에러 방지를 위함
        StringBuilder sb = new StringBuilder();

        while(end < s.length()) {
            if(s.charAt(start) == s.charAt(end)) {
                end++;
            } else {
                if(end - start > 1) {
                    sb.append(s.charAt(start));
                    sb.append(end-start);   //= 중복되는 알파벳 개수
                    start = end;
                    end = start+1;
                    continue;
                }
                sb.append(s.charAt(start));
                start++;
                end++;
            }
        }

        return sb.toString();
    }

    public static void main(String[] args) {
        Scanner in=new Scanner(System.in);
        String input = in.nextLine();
        System.out.println(solution(input));
    }
}

```
