문제 : https://leetcode.com/problems/maximum-subarray/  
문제를 처음 봤을 땐 이해를 못해서 검색해보았다.  
그림을 직접 그려서 설명을 해준 글이 있어서 
그림과 똑같이 구현해내려고 했다.  
하지만 뜻대로 되지 않았다.  
참고 글 : https://the-dev.tistory.com/57
```java
class Solution {
    public int maxSubArray(int[] nums) {
        if(nums.length == 1) return nums[0];
        if(nums.length == 0) return 0;

        int currentSubArray = nums[0];
        int maxSum = nums[0];

        for(int i=1; i<nums.length; i++) {
            if(nums[i] >= currentSubArray + nums[i]) {
                currentSubArray = nums[i];
            } else {
                currentSubArray += nums[i];
            }

            if(maxSum < currentSubArray) {
                maxSum = currentSubArray;
            }
        }
        return maxSum;
    }
}
```  
<br>
블로그 글에서 풀어낸 코드는 아래와 같다.  

```java
class Solution {
    
    public int maxSubArray(int[] nums) { 
        int currentSubarray = nums[0]; 
        int maxSubarray = nums[0]; 
        for(int i = 1; i < nums.length; i++){ 
            currentSubarray = Math.max(nums[i], currentSubarray + nums[i]); 
            maxSubarray = Math.max(currentSubarray, maxSubarray); 
        } 
        return maxSubarray; 
    }
}
```
