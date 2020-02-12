# Reverse a Linked List
## https://leetcode.com/problems/reverse-linked-list

Reverse a singly linked list.
```
Example:

Input: 1->2->3->4->5->NULL
Output: 5->4->3->2->1->NULL
```

**Follow up:**

A linked list can be reversed either iteratively or recursively. Could you implement both?

# Implementation : Iterative 

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode reverseList(ListNode head) {
       ListNode curr = head;
       ListNode prev = null;
       while(curr != null){
           ListNode next = curr.next;
           curr.next = prev;
           prev = curr;
           curr = next;
       } 
       return prev; 
    }
}
```

# Implementation : Recursive

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode reverseList(ListNode head) {
       if(head == null || head.next == null){
           return head;
       }
       ListNode reversedListHead = reverseList(head.next);
       head.next.next = head;  
       head.next = null;
       return reversedListHead;
    }
}
```

# Reference :
https://www.youtube.com/watch?v=O0By4Zq0OFc
