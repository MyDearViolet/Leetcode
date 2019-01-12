Find the contiguous subarray within an array (containing at least one number) which has the largest sum.

For example, given the array `[-2,1,-3,4,-1,2,1,-5,4]`,
the contiguous subarray `[4,-1,2,1]` has the largest sum = `6`.

    public int maxSubArray(int[] nums) {
        int largest=Integer.MIN_VALUE;
        int sum=0;
        for(int i=0;i<nums.length;i++){
        if(sum<0){
            sum=nums[i];
        }
        else{
            sum+=nums[i];
        }
        if(sum>largest){
            largest=sum;
        }
        }
         return largest;
    }
```
public int maxSubArray(int[] A) {
    int max = A[0], dp = A[0];
    for (int i = 1; i < A.length; i++) {            
        dp = Math.max(dp + A[i] ,A[i]);
        max = Math.max(max, dp);
    }
    return max;
}
```