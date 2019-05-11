# 题目 20. 有效的括号
## 描述：
给定一个只包括 '('，')'，'{'，'}'，'['，']' 的字符串，判断字符串是否有效。

有效字符串需满足：

左括号必须用相同类型的右括号闭合。
左括号必须以正确的顺序闭合。
注意空字符串可被认为是有效字符串。
## 代码
```
python
class Solution:
    def isValid(self, s: str) -> bool:
        #if (len(s)%2) == 0:
        #    mid = len(s)//2
        #    for i in range(0,mid):
        #        if list(s)[i]==list(s)[-i-1]:
        #            return True
        #else:
        #    return False
        while any(('()' in s, '[]' in s, '{}' in s)):
            s = s.replace('()', '').replace('[]', '').replace('{}', '')
        return not s
```
注释掉的是我写错的，题解的思路是是一对的话就消除，我的解法“（）”的时候老是返回null，不太明白为什么。。。明天问一下
