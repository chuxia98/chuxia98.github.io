---
layout: post
title: 反转单链表
categories: Algorithms, 链表
---


```
class Node {
    int val;
    Node next;
}

Node reverseList(Node head) {
    if (head == null) return;

    Node cur = head;

    while(cur != null) {
        Node tmp = cur.next;
        cur.next = head;
        head.next = cur;
        cur = tmp;
    }
}
```