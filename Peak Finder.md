# Peak Finder

## 问题

在一个数组中找一个peak，使之大于他的邻居即可。可假设数组两端为负无穷。

## 具体描述

A peak element is an element that is greater than its neighbors.

Given an input array where `num[i] ≠ num[i+1]`, find a peak element and return its index.

The array may contain multiple peaks, in that case return the index to any one of the peaks is fine.

You may imagine that `num[-1] = num[n] = -∞`.

For example, in array `[1, 2, 3, 1]`, 3 is a peak element and your function should return the index number 2.

## 算法描述

1. 因为我们假设两端为负无穷，因此我们只要找到数组的第一个元素大于第二个或最后一个元素大于倒数第二个元素即可说明其为peak。若还未找到即可使用for循环对数组进行遍历，判断某个元素是否大于其邻居，找到即可return。复杂度为O(n)
2. 易证在任何序列我们都可以找到局部的peak,所以我们使用二分法寻找，判断中间的元素是不是，如果不是，判断中间的元素是否大于右边的元素，大于就将序列变小为左边的序列，反之亦然。复杂度为O（logn)

## 代码

~~~
public static int traversal(int []numbers){
		if(numbers[0]>=numbers[1]){
			return numbers[0];
		}
		else if (numbers[numbers.length-1]>=numbers[numbers.length-2]){
			return numbers[numbers.length-1];
		}
		else{
		for(int i=1;i<numbers.length-1;i++){
			if(numbers[i-1]<=numbers[i]&&numbers[i+1]<=numbers[i]){
				return numbers[i];
			}
		}
		}
		return 0;
	}
~~~

~~~
public static int binarySearch(int []numbers){
		int low=0;
		int high=numbers.length-1;
		int mid=0;
		while(high>low){
			mid=(high+low)/2;
			if(numbers[mid]>=numbers[mid-1]&&numbers[mid]>=numbers[mid+1]){
				return numbers[mid];
			}
			else if(numbers[mid]>=numbers[mid+1]){
				high=mid;
			}
			else{
				low=mid+1;
			}
		}
		return low;
	}
~~~

## 进一步了解

[问题详细解答](https://leetcode.com/problems/find-peak-element/solution/)