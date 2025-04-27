# Problem 1929: Concatenation of Array

🔗 [Problem Link](https://leetcode.com/problems/contains-duplicate/)

🏷️ **Problem Type:** Array, Hash Table, Set

---

## ✨ My Approach
- Create a set from the original list, which automatically removes duplicates.
- Compare the size of the set (`newSet`) with the size of the original list (`nums`).
- If lengths are the same, no duplicates exist; otherwise, duplicates are present.
- Return `True` if a duplicate exists, `False` otherwise.

---

## 🧩 Code
```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        newSet = set(nums)
        count = len(newSet)
        countOld = len(nums)
        print(count)
        print(countOld)
        if count == countOld:
            return False
        else:
            return True
```

---

## ⏳ Time and Space Complexity
- **Time Complexity:** O(n)
- **Space Complexity:** O(n)

---

## 🔀 Alternate Approach 1
- Use a set while traversing the array:

- For each number, check if it already exists in the set.

- If yes, immediately return True.

- Otherwise, add it to the set.
### Code
```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        seen = set()
        for num in nums:
            if num in seen:
                return True
            seen.add(num)
        return False

```
- **Time Complexity:** O(n)
- **Space Complexity:** O(n)

---

## 🔀 Alternate Approach 2
- Sort the array first:

- If any two adjacent elements are the same, a duplicate exists.
### Code
```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        nums.sort()
        for i in range(1, len(nums)):
            if nums[i] == nums[i - 1]:
                return True
        return False

```
- **Time Complexity:** O(n log(n))
- **Space Complexity:** O(1)
