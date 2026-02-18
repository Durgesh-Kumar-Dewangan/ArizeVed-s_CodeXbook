# 🧮 Two Sum

> 🟢 Difficulty: Easy
> 🔗 Platform: LeetCode
> 📚 Topics: Array, Hash Table

---

## 📌 Problem Statement

Given an array of integers `nums` and an integer `target`, return the **indices** of the two numbers such that they add up to `target`.

### ⚠️ Constraints

* Each input has **exactly one solution**.
* You may **not use the same element twice**.
* You can return the answer in **any order**.

---

## 🧾 Examples

### Example 1

```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: nums[0] + nums[1] == 9
```

### Example 2

```
Input: nums = [3,2,4], target = 6
Output: [1,2]
```

### Example 3

```
Input: nums = [3,3], target = 6
Output: [0,1]
```

---

## 📊 Constraints

* `2 <= nums.length <= 10^4`
* `-10^9 <= nums[i] <= 10^9`
* `-10^9 <= target <= 10^9`
* Only one valid answer exists.

---

## 💡 Approach

### 🔹 Brute Force (O(n²))

* Check every pair of elements.
* If their sum equals the target, return their indices.
* Simple but inefficient for large inputs.

### 🔹 Optimized Approach — Hash Map (O(n))

Use a hash map (dictionary) to store numbers and their indices while iterating.

#### Algorithm:

1. Create an empty hash map.
2. Iterate through the array.
3. For each element:

   * Compute `complement = target - nums[i]`
   * If complement exists in the map → return indices.
   * Otherwise, store current number with its index.

---

## 🚀 Optimal Solution (Python)

```python
def twoSum(nums, target):
    hashmap = {}
    
    for i, num in enumerate(nums):
        complement = target - num
        
        if complement in hashmap:
            return [hashmap[complement], i]
        
        hashmap[num] = i
```

---

## ⏱ Time & Space Complexity

| Approach    | Time Complexity | Space Complexity |
| ----------- | --------------- | ---------------- |
| Brute Force | O(n²)           | O(1)             |
| Hash Map    | O(n)            | O(n)             |

---

## 🧠 Key Takeaway

Using a hash map allows us to reduce the time complexity from **O(n²)** to **O(n)** by trading space for speed.

---

### ⭐ If this helped you, consider giving the repository a star!
