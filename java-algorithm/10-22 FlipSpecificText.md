# 설명

영어 알파벳과 특수문자로 구성된 문자열이 주어지면 영어 알파벳만 뒤집고, 특수문자는 자기 자리에 그대로 있는 문자열을 만들어 출력하는 프로그램을 작성하세요.

## 예시 입력 1 
a#b!GE*T@S

## 예시 출력 1
S#T!EG*b@a<br>

---

```java
package study;

public class FlipSpecificText {
    public static String solution(String input) {
        int start = 0, end = input.length() - 1;
        String answer = "";

        char[] in = input.toCharArray();

        while(start < end) {
            //특수문자인지 아닌지
            if(!Character.isAlphabetic(in[start]) && !Character.isAlphabetic(in[end])) {
                start++;
                end--;
            } else {
                char temp = in[start];
                in[start] = in[end];
                in[end] = temp;
                start++;
                end--;
            }
        }
        answer = String.valueOf(in);
        return answer;
    }

    public static void main(String[] args) {
        String input = "a#b!GE*T@S";
        System.out.println(solution(input));
    }

}

```
