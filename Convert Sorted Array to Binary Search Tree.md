## Convert Sorted Array to Binary Search Tree

Given an array where elements are sorted in ascending order, convert it to a height balanced BST.

~~~
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    public TreeNode sortedArrayToBST(int[] nums) {
        if(nums.length==0){
            return null;
        }
        TreeNode head=helper(nums,0,nums.length-1);
        return head;
    }
    public TreeNode helper(int[] nums,int low,int high){
        if(low>high){
            return null;
        }
        int mid=(high+low)/2;
        TreeNode root=new TreeNode(nums[mid]);
        root.left=helper(nums,low,mid-1);
        root.right=helper(nums,mid+1,high);
        return root;
    }
}
~~~

很明显，给我们一个排序了的数组，为了得到平衡的二叉查找树，那么我们需要不断取数组的中间节点即可。很容易我们又想到了递归，不断将数组分成两份，将各自的数组中的中间元素赋给左节点和右节点，然后得出答案。