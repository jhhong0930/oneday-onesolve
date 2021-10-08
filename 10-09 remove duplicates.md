```
package com.saname.amen.security;

public class z {
    public int removeDuplicates(int[] nums) {
        int i  = 0;
        int lenCount = 0;
        int inum=-1; //여기도 생각
        for (int num : nums) { // 지성인처럼 여기 수정말고 교체..?
            if (inum<num){ //여기도..?
                nums[i]=num;
                i++;
                lenCount++;
            }
        }
        return lenCount;
    }
}
```

