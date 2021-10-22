```python
class Solution:
     def longestCommonPrefix(self, strs):
        if len(strs) == 0:
            return ''
        strs.sort(key=lambda x: len(x))
        s = strs[0]
        res = [s[i: j] for i in range(len(s))for j in range(i + 1, len(s) + 1)]
        res.sort(key=lambda x: -len(x))
        for x in res:
            if all([x in y for y in strs]):
                return x
        return ''
```
