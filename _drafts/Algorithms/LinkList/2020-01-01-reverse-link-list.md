---
layout: post
title: 反转链表
categories: Algorithms, 链表
---

# [剑指 Offer 24. 反转链表](https://leetcode-cn.com/problems/fan-zhuan-lian-biao-lcof/)

```
class ListNode {
    int val;
    ListNode next;
}
```

```
// 迭代
ListNode reverseList(ListNode head) {
    if (head == null || head.next == null) return head;

    ListNode cur = head, pre = null;

    while(cur != null) {
        ListNode tmp = cur.next;
        cur.next = pre;
        pre = cur;
        cur = tmp;
    }
    return pre;
}

```

```
// 递归
ListNode reverseList(ListNode head) {
    if (head == null || head.next == null) return head;
    return _reverse(head, null);
}

ListNode _reverse(ListNode cur, ListNode pre) {
    if (cur == null) return pre;
    ListNode res = _reverse(cur.next, cur);
    cur.next = pre;
    return res;
}

```