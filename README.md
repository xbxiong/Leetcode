# Leetcode 刷题笔记
## Task 1：链表
- **203 [移除链表元素](https://leetcode-cn.com/problems/remove-linked-list-elements/)**  
  **题目**：给你一个链表的头节点`head`和一个整数`val`，请你删除链表中所有满足`Node.val == val`的节点，并返回新的头节点  
  **Tips**移除链表中元素：
  如果要删除节点`p`的下一个节点,只需要进行`p.next = p.next.next`操作便可将`p`的**下一个节点**删除。  
  **思路**：对于这一题只需要从头节点开始遍历一遍后续节点，（**即从`p.next`开始遍历**）将所有符合条件的节点移除即可  
  最后再判断头节点是否需要移除。  
  python 实现：  
  ```
  class Solution:
    def removeElements(self, head: ListNode, val: int) -> ListNode:
        p1 = head
        #print(p1.val)
        if p1 == None:
            return head
        while p1.next:
            if p1.next.val == val:
                p1.next = p1.next.next
            else:
                p1 = p1.next
        if head.val == val:
            head = head.next
        return head
  ```
  
