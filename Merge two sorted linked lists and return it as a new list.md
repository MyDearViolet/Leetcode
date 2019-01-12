Merge two sorted linked lists and return it as a new list. The new list should be made by splicing together the nodes of the first two lists.

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
    public ListNode mergeTwoLists(ListNode l1, ListNode l2) {
        if(l1==null){
            return l2;
        }
        if(l2==null){
            return l1;
        }
        ListNode node;
        if(l1.val>l2.val){
            node=l2;
            node.next=mergeTwoLists(l1,l2.next);
        }
        else{
        node=l1;
        node.next=mergeTwoLists(l1.next,l2);
        }
        return node;
    }
}
~~~

