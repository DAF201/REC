You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

```

Input: l1 = [2,4,3], l2 = [5,6,4]
Output: [7,0,8]
Explanation: 342 + 465 = 807.

```

```
Input: l1 = [9,9,9,9,9,9,9], l2 = [9,9,9,9]
Output: [8,9,9,9,0,0,0,1]
```

```python
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def addTwoNumbers(self, l1:ListNode, l2: ListNode) -> ListNode:
        
        
        temp1=''
        l = []
        n = l1
        while n is not None:
            l.append(n.val)
            n = n.next
        l1=l
        l1.reverse()
        
        
        l=[]
        n = l2
        while n is not None:
            l.append(n.val)
            n = n.next
        l2=l
        
        l1.reverse()
        for x in l1:
            temp1=temp1+str(x)
            
            
        l2.reverse()
        temp2=''
        for x in l2:
            temp2=temp2+str(x)
        result=list(str(int(temp1)+int(temp2)))
        
        dummy = curr =  ListNode(0)

        for i in result:
            curr.next = ListNode(val = int(i))
            curr = curr.next

        curr.next  = None
        return dummy.next
```
