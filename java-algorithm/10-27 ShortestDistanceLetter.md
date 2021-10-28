# 가장 짧은 문자거리

## 설명

한 개의 문자열 s와 문자 t가 주어지면 문자열 s의 각 문자가 문자 t와 떨어진 최소거리를 출력하는 프로그램을 작성하세요.


## 입력
첫 번째 줄에 문자열 s와 문자 t가 주어진다. 문자열과 문자는 소문자로만 주어집니다.

문자열의 길이는 100을 넘지 않는다.


## 출력
첫 번째 줄에 각 문자열 s의 각 문자가 문자 t와 떨어진 거리를 순서대로 출력한다.


## 예시 입력 1 

teachermode e

## 예시 출력 1

1 0 1 2 1 0 1 2 2 1 0

---

## 강의 풀이

왼쪽 -> 오른쪽 으로 반복문 돌면서 거리 구하고,

오른쪽 -> 왼쪽 으로 반복문 돌면서 거리 구하는데

왼쪽 -> 오른쪽에서 구한 각각의 거리와 오른쪽 -> 왼쪽에서 구한 각각의 거리를 비교해서 

작은 값으로 정한다


```java
package study;

import java.util.Scanner;

public class ShortestDistanceLetter1027 {
    public static void solution(String input, char t) {
        int input_len = input.length();
        int[] distance = new int[input_len];

        int max_distance = 1000;
        for(int i=0; i<input_len; i++) {
            if(input.charAt(i) == t) max_distance = 0;
            else max_distance++;
            distance[i] = max_distance;
        }

        max_distance = 1000;
        for(int i=input_len-1; i>=0; i--) {
            if(input.charAt(i) == t) max_distance = 0;
            else max_distance++;
            distance[i] = Math.min(distance[i], max_distance);
        }

        for(int d : distance) {
            System.out.print(d + " ");
        }
    }

    public static void main(String[] args) {
        Scanner in=new Scanner(System.in);
        String s = in.next();
        char t = in.next().charAt(0);
        solution(s, t);
    }

}

```
