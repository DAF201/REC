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

```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        mx=s[0]
        for x in range(0,len(s)):
            if len(s)==1:
                return s[0]
            for y in range(x+1,len(s)):
                # print(s[x:y])
                if s[x]==s[y]:
                    a=s[x:y+1]
                    b=a[::-1]
                    if a==b:
                        # print(True)
                        # print(s[x:y])
                        if len(mx)<y-x+1:
                            mx=s[x:y+1]
        return mx
```
