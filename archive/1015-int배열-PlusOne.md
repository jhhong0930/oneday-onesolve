
https://leetcode.com/problems/plus-one/submissions/

내답안:      
```java

 public int[] plusOne(int[] digits) {
        if(digits.length ==1 && digits[0] ==9) return new int[]{1,0};
        for(int i = digits.length-1; i>=0; i--){
            if(digits[i] ==9){
                digits[i] = 0;
            }else{
                digits[i]++;
                return digits;
            }
        }
        if(digits[0] ==0 && digits[1]==0){
            int[] answer = new int[digits.length+1];
            answer[0] = 1;
            return answer;
        }
        return digits;
    }


```


모범답안:       

```java

public int[] plusOne(int[] digits) {
        
    int n = digits.length;
    for(int i=n-1; i>=0; i--) {
        if(digits[i] < 9) {
            digits[i]++;
            return digits;
        }
        
        digits[i] = 0;
    }
    
    int[] newNumber = new int [n+1];
    newNumber[0] = 1;
    
    return newNumber;
}

````
