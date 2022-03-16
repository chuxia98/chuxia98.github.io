---
layout: post
title: 删除中间节点
categories: Algorithms, 链表
---

# [876. 链表的中间结点](https://leetcode-cn.com/problems/middle-of-the-linked-list/)

```
ListNode middleNode(ListNode head) {
    ListNode slow = head, fast = head;
    while (fast != null, fast.next != null) {
        slow = slow.next;
        fast = fast.next.next;
    }
    return slow;
}
```