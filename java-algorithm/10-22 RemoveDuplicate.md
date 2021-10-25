# 설명

소문자로 된 한개의 문자열이 입력되면 중복된 문자를 제거하고 출력하는 프로그램을 작성하세요.

## 예시 입력 1 
ksekkset

## 예시 출력 1
kset

---

```java
package study;

public class RemoveDuplicate {
    public static String solution(String input) {
        String answer = "";
        for(int i=0; i<input.length(); i++) {
            //charAt(i): i번째 문자 리턴
            //indexOf(char): 문자가 있는 위치 리턴
            //i번째 문자    문자열에서 현재 위치      i번째에 있는 문자가 문자열에서 첫번째로 나오는 위치
            //System.out.println(input.charAt(i)+ " " + i + " " + input.indexOf(input.charAt(i)));

            
            //i번째에 있는 문자의 위치(: i)와
            //문자열에서 첫 번째로 나온 위치가 같으면
            //중복된 문자가 문자열에 없는 것이므로 answer에 현재 문자추가
            if(input.indexOf(input.charAt(i)) == i) answer += input.charAt(i);
        }
        return answer;
    }

    public static void main(String[] args) {
        String input = "ksekkset";
        System.out.println(solution(input));
    }
}

```
