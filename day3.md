# 题目 21. 合并两个有序链表
## 描述 将两个有序链表合并为一个新的有序链表并返回。新链表是通过拼接给定的两个链表的所有节点组成的。 

示例：

输入：1->2->4, 1->3->4
输出：1->1->2->3->4->4

实现：
```
python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        if l1 and l2:
            if l1.val > l2.val:
                l1,l2=l2,l1
            l1.next = self.mergeTwoLists(l1.next,l2)
        return  l1 or l2
```

做这个之前不知道什么是链表 没理解 看了一下其他人的解法
链表是一种递归的数据结构，它或者为空（null），或者是指向一个结点（node）的引用，该节点还有一个元素和一个指向另一条链表的引用
return l1 or l2 那里 想了好久 不理解链表和列表的区别 
最后那里，排完l1的最后一个结点以后 l2还剩一个 l1此时为None， l1 and l2 为None ，return的时候return l2 那个结点
