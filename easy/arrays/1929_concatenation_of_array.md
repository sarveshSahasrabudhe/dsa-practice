# Problem 1929: Concatenation of Array

🔗 [Problem Link](https://leetcode.com/problems/concatenation-of-array/)

🏷️ **Problem Type:** Array

---

## ✨ My Approach
- Concatenate the list with itself using multiplication (`2*nums`).
- This duplicates the original list in sequence.
- Return the new list.

---

## 🧩 Code
\`\`\`python
class Solution:
    def getConcatenation(self, nums: List[int]) -> List[int]:
        ans = 2 * nums
        return ans
\`\`\`

---

## ⏳ Time and Space Complexity
- **Time Complexity:** O(n)
- **Space Complexity:** O(n)

---

## 🔀 Alternate Approach 1
- Manually append elements into a new list twice.

### Code
\`\`\`python
class Solution:
    def getConcatenation(self, nums: List[int]) -> List[int]:
        ans = []
        for _ in range(2):
            for num in nums:
                ans.append(num)
        return ans
\`\`\`
- **Time Complexity:** O(n)
- **Space Complexity:** O(n)

---

## 🔀 Alternate Approach 2
- Use list addition: `nums + nums`

### Code
\`\`\`python
class Solution:
    def getConcatenation(self, nums: List[int]) -> List[int]:
        return nums + nums
\`\`\`
- **Time Complexity:** O(n)
- **Space Complexity:** O(n)
