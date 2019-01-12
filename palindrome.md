Determine whether an integer is a palindrome. Do this without extra space.

判断一个整型是否是回文，回文需要规避负数，以及小于10的正数，别的与之前的Reverse Number无异

    class Solution {
    public boolean isPalindrome(int x) {
        int result=0;
        if(x<0||(x%10==0&&x!=0)){
            return false;
        }
        while(x>result){
            result=result*10+x%10;
            x/=10;
        }
        return (x==result||x==result/10);
    }
    }
这是相对比较正确的解法，同时我也发现LeetCode测算runtime真的靠运气啊！