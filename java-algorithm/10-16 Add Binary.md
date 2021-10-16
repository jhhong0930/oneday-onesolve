문제: https://leetcode.com/problems/add-binary/<br>
<br>
문제를 꼼꼼히 읽자..이미 이진수로 주어진 값들인데<br>
십진수에서 이진수로 변환하는 함수를 만들었었다..<br>
내가 이해할 수 있는 코드를 참고해서 짰는데 거의 똑같이 되어버린것 같다<br>
https://leetcode.com/problems/add-binary/discuss/1497329/Java-Simple-Solution-Using-StringBuilder<br>
<br>
StringBuilder를 쓰면 확실히 빨라진다는 것을 느꼈다
<br>
```java
class Solution {
    public String addBinary(String a, String b) {
        int sum_remainder = 0;
        //String binary_sum = "";   //11ms

        StringBuilder binary_sum = new StringBuilder("");   //2ms
        
        int i = 0, x = 0, y = 0, carry = 0;
        while(i< a.length() || i< b.length()) {
            x = 0;
            y = 0;
            if(i< a.length()) {
                //Character.getNumericValue(): 숫자로 된 char를 int로 변경
                x = Character.getNumericValue((a.charAt(a.length() - 1 - i)));
            }
            if(i< b.length()) {
                y = Character.getNumericValue((b.charAt(b.length() - 1 - i)));
            }
            int sum = x + y + carry;
            switch(sum) {
                case 0:
                case 1: {
                    binary_sum.append(sum);
                    carry = 0;
                    break;
                }
                case 2: {
                    binary_sum.append(0);
                    carry = 1;
                    break;
                }
                case 3: {
                    binary_sum.append(1);
                    carry = 1;
                    break;
                }
            }
            i++;
        }
        if(carry > 0) {
            binary_sum.append(1);
        }

        //StringBuilder 미사용 시
        //binary_sum은 거꾸로 되어있어서 뒤집어줘야함
        // String binary = "";
        // for(int j=binary_sum.length()-1; j>=0; j--) {
        //     binary += binary_sum.charAt(j);
        // }
        //return binary;
        
        //StringBuilder 사용 시
        return binary_sum.reverse().toString();
    }

}
```
