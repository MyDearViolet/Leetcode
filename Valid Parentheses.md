Given a string containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

The brackets must close in the correct order, `"()"` and `"()[]{}"` are all valid but `"(]"` and `"([)]"` are not.

class Solution {

    public boolean isValid(String s) {
       Stack<Character> stack=new Stack<Character>();
       for(char c:s.toCharArray()){
        if (c == '(')
    		stack.push(')');
    	else if (c == '{')
    		stack.push('}');
    	else if (c == '[')
    		stack.push(']');
    	else if (stack.isEmpty() || stack.pop() != c)
    		return false;
       }
        return stack.isEmpty();
    }
}

做到这种题型很自然想到使用栈，但是居然java带有stack的集合框架，那么这个题目就简单了。

至于toCharArray()这个函数的意思是将一个字符串转换成一个Character型的字符数组，并且这里面的字符是原封不动的拿进去的。