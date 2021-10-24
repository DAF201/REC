Given the head of a linked list, remove the nth node from the end of the list and return its head.

refer a little bit of previous code

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        new_head=[]
        while head is not None:
            new_head.append(head.val)
            head=head.next
        new_head.reverse()
        new_head.pop(n-1)
        new_head.reverse()
        result=cur=ListNode(0)
        for x in new_head:
            cur.next = ListNode(val = x)
            cur = cur.next
        cur.next=None
        return result.next
```
