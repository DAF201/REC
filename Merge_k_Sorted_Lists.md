You are given an array of k linked-lists lists, each linked-list is sorted in ascending order.

Merge all the linked-lists into one sorted linked-list and return it.

```python

# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def mergeKLists(self, lists: List[Optional[ListNode]]) -> Optional[ListNode]:
        inputs=[]
        for x in lists:
            while x is not None:
                inputs.append(x.val)
                x=x.next
        result=[]
        for x in inputs:
            result.append(x)
        result.sort()
        fin=cur=ListNode(0)
        for x in result:
            cur.next=ListNode(val=x)
            cur=cur.next
        cur.next=None
        return fin.next
        ```
