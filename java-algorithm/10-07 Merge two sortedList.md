문제:&nbsp;https://leetcode.com/problems/merge-two-sorted-lists/<br>
<br>
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
        //head노드를 새로 생성
        ListNode head_node = new ListNode(0);
        //가장 마지막 노드를 저장(이것이 이동할 예정)
        ListNode last_node = head_node;
        
        
        //l1과 12의 가장 마지막 노드로 이동할 때까지 반복
        while(l1 != null && l2 != null) {
            //만약 현재 l1 노드의 값이 현재 l2의 노드의 값보다 작을 때
            if(l1.val < l2.val) {
                //가장 마지막 노드의 다음을 l1 노드로 설정
                last_node.next = l1;
                //l1의 다음 노드로 이동
                l1 = l1.next;
            } else { //만약 현재 l1 노드의 값이 현재 l2의 노드 값보다 클 때
                //가장 마지막 노드의 다음을 l2 노드로 설정
                last_node.next = l2;
                //l2의 다음 노드로 이동
                l2 = l2.next;
            }
            //last_node의 다음 노드로 이동
            last_node = last_node.next;
        }
        
        //만약 l1 노드가 아예 없을 경우 head 노드의 다음을 l2로 설정 
        if(l1 == null) last_node.next = l2;
        //만약 l2 노드가 아예 없을 경우 head 노드의 다음을 l1으로 설정 
        else last_node.next = l1;
        
        return head_node.next; //맨 앞에 0이 있어서
    }
}
```
