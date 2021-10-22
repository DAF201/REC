Given a string s, return the longest palindromic substring in s.


```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        mx=''
        #@all substrings
        res = [s[i: j] for i in range(len(s))
          for j in range(i + 1, len(s) + 1)]
          
        for x in res:
            if x==x[::-1]:
                if len(mx)<len(x):
                    mx=x
        return mx
```
