## Merge Sorted Array

Given two sorted integer arrays *nums1* and *nums2*, merge *nums2* into *nums1* as one sorted array.

**Note:**
You may assume that *nums1* has enough space (size that is greater or equal to *m* + *n*) to hold additional elements from *nums2*. The number of elements initialized in *nums1* and *nums2* are *m* and *n* respectively.

~~~
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        int i=m-1;int j=n-1;int sum=m+n-1;
        while(i>=0&&j>=0){
        if(nums1[i]>nums2[j]){
            nums1[sum--]=nums1[i--];
        }
        else{
        nums1[sum--]=nums2[j--];
        }
        }
        while(j>=0){
            nums1[sum--]=nums2[j--];
        }
    }
}
~~~

因为题目表示要把两个数组合并到nums1中，但是不能把合并的数组元素放在nums1的前部，因为这会导致没有比较的元素遗失，因此从后往前进行比较。