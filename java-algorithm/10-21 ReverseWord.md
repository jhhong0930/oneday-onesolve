![image (1)](https://user-images.githubusercontent.com/44156173/138339308-7912a3d5-bc9e-4e3f-9e49-f11a2519b310.png)

```java
package study;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class ReverseWord {

    public static void solution(String[] input) {
        int index = 0;      //input 배열의 현재 index

        for(String str: input) {
            //문자열을 문자 배열로 변환
            char[] str_char = str.toCharArray();
            int start = 0, end = str_char.length-1;

            //앞에서 n번째와 뒤에서 n번째 문자끼리 위치 바꾸기
            while(start < end) {
                char temp = str_char[end];
                str_char[end] = str_char[start];
                str_char[start] = temp;

                start++;
                end--;
            }
            
            //문자 배열의 원소를 모두 합쳐 문자열로 만들기
            //[q,w,e,r] -> "qwer"
            input[index] = String.valueOf(str_char);
            index++;
        }

        for(String a : input) {
            System.out.println(a);
        }

    }

    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        int count = Integer.parseInt(br.readLine());

        String[] input = new String[count];

        for(int i=0; i<count; i++) {
            input[i] = br.readLine();
        }

        solution(input);

    }

}

```
