문제: https://leetcode.com/problems/search-insert-position/  
O(log N)이라길래 계속 2로 나누는 것을 생각했지만  
어디가 문제인지 모르겠다...ㅠㅠ

```java
class Solution {
    public int searchInsert(int[] nums, int target) {
        int start = 0;
        int end = nums.length;
        int half =(int) Math.floor((start + end) / 2); //버림
        
        //nums의 마지막 값이 target보다 크면 마지막 값 다음에 위치해야함
        if(nums[end-1] < target) return end;
        if(nums[start] >= target) return 0;
            
        ArrayList<Integer> arrayList = new ArrayList<>();

        for(int num : nums){
          arrayList.add(num);
        }

        System.out.println("half:" + half);
        
        while(half != 0 && start != half && end!= half) {
            System.out.println("nums[half]: " + nums[half] + ", target: " + target);
            if(nums[half] > target) {
                System.out.println("if(nums[half] > target)");
                end = half;
                System.out.println("start:" + start + ", half:" + half + ", end: " + end);
            } else if(nums[half] == target) {
                System.out.println("else if(nums[half] == target)");
                System.out.println("start:" + start + ", half:" + half + ", end: " + end);
                return arrayList.indexOf(target);
            }else if(nums[half] < target){
                System.out.println("else");
                start = half;
                System.out.println("start:" + start + ", half:" + half + ", end: " + end);
            } 
            half =(int) Math.floor(start + end / 2);
            System.out.println("half: " + half);
        }
        
        return half;
    }
}
```
<br>
이건 O(log N)을 고려한 것인지는 모르겠지만(생각 안한거 같기도..)  
간단하다

```java
class Solution {
    public int searchInsert(int[] nums, int target) {
        int len = nums.length;
        int i;
        for(i = 0; i < len; i++) {
            if(nums[i] >= target)
            return i;
        }
        return i;
    }
}
```