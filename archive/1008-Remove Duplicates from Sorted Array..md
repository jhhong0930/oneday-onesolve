
문제링크: https://leetcode.com/problems/remove-duplicates-from-sorted-array/ 

처음시도한 방법: Set이용..무식       
faster than: 6%     
```java
class Solution {
    public int removeDuplicates(int[] nums) {
        Set<Integer> numSet = new HashSet<>();
        for(int num: nums){
            numSet.add(num);
        }
        ArrayList<Integer> arrayList = new ArrayList<>(numSet);
        arrayList.sort(Comparator.naturalOrder());

        for(int i=0; i<arrayList.size(); i++){
            nums[i] = arrayList.get(i);
        }
        return numSet.size();
    }
}

```






더 괜찮은 방법:     
faster than 88%       
```java

class Solution {
    public int removeDuplicates(int[] nums) {
        
        int j=1;
        for(int i=1; i<nums.length; i++){
            if(nums[i]!=nums[i-1]){
                nums[j] = nums[i];
                j++;
            }
        }
        return j;
    }
}

```
