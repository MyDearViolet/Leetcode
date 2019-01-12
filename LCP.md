

Write a function to find the longest common prefix string amongst an array of strings.

    class Solution {
    public String longestCommonPrefix(String[] strs) {
        if(strs.length==0){
            return "";
        }
        String prefix=strs[0];
        for(int i=1;i<strs.length;i++){
        while(strs[i].indexOf(prefix)!=0){
            prefix=prefix.substring(0,prefix.length()-1);
            if(prefix.isEmpty()){
            return "";
            }
        }
        }
        return prefix;
    }
    }
    public String longestCommonPrefix(String[] strs) {
    if (strs == null || strs.length == 0) return "";
     for(int i=0;i<strs[0].length();i++){
         char c=strs[0].charAt(i);
         for(int j=1;j<strs.length;j++){
            if(i==strs[j].length()||strs[j].charAt(i)!=c){
                return strs[0].substring(0,i);
            }
         }
     }
        return strs[0];
    }
这上面是两种解题的思路，一种是定一个前缀，然后看看这个前缀在别的字符串里是不是，不是就一个一个字符的减少直到满足所有字符串为止。第二种则是垂直比较，一个一个字符进行比较，一个字符与数组里的字符串对应的字符比较。这两种是相对来说比较好理解的。

indexOf 方法返回一个整数值，指出 String 对象内子字符串的开始位置。如果没有找到子字符串，则返回-1。

**java.lang.String.charAt() **方法返回指定索引处的char值。索引范围是从0到length() - 1。

public String substring(int beginIndex, int endIndex)

第一个int为开始的索引，对应String数字中的开始位置，

第二个是截止的索引位置，对应String中的结束位置

1、取得的字符串长度为：endIndex - beginIndex;

2、从beginIndex开始取，到endIndex结束，从0开始数，其中不包括endIndex位置的字符