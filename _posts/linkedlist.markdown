# Linked List

## Reverse a Linked List
### Solution 1: detach a node and insert after dummy
```java
public ListNode reverseList(ListNode head) {
    if (head == null || head.next == null) {
        return head;
    }
    // Add a dummy head, making it easier to insert a node at head.
    ListNode dummy = new ListNode(0);
    dummy.next = head;
    
    ListNode curr = head, next = null;
    while (curr.next != null) {
        next = curr.next;
        curr.next = next.next;
        next.next = dummy.next;
        dummy.next = next;
    }
    return dummy.next;
}
```
### Solution 2: use three pointers and iterate through the list.

Use three pointers: no need to create a helper node. Be aware of two things:
1. the tail.next should be null. 
2. the last two element should be linked.


```java
public ListNode reverseList(ListNode head) {
    if (head == null || head.next == null) {
        return head;
    }
    
    ListNode prev = null, curr = head, next = curr.next;
    while (next != null) {
        curr.next = prev;
        prev = curr;
        curr = next;
        next = curr.next;
    }
    curr.next = prev;
    return curr;
}
```

### Solution 3: recursively reverse the list.
The basic idea is to use a recursive helper. The helper takes the sublist after curr node as input, and  returns an array of ListNode. ret[0] is the head, while ret[1] is the tail of the reversed sublist. By this way, the last ListNode is passed through to the uppermost layer as ret[0].
```java
public ListNode reverseList(ListNode head) {
    if (head == null || head.next == null) {
        return head;
    }
    
    return helper(head)[0];
}

// Returns an array of ListNode: {head, tail}
private ListNode[] helper(ListNode node) {
    if (node.next == null) {
        return new ListNode[]{node, node};
    }
    
    ListNode[] prev = helper(node.next);
    node.next = prev[1].next;
    prev[1].next = node;
    return new ListNode[]{prev[0], node};
}
```


# Fast-slow pointer.


