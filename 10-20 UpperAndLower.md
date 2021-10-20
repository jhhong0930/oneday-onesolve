대문자는 소문자로, 소문자는 대문자로 변경하기

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Main fs = new Main();
        Scanner in=new Scanner(System.in);
        String input1 = in.next();

        System.out.println(fs.solution(input1));
    }
    private String solution(String inputStr) {
        String answer ="";

        for( char x : inputStr.toCharArray() ) {
            if(x>=97 && x<=122){
                answer += (x-32);
            }
            else
                answer += (x+32);
        }

        return answer;
    }
}
