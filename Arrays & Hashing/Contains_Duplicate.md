# [Problem Statement](https://leetcode.com/problems/contains-duplicate/)

# Approach - Use two for loops (in nested format) and check for each element and its further elements , if any two element are equal return true else false.

```python
class Solution:
    # Time Complexity - O(n^2)
    def containsDuplicate(self, nums: List[int]) -> bool:
        for i in range(len(nums)):
            for j in range(i+1,len(nums)):
                if nums[i] == nums[j]:
                    return True
        return False
```

# Approach - Use hashset to store all the elements and then if length of original array and length hashset is equal or not. If length is equal return false else return true.

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        hashset = set()
        for i in nums:
            hashset.add(i)
        return False if len(hashset) == len(nums) else True
```

# Approach - Use hashset to store the element of array one by one using for loop and check that does that element that we are going to insert exist in set or not. If it exist , it means we've encountered duplicate value

```
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        hashset = set()
        for i in nums:
            if i in hashset:
              return True
            hashset.add(i)
        return False
```


