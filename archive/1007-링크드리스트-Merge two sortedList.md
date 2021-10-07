문제링크: https://leetcode.com/problems/merge-two-sorted-lists/
두가지 해결방법이 있다. 하나는 링크드리스트의 자료구조를 이용한 반복문이며, 다른하나는 재귀함수.    
깔끔한건 재귀함수겠지만, 정석은 자료구조를 활용한 반복문이라 생각한다.

1)링크드리스트 자료구조를 이용한 반복문. 
```java

public ListNode mergeTwoLists(ListNode l1, ListNode l2) {
    ListNode preHead = new ListNode(0);
    ListNode last = preHead;
    
    while(l1 != null && l2 != null) {
        if(l1.val > l2.val) {
            last.next = l2;
            l2 = l2.next;
        } else {
            last.next = l1;
            l1 = l1.next;
        }
        last = last.next;
    }
    
    if(l1 == null) {
        last.next = l2;
    } else {
        last.next = l1;
    }
    
    return preHead.next;
}

```



2)재귀함수이용
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
        if(l1 == null) return l2;
		if(l2 == null) return l1;
		if(l1.val < l2.val){
			l1.next = mergeTwoLists(l1.next, l2);
			return l1;
		} else{
			l2.next = mergeTwoLists(l1, l2.next);
			return l2;
		}
    }
}

```
