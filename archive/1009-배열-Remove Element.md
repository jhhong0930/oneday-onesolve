문제링크: https://leetcode.com/problems/remove-element/

내 답안: faster than 100% 오졋다리


```java

class Solution {
    public int removeElement(int[] A, int elem) {
        int m = 0;
        for(int i = 0; i < A.length; i++){   
            if(A[i] != elem){
                A[m++] = A[i];
            }
        }
        return m;
    }
}

```
