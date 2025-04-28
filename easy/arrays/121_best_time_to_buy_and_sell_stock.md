
# Problem 121: Best Time to Buy and Sell Stock

🔗 [Problem Link](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

🏷️ **Problem Type:** Array, Two Pointers, Greedy

---

## ✨ My Approach
- Use two pointers: l_p (left pointer for buy day) and r_p (right pointer for sell day).
- Initially, set buy day at 0 and sell day at 1.
- If prices[r_p] > prices[l_p], calculate profit and update curr_profit if it's better than previous.
- If not profitable (prices[r_p] <= prices[l_p]), move the buy pointer to the current sell day.
- Always move the sell pointer one step ahead.

---

## 🧩 Code
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        curr_profit = 0
        l_p = 0
        r_p = 1
        while r_p < len(prices):
            if prices[l_p] < prices[r_p]:
                curr_profit = max(curr_profit, prices[r_p] - prices[l_p])
            else:
                l_p = r_p
            r_p += 1
        return curr_profit
```

---

## ⏳ Time and Space Complexity
- **Time Complexity:** O(n)
- **Space Complexity:** O(1)

---

## 🔀 Alternate Approach 1
- Track the minimum price seen so far and calculate profit at every step.
- At each price, check the profit if you sell at that day.

### Code
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        min_price = float('inf')
        max_profit = 0
        for price in prices:
            if price < min_price:
                min_price = price
            elif price - min_price > max_profit:
                max_profit = price - min_price
        return max_profit
```

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)

---

## 🔀 Alternate Approach 2
- Brute Force (Not optimal):
- Try buying at every day and selling at every future day.
- Compare all possible profits.

### Code
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        max_profit = 0
        for i in range(len(prices)):
            for j in range(i+1, len(prices)):
                if prices[j] > prices[i]:
                    max_profit = max(max_profit, prices[j] - prices[i])
        return max_profit
```

- **Time Complexity:** O(n²)
- **Space Complexity:** O(1)
