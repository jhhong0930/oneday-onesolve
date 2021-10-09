문제:&nbsp;https://leetcode.com/problems/remove-element/<br>
foreach문을 좀 더 활용하면 좋을 것 같다<br>
<br>

```java
class Solution {
    public int removeElement(int[] nums, int val) {
        //nums에서 바꿔줘야 하는 값의 위치
        int have_to_change_val_index = 0;
        //값을 하나씩 가져옴
        for(int num: nums) {
            //만약 nums에서 가져온 값과 val 값이 다르면
            if(num != val) {
                //have_to_change_val_index가 현재 바꿔줘야하는 값의 위치에 있는데
                //그 위치에 있는 값을 num으로 바꿈
                nums[have_to_change_val_index] = num;
                //위치를 한 칸 옮김
                have_to_change_val_index++;
            }
            //만약 nums에서 가져온 값과 val 값이 같다면
            //통과시켜줌
        }
        return have_to_change_val_index;
    }
} 
```
