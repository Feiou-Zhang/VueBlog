title: Guide
------------------------------------
<!-- en-US:+ -->


#### Question


>Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

>The brackets must close in the correct order, "()" and "()[]{}" are all valid but "(]" and "([)]" are not.


#### Tips

This is typical question test you on the data structure, if you understand `stack` well, you can easily answer this one.

```java
class Solution {
    public boolean isValid(String s) {
        char[] c = s.toCharArray();
        int len = c.length;
        if(len == 0 || len % 2 == 1) return false;
        if(c[0] == ')' || c[0] == ']' || c[0] == '}') return false;
        Stack<Character> stack = new Stack<>();
        for(char ch : c){
            if(ch == '(' || ch == '[' || ch == '{')
                stack.push(ch);
            if(ch == ')' && stack.pop() != '(')
                return false;
            if(ch == ']' && stack.pop() != '[')
                return false;
            if(ch == '}' && stack.pop() != '{')
                return false;
        }
        return stack.empty();
    }
}
```

<!-- en-US:- -->

<!-- zh-CN:+ -->

#### 概览

- [Vuelog 文件结构](#/blog/docs/2016/file-structure-of-vuelog)

#### 文档

- [自定义站点](#/blog/docs/2017/customize-the-site)
- [自定义导航菜单](#/blog/docs/2017/customize-navigation-menu)
- [新建文章或页面](#/blog/docs/2017/add-posts-or-pages)
- [编写文章或页面](#/blog/docs/2017/author-posts-or-pages)
- [插入语法高亮的代码块](#/blog/docs/2017/insert-code-blocks-with-syntax-highlight)
- [多语言支持](#/blog/docs/2017/multiple-languages-support)
- [使用社会化评论服务](#/blog/docs/2017/use-social-commenting-services)

#### 示例

- [样式示例](#/blog/showcase/2016/style-examples)

<!-- zh-CN:- -->
