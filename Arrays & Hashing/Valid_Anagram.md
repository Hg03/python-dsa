# [Problem Statement](https://leetcode.com/problems/valid-anagram/)

# Approach - We'll check first the length of both string, if both are not equal then they can't be anagram of each other. If equal then sort both strings and check if they are equal or not. If equal return true else false.

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:

        if len(s) != len(t):
            return False
        else:
            sorted_s = sorted(s)
            sorted_t = sorted(t)
            return sorted_s == sorted_t
```

# Approach - Here we'll use hashmap, first we'll store it to store the frequency of characters of string in map, then we'll iterate the other string and reduce the frequency of same map. If frequency in the map of each becomes zero, it means it is valid anagram else not.

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False

        countS, countT = {}, {}

        for i in range(len(s)):
            countS[s[i]] = 1 + countS.get(s[i], 0)
            countT[t[i]] = 1 + countT.get(t[i], 0)
        return countS == countT

```
