문제:   
문자열 중에서 대문자->소문자 또는 소문자->대문자 로 모두 변환   
   

```java
public class ConvertUpperLower {
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        String input = in.next();

//        //방법 1 : 문자열 하나하나 가져와 대소문자 판단
//        String result = "";
//        for(char c : input.toCharArray()) {
//            if(Character.isLowerCase(c)) result += Character.toUpperCase(c);
//            else result += Character.toLowerCase(c);
//        }

        //방법 2 : ASCII 코드를 이용
        StringBuilder result = new StringBuilder();
        //대문자 ASCII코드: 65 ~ 90,  소문자 ASCII코드: 97 ~ 122
        //대문자와 소문자는 32 차이 남
        //대문자일 경우 +32, 소문자일 경우 -32 한 뒤 char로 형변환해서 append
        for(int c : input.toCharArray()) {
            if(65<=c && c<=90) result.append((char) (c + 32));
            else result.append((char) (c - 32));
        }

        System.out.println(result);
    }
}
```
