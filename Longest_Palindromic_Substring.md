Given a string s, return the longest palindromic substring in s.

Both reach the time limit
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
#@right side looping
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

others' solution:

```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        p = ''
        for i in range(len(s)):
            p1 = self.get_palindrome(s, i, i+1)
            p2 = self.get_palindrome(s, i, i)
            p = max([p, p1, p2], key=lambda x: len(x))
        return p
    
    def get_palindrome(self, s: str, l: int, r: int) -> str:
        while l >= 0 and r < len(s) and s[l] == s[r]:
            l -= 1
            r += 1
        return s[l+1:r]
```
