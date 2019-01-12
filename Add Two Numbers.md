## Add Two Numbers

You are given two **non-empty** linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

**Input:** (2 -> 4 -> 3) + (5 -> 6 -> 4)
**Output:** 7 -> 0 -> 8

~~~
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode pre=new ListNode(0);
        ListNode head=pre;
        int sum=0;
        while(l1!=null||l2!=null){
            sum=((l1==null)?0:l1.val)+((l2==null)?0:l2.val)+sum/10;
            pre.next=new ListNode(sum%10);
            pre=pre.next;
            if(l1!=null)l1=l1.next;
            if(l2!=null)l2=l2.next;
        }
        if(sum/10==1){
        pre.next=new ListNode(1);
        }
        return head.next;
    }
}
~~~

