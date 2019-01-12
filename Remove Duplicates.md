Given a sorted array, remove the duplicates [**in-place**](https://en.wikipedia.org/wiki/In-place_algorithm) such that each element appear only *once* and return the new length.

Do not allocate extra space for another array, you must do this by **modifying the input array in-place** with O(1) extra memory.

~~~
class Solution {
    public int removeDuplicates(int[] nums) {
        if(nums.length==0){
            return 0;
        }
       int i=0;
        for(int j=1;j<nums.length;j++){
            if(nums[j]!=nums[i]){
            i++;
            nums[i]=nums[j];
            }
        }  
    return (i+1);
    }
}
~~~

因为要求不能构建一个新的数组只能依靠数组向前覆盖了，找不到不相等就覆盖。