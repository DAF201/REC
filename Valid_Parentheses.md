Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.

Open brackets must be closed in the correct order.

vaild:{[()]}

invaild:({[])}

```python
class Solution:
    def isValid(self, s: str) -> bool:
        while len(s) > 0:
            l = len(s)
            s = s.replace('()', '')
            s = s.replace('{}', '')
            s = s.replace('[]', '')
            if l == len(s):
                return False
        return True
```

all valid baskets will be removed finally, if the length didn't change at any point, it means it is invalid
