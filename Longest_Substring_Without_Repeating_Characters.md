Given a string s, find the length of the longest substring without repeating characters.


```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        seen = {}
        mx = left = 0
        for right, c in enumerate(s):
            if c in seen:
                left = max(left, seen[c] + 1)
            seen[c] = right
            mx = max(mx, right-left+1)
        return mx
```
those guys are genius
```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        seen = ''
        mx = 0
        for c in s:
            if c not in seen:
                seen += c
            else:
                mx = max(mx, len(seen))
                seen = seen[seen.index(c) + 1:] + c
        return max(mx, len(seen))
```
