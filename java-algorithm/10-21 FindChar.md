문제:   
문자열과 문자를 입력한 뒤, 문자열에서 문자가 포함되어있는 개수 구하기   
   
```java
public class FindChar {
    public static void main(String[] args){
        int count = 0;

        Scanner in = new Scanner(System.in);

        String input1 = in.next();
        char c = in.next().charAt(0);

        input1 = input1.toUpperCase();
        c = Character.toUpperCase(c);

        //방법 1: 문자열에서 문자 하나 가져와 비교
        for(int i=0; i<input1.length(); i++) {
            if(input1.charAt(i) == c) {
                count++;
            }
        }



//         //방법 2: 문자열을 문자 배열로 만들어 하나씩 가져와 비교
//         for(char x: input1.toCharArray()) {
//             if(x == c) count++;
//         }

        System.out.println(count);

    }
}
```
