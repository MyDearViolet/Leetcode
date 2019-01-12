## Ugly Number

Write a program to check whether a given number is an ugly number.

Ugly numbers are positive numbers whose prime factors only include `2, 3, 5`. For example, `6, 8` are ugly while `14` is not ugly since it includes another prime factor `7`.

Note that `1` is typically treated as an ugly number.

~~~
class Solution {
    public boolean isUgly(int num) {
        if (num <= 0) {return false;}
        if(num==1){
            return true;
        }
        if(num%2!=0&&num%3!=0&&num%5!=0){
            return false;
        }
        if(num%2==0){
            return isUgly(num/2);
        }
        else if(num%3==0){
            return isUgly(num/3);
        }
        else if(num%5==0){
            return isUgly(num/5);
        }
        return false;
    }
}
~~~

这个也相对简单，因为题目条件因此num<0及num==1的判断条件可以写出，然后判断num是否能整除2,3,5如果不能即可以知道不是ugly number，如果有整除就递归调用方法，判断是不是即可。 