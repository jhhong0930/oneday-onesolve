![image](https://user-images.githubusercontent.com/44156173/138338280-8da03294-c211-407d-93bb-cd43f6cfe57d.png)   
   
   
   ```java
   package study;

import java.util.Scanner;

public class WordInTheSentence {

    public static String solution(String input) {
        String[] split_array = input.split(" ");

        int max_length_index = 0;
        int max_length = 0;
        for(int i=0; i<split_array.length; i++) {
            int str_length = split_array[i].length();
            if(max_length < str_length) {
                max_length = str_length;
                max_length_index = i;
            }
        }

        return split_array[max_length_index];
    }

    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        String input = in.nextLine();

        System.out.println(solution(input));

    }

}

   ```
