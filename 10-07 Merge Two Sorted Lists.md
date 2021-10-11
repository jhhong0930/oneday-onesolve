```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode mergeTwoLists(ListNode l1, ListNode l2) {
    	if (l1 == null) return l2;
	    if (l2 == null) return l1;
        if (l1.val < l2.val) {
   	     	l1.next = mergeTwoLists(l1.next, l2);
	        return l1;
	    } else {
	        l2.next = mergeTwoLists(l1, l2.next);
	        return l2;
        }
    }
}
```

![](https://images.velog.io/images/9sanha/post/03ca5408-a57f-492f-9f75-681b4e7078d7/%E1%84%8B%E1%85%B5%E1%84%85%E1%85%B3%E1%86%B7%20%E1%84%8B%E1%85%A5%E1%86%B9%E1%84%82%E1%85%B3%E1%86%AB%20%E1%84%82%E1%85%A9%E1%84%90%E1%85%B3%E1%84%87%E1%85%AE%E1%86%A8-4.jpg)

