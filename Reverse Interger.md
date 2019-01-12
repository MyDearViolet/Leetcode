Given a 32-bit signed integer, reverse digits of an integer.

**Example 1:**

```
Input: 123
Output:  321
```

**Example 2:**

```
Input: -123
Output: -321
```

**Example 3:**

```
Input: 120
Output: 21
```

**Note:**
Assume we are dealing with an environment which could only hold integers within the 32-bit signed integer range. For the purpose of this problem, assume that your function returns 0 when the reversed integer overflows.

解决办法：

    class Solution {
    public int reverse(int x) {
        int result=0;
        while(x!=0){
        	int tail=x%10;
            int newResult=result*10+tail;
            if((newResult-tail)/10!=result){
                return 0;
            }
            x=x/10;
            result=newResult;
        }
       return result;
     }
    }
本来这是一个简单的翻转数字，但是给的是32位的整数，因此需要有所判断，超出界限就应该return 0

那么该如何判断呢？假设得出的newResult是溢出的，那么它得出的值是混乱的，因此利用newResult重新逆着计算就会得出不一样的答案。