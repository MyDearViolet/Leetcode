## Balanced Binary Tree

Given a binary tree, determine if it is height-balanced.

For this problem, a height-balanced binary tree is defined as a binary tree in which the depth of the two subtrees of *every* node never differ by more than 1.

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
    public boolean isBalanced(TreeNode root) {
        if(root==null){
            return true;
        }
       return height(root)!=-1;
    }
    public int height(TreeNode root){
        if(root==null){
        return 0;
        }    
        int sum1=height(root.left);
        int sum2=height(root.right);
        if(sum1==-1||sum2==-1||Math.abs(sum1-sum2)>1){
            return -1;
        }
        else if(sum1-sum2>0){
        return sum1+1;
        }
        else return sum2+1;
    }
}
~~~

用递归来做，判断左右字数深度是否大于1，大于1就返回-1，然后往上的节点也不需要比较直接置-1即可，否则就不断给深度大