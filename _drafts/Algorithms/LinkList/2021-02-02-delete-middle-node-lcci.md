---
layout: post
title: 删除中间节点
categories: Algorithms, 链表
---

# [面试题 02.03. 删除中间节点](https://leetcode-cn.com/problems/delete-middle-node-lcci/)

```
public void deleteNode(ListNode node) {
    node.val = node.next.val;
    node.next = node.next.next;        
}

```