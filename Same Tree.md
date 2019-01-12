## Same Tree

Given two binary trees, write a function to check if they are the same or not.

Two binary trees are considered the same if they are structurally identical and the nodes have the same value.

**Example 1:**

```
Input:     1         1
          / \       / \
         2   3     2   3

        [1,2,3],   [1,2,3]

Output: true

```

**Example 2:**

```
Input:     1         1
          /           \
         2             2

        [1,2],     [1,null,2]

Output: false

```

**Example 3:**

```
Input:     1         1
          / \       / \
         2   1     1   2

        [1,2,1],   [1,1,2]

Output: false
```

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
    public boolean isSameTree(TreeNode p, TreeNode q) {
        if(p==null&&q==null){
            return true;
        }
        if(p == null || q == null){
            return false;
        } 
        if(p.val==q.val){
        return isSameTree(p.left,q.left)&&isSameTree(p.right,q.right);
        }
        return false;
    }
}
~~~

这个明显是使用递归，因此我们应该决定终止条件，当p,q为空时，则可以判断为真，乍看可能觉得不用判断p或q是否为空，但是如果不判断，我们无法保证p,q是否为空，因此无法进行p.val==q.val的判断，会报空指针错误。