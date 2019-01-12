## Remove Duplicates from Sorted List

Given a sorted linked list, delete all duplicates such that each element appear only *once*.

For example,
Given `1->1->2`, return `1->2`.
Given `1->1->2->3->3`, return `1->2->3`.

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
    public ListNode deleteDuplicates(ListNode head) {
        ListNode list=head;
        while(list!=null&&list.next!=null){
        if(list.val!=list.next.val){
            list=list.next;
        }
        else{
            list.next=list.next.next;
        }
        }
        return head;
    }
}
~~~

可见就是判断当前节点和下一个节点是否相等，如果相等就让下一个节点等于下下个节点，如果不相等就让下一个节点等于当前指针，继续比较下去。