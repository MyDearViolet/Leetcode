# Climbing Stairs

You are climbing a stair case. It takes *n* steps to reach to the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

**Note:** Given *n* will be a positive integer.

**Example 1:**

```
Input: 2
Output:  2
Explanation:  There are two ways to climb to the top.

1. 1 step + 1 step
2. 2 steps
```

**Example 2:**

```
Input: 3
Output:  3
Explanation:  There are three ways to climb to the top.

1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step
```

通过观察我们可以发现这个问题其实类似于斐波那契问题，fn=fn-1+fn-2,因为最后一步不是1就是2，所以这个问题就可以分解成两个问题：到达目的差两步和到达目的差一步的问题，然后不断的向下分解即可。

~~~
class Solution {
    public int climbStairs(int n) {
        if(n==0||n==1||n==2){
        return n;
        }
        int oneStep=1;
        int twoStep=2;
        int sumStep=0;
        for(int i=2;i<n;i++){
            sumStep=oneStep+twoStep;
            oneStep=twoStep;
            twoStep=sumStep;
        }
        return sumStep;
    }
}
~~~

