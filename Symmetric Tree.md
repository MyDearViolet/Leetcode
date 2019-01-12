## Symmetric Tree

Given a binary tree, check whether it is a mirror of itself (ie, symmetric around its center).

For example, this binary tree `[1,2,2,3,4,4,3]` is symmetric:

```
    1
   / \
  2   2
 / \ / \
3  4 4  3

```

But the following `[1,2,2,null,3,null,3]` is not:

```
    1
   / \
  2   2
   \   \
   3    3

```

**Note:**
Bonus points if you could solve it both recursively and iteratively.

解决方法：

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
    public boolean isSymmetric(TreeNode root) {
        if(root!=null){
       return isMirror(root.left,root.right);
        }
        return true;
    }
    public boolean isMirror(TreeNode r1,TreeNode r2){
        if(r1==null&&r2==null){
            return true;
        }
        if(r1==null||r2==null){
            return false;
        }
        if(r1.val==r2.val){
            return isMirror(r1.left,r2.right)&&isMirror(r1.right,r2.left);
        }
        return false;
    }
}
~~~

判断一个数是否是对称的，我们就需要比较两个节点，因此声明一个isMirror方法,判断左右节点都为空，或者左右节点有一个为空的情况，我们只有排除了r1,r2是空的情况，才可以进行r1,r2值的比较，不然会报出空指针异常。当左右节点值相等的时候，我们继续往底部递归，调用isMirror方法，从而得出答案