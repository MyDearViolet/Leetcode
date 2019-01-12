## Count Primes

**Description:**

Count the number of prime numbers less than a non-negative number, **n**.

Solution：

~~~
class Solution {
    public int countPrimes(int n) {
        if(n<3){
            return 0;
        }
        boolean[] notPrime=new boolean[n];
        int count=0;
        for(int i=2;i<n;i++){
            if(notPrime[i]==false){
                count++; 
            for(int j=2;i*j<n;j++){
                notPrime[i*j]=true;
                }
            }
            }
         return count;
            }
    }
~~~

这个是个很聪明的做法，利用动态规划，巧妙利用n前的质数，质数和任何数的乘积得到的数肯定不是质数，而没有通过乘积得到的就是质数