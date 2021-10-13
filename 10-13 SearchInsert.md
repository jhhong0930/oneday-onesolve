``` java
// 쉬운 문제지만 인간승리..

public class SearchInsert { 
    public int searchInsert(int[] nums, int target) {

        int numsLen = nums.length;

        for (int i = 0; i < numsLen; i++){
            if (target == nums[i]){
                return i;
            }else if(target < nums[i]){
                return i;
            }
        }
        return numsLen;
    }
}
```















![](https://images.velog.io/images/9sanha/post/52550eec-cb29-4741-831e-78edc119e559/image.png)

