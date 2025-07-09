# Bloomberg Interview Coding Problems

This README contains a list of coding problems I solved for my Bloomberg interview prep. Problems are grouped in the order they were tackled and include table of contents for easy navigation.

---

## Table of Contents

1. [Longest Substring Without Repeating Characters](#1-longest-substring-without-repeating-characters)
2. [Merge k Sorted Lists](#2-merge-k-sorted-lists)
3. [Number of Islands (Grid flood-fill)](#3-number-of-islands-grid-flood-fill)
4. [LRU Cache Design](#4-lru-cache-design)
5. [Top K Frequent Elements](#5-top-k-frequent-elements)
6. [Median of Two Sorted Arrays](#6-median-of-two-sorted-arrays)
7. [Container With Most Water](#7-container-with-most-water)
8. [Word Ladder (Shortest transformation)](#8-word-ladder-shortest-transformation)
9. [Coin Change (DP)](#9-coin-change-dp)
10. [Clone Graph / Course Schedule (Cycle Detection)](#10-clone-graph--course-schedule-cycle-detection)
11. [Subarray Sum Equals K](#11-subarray-sum-equals-k)
12. [Serialize/Deserialize Binary Tree](#12-serializedeserialize-binary-tree)
13. [Meeting Rooms II (min meeting rooms)](#13-meeting-rooms-ii-min-meeting-rooms)
14. [K Closest Points to Origin](#14-k-closest-points-to-origin)
15. [Insert/Delete/GetRandom O(1)](#15-insertdeletegetrandom-o1)
16. [3Sum](#16-3sum)
17. [Product of Array Except Self](#17-product-of-array-except-self)
18. [Coin Change](#18-coin-change)
19. [Lowest Common Ancestor](#19-lowest-common-ancestor)
20. [Minimum Window Substring](#20-minimum-window-substring)
21. [Unique Paths](#21-unique-paths)
22. [Bit Manipulation: Single Number, Subsets](#22-bit-manipulation-single-number-subsets)
23. [Partition Labels](#23-partition-labels)
24. [Candy Crush](#24-candy-crush)
25. [Maximum Difference Between Even and Odd Frequency II](#25-maximum-difference-between-even-and-odd-frequency-ii)
26. [Insert Delete GetRandom O(1) (variant)](#26-insert-delete-getrandom-o1-variant)
27. [Max Area of Island](#27-max-area-of-island)
28. [Best Time to Buy and Sell Stock](#28-best-time-to-buy-and-sell-stock)
29. [Invalid Transactions](#29-invalid-transactions)
30. [Design Underground System](#30-design-underground-system)
31. [Decode String](#31-decode-string)
32. [Two City Scheduling](#32-two-city-scheduling)
33. [Remove All Adjacent Duplicates in String II](#33-remove-all-adjacent-duplicates-in-string-ii)
34. [Merge Intervals](#34-merge-intervals)
35. [Design an Ordered Stream](#35-design-an-ordered-stream)
36. [Flatten a Multilevel Doubly Linked List](#36-flatten-a-multilevel-doubly-linked-list)
37. [All Paths From Source to Target](#37-all-paths-from-source-to-target)
38. [Two Sum](#38-two-sum)
39. [Word Search](#39-word-search)
40. [Valid Anagram](#40-valid-anagram)
41. [Validate Binary Search Tree](#41-validate-binary-search-tree)
42. [Word Break II](#42-word-break-ii)
43. [Design A Leaderboard](#43-design-a-leaderboard)
44. [Knapsack Problem & 3 Stones Variant (3Sum)](#44-knapsack-problem--3-stones-variant-3sum)
45. [A very big sum](#45-a-very-big-sum)
46. [Left Rotation](#46-left-rotation)
47. [Insert a Node at a Position Given in a List](#47-insert-a-node-at-a-position-given-in-a-list)
48. [Cycle Detection](#48-cycle-detection)
49. [Balanced Brackets](#49-balanced-brackets)
50. [Queue Using Two Stacks](#50-queue-using-two-stacks)
51. [Ice Cream Parlour](#51-ice-cream-parlour)
52. [Insertion Sort - Part 1](#52-insertion-sort---part-1)
53. [Insertion Sort - Part 2](#53-insertion-sort---part-2)
54. [Binary Tree Insertion](#54-binary-tree-insertion)
55. [Height of a Binary Tree](#55-height-of-a-binary-tree)
56. [Breadth First Search](#56-breadth-first-search)
57. [Snakes and Ladders](#57-snakes-and-ladders)
58. [Fibonacci Numbers](#58-fibonacci-numbers)

---

## 1. Longest Substring Without Repeating Characters

### Problem Statement

Given a string `s`, find the length of the longest substring without repeating characters.

### Example

**Input:** `"abcabcbb"`  
**Output:** `3`  
**Explanation:** The answer is `"abc"`, with the length of 3.

**Input:** `"bbbbb"`  
**Output:** `1`  
**Explanation:** The answer is `"b"`.

**Input:** `"pwwkew"`  
**Output:** `3`  
**Explanation:** The answer is `"wke"`.

### Constraints

- 0 <= s.length <= 5 \* 10^4
- s consists of English letters, digits, symbols, and spaces.

### Smart Questions to Ask Before/During Solving

- Are the characters case-sensitive? (e.g., is 'A' different from 'a'?)
- Can the input string be empty? What should be returned in that case?
- Can the string contain special characters or spaces?
- Do I need to return the substring or just its length?
- What is the expected time complexity? Is O(n^2) acceptable?
- Are Unicode characters possible or only ASCII?

### Edge Cases

- Empty string: `""` should return 0.
- String with all identical characters: `"aaaaaa"` should return 1.
- String with all unique characters: `"abcdef"` should return the length of the whole string.
- Very long string to test performance, up to 50,000 characters.

### Specific Scenarios

- String with mixed characters and numbers: `"a1b2c3d4"`.
- String with special characters: `"a@#a$%^&*()"`.
- String with spaces and tabs: `"a b c d e"`.

### Performance Requirements

- Optimal solution should run in O(n) time, where n is the length of the string.
- Use constant space or O(min(n, m)) where m is the character set size (usually 128 or 256 for ASCII).

### Pattern Used to Solve

- Sliding Window technique with two pointers.
- HashMap (or Dictionary in C#) to store the last seen index of characters.

### Approach in Simple Words

- Use two pointers (start and end) to represent the sliding window of the current substring without repeating characters.
- Move the end pointer forward, adding characters to the window.
- If a character repeats (found in the window), move the start pointer forward to remove the repeated character.
- Keep track of the maximum length of such substrings while expanding and contracting the window.
- Return the maximum length found.

### C# Solution with Explanation

```csharp
using System;
using System.Collections.Generic;

public class Solution {
    public int LengthOfLongestSubstring(string s) {
        if (string.IsNullOrEmpty(s))
            return 0;

        Dictionary<char, int> charIndexMap = new Dictionary<char, int>();
        int maxLength = 0;
        int start = 0;

        for (int end = 0; end < s.Length; end++) {
            char currentChar = s[end];

            // If character is found in the map and is inside current window
            if (charIndexMap.ContainsKey(currentChar) && charIndexMap[currentChar] >= start) {
                // Move the start pointer to one position after the last occurrence
                start = charIndexMap[currentChar] + 1;
            }

            // Update or add the current character's latest index
            charIndexMap[currentChar] = end;

            // Calculate max length of substring without repeating characters
            maxLength = Math.Max(maxLength, end - start + 1);
        }

        return maxLength;
    }
}
```

### Explanation

- We use a dictionary to map each character to its latest index.
- As we iterate through the string with end pointer, if the character was seen before and is inside the current window (start to end), we move the start pointer to exclude the previous occurrence.
- We keep updating the maximum length as we go.

### Counter Questions and Answers

**Q1: What if the input is null or empty?**  
A: Return 0 since no substring exists.

**Q2: How do you handle case sensitivity?**  
A: The code treats uppercase and lowercase characters as distinct.

**Q3: Can you return the substring instead of length?**  
A: Yes, by storing the start index of the max substring and slicing at the end.

**Q4: Why use a dictionary instead of a set?**  
A: The dictionary stores the index of characters to quickly jump the start pointer, which a set cannot do efficiently.

**Q5: What is the time complexity?**  
A: O(n), as each character is visited at most twice (start and end pointers).

**Q6: What if the input contains Unicode characters?**  
A: The dictionary will still work fine since keys are char which supports Unicode characters.

---

## 2. Merge k Sorted Lists

### Problem Statement

You are given an array of k linked-lists, each linked-list is sorted in ascending order.

Merge all the linked-lists into one sorted linked-list and return it.

### Example

**Input:** `lists = [[1->4->5],[1->3->4],[2->6]]`  
**Output:** `1->1->2->3->4->4->5->6`  
**Explanation:** The merged linked list in sorted order is 1->1->2->3->4->4->5->6.

**Input:** `lists = []`  
**Output:** `[]`

**Input:** `lists = [[]]`  
**Output:** `[]`

### Constraints

- `k == lists.length`
- `0 <= k <= 10^4`
- `0 <= lists[i].length <= 500`
- `-10^4 <= lists[i][j] <= 10^4`
- `lists[i]` is sorted in ascending order.
- The sum of `lists[i].length` won’t exceed 10^4.

### Smart Questions to Ask Before/During Solving

- What if the input array of lists is empty or contains empty lists?
- Are all input lists sorted in ascending order?
- How large can k be and how large can each list be?
- Do we need to preserve the input lists or can we modify them?
- What data structure should be used to efficiently merge multiple sorted lists?
- What should be the time and space complexity?

### Edge Cases

- Empty array of lists.
- Lists with one or zero elements.
- Lists with duplicate elements.
- Lists with negative numbers.
- Lists where some or all are empty.
- Lists where all nodes have the same value.

### Specific Scenarios

- k = 1, just one list.
- All lists are empty.
- One very long list and many short lists.
- Lists with overlapping or non-overlapping ranges of values.

### Performance Requirements

- Aim for O(N log k) time complexity, where N is the total number of nodes.
- Space complexity should be O(k) or less (excluding the output list itself).

### Pattern Used to Solve

- Divide and conquer merging.
- Priority Queue (Min Heap) for efficient retrieval of smallest current node.
- Linked list merging technique.

### Approach in Simple Words

- Use a min heap (priority queue) to keep track of the smallest current head nodes of all k lists.
- Push the head of each list into the min heap.
- Pop the smallest node from the heap and attach it to the merged list.
- If the popped node has a next node, push that next node into the min heap.
- Repeat until all nodes are merged.
- Return the head of the merged linked list.

### C# Solution with Explanation

```csharp
using System;
using System.Collections.Generic;

public class ListNode {
    public int val;
    public ListNode next;
    public ListNode(int val=0, ListNode next=null) {
        this.val = val;
        this.next = next;
    }
}

public class Solution {
    public ListNode MergeKLists(ListNode[] lists) {
        if (lists == null || lists.Length == 0)
            return null;

        // Comparer for min heap to compare ListNode by their values
        var comparer = Comparer<ListNode>.Create((a, b) => a.val - b.val);
        var minHeap = new SortedSet<ListNode>(comparer);

        // We use a SortedSet but it requires unique elements, so we can
        // implement a custom comparer or use a PriorityQueue from .NET 6+
        // For now, let's use PriorityQueue if available (C# 10 / .NET 6)

        return MergeWithPriorityQueue(lists);
    }

    private ListNode MergeWithPriorityQueue(ListNode[] lists) {
#if NET6_0_OR_GREATER
        var pq = new PriorityQueue<ListNode, int>();

        // Push all non-null heads into priority queue
        foreach (var node in lists) {
            if (node != null) {
                pq.Enqueue(node, node.val);
            }
        }

        var dummy = new ListNode(0);
        var current = dummy;

        while (pq.Count > 0) {
            var smallestNode = pq.Dequeue();
            current.next = smallestNode;
            current = current.next;

            if (smallestNode.next != null) {
                pq.Enqueue(smallestNode.next, smallestNode.next.val);
            }
        }

        return dummy.next;
#else
        // Fallback for earlier versions - use a manual min heap implementation or divide and conquer
        return MergeKListsDivideAndConquer(lists);
#endif
    }

    private ListNode MergeKListsDivideAndConquer(ListNode[] lists) {
        if (lists.Length == 0) return null;
        int interval = 1;
        while (interval < lists.Length) {
            for (int i = 0; i + interval < lists.Length; i += interval * 2) {
                lists[i] = MergeTwoLists(lists[i], lists[i + interval]);
            }
            interval *= 2;
        }
        return lists[0];
    }

    private ListNode MergeTwoLists(ListNode l1, ListNode l2) {
        var dummy = new ListNode(0);
        var current = dummy;

        while (l1 != null && l2 != null) {
            if (l1.val < l2.val) {
                current.next = l1;
                l1 = l1.next;
            } else {
                current.next = l2;
                l2 = l2.next;
            }
            current = current.next;
        }

        current.next = (l1 != null) ? l1 : l2;

        return dummy.next;
    }
}
```

### Explanation

- If you’re using .NET 6 or higher, the PriorityQueue<TElement, TPriority> class makes it very simple to implement the min heap.
- For older versions, a divide and conquer approach is used to merge pairs of lists repeatedly until only one list remains.
- The MergeTwoLists method merges two sorted linked lists in O(n) time.
- Overall complexity is O(N log k), where N is total nodes and k is number of lists.

### Counter Questions and Answers

**Q1: What if the lists array is empty or null?**  
A: Return null.

**Q2: Can the input lists contain empty linked lists?**  
A: Yes, they will be handled naturally by skipping null heads.

**Q3: What if all lists are empty?**  
A: The output is null.

**Q4: Can the lists contain duplicate values?**  
A: Yes, duplicates are allowed and merged in order.

**Q5: Why choose priority queue over simple merging?**  
A: Priority queue merges in O(N log k), efficient when k is large.

**Q6: What if k=1?**  
A: The function will return the single list itself.

---

## 3. Number of Islands (Grid flood-fill)

### Problem Statement

Given a 2D grid map of '1's (land) and '0's (water), count the number of islands.
An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically.
You may assume all four edges of the grid are surrounded by water.

### Example

**Input:**

```csharp
char[][] grid = {
    new char[] { '1', '1', '0', '0', '0' },
    new char[] { '1', '1', '0', '0', '0' },
    new char[] { '0', '0', '1', '0', '0' },
    new char[] { '0', '0', '0', '1', '1' }
};
```

**Output:**

```
3
```

**Explanation:**

- First island: Top-left 1s
- Second island: Center 1
- Third island: Bottom-right cluster of 1s

### Smart Questions to Ask Before/During Solving

- Can the grid be empty or null?
- Are diagonal connections considered part of the same island? (No, only up/down/left/right)
- Can we modify the input grid?
- What is the maximum size of the grid?
- Are all characters guaranteed to be '0' or '1'?

### Edge Cases

- Empty grid → 0
- Grid with all '0' → 0
- Grid with all '1' → 1
- Single row or column
- Grid with diagonal islands → should not count as connected

### Specific Scenarios

- Multiple disconnected islands
- Large sparse matrix
- Very long narrow grid (e.g., 1x1000)

### Performance Requirements

- **Time Complexity:** O(m × n), where m is number of rows and n is number of columns.
- **Space Complexity:** O(m × n) for visited flags (or O(1) if modifying grid in-place).

### Pattern Used

- Flood Fill / DFS / BFS
- Similar to “connected components in graph”

### Simple Approach Explanation

Traverse each cell in the grid:

- If you find a '1', it’s the start of a new island.
- Use DFS or BFS to visit all connected '1's, marking them as '0' to avoid revisiting.
- Count how many times this happens → number of islands.

### C# Solution

```csharp
using System;

public class Solution {
    public int NumIslands(char[][] grid) {
        if (grid == null || grid.Length == 0) return 0;

        int rows = grid.Length;
        int cols = grid[0].Length;
        int count = 0;

        for (int r = 0; r < rows; r++) {
            for (int c = 0; c < cols; c++) {
                if (grid[r][c] == '1') {
                    count++;
                    DFS(grid, r, c);
                }
            }
        }

        return count;
    }

    private void DFS(char[][] grid, int r, int c) {
        if (r < 0 || c < 0 || r >= grid.Length || c >= grid[0].Length || grid[r][c] == '0')
            return;

        grid[r][c] = '0'; // mark as visited

        DFS(grid, r - 1, c); // up
        DFS(grid, r + 1, c); // down
        DFS(grid, r, c - 1); // left
        DFS(grid, r, c + 1); // right
    }
}
```

### Add Main Method to Test

```csharp
public class Program {
    public static void Main(string[] args) {
        char[][] grid = new char[][] {
            new char[] { '1', '1', '0', '0', '0' },
            new char[] { '1', '1', '0', '0', '0' },
            new char[] { '0', '0', '1', '0', '0' },
            new char[] { '0', '0', '0', '1', '1' }
        };

        Solution sol = new Solution();
        int islands = sol.NumIslands(grid);

        Console.WriteLine($"Number of Islands: {islands}");
    }
}
```

### Constraints (from Leetcode)

- m == grid.length
- n == grid[i].length
- 1 <= m, n <= 300
- grid[i][j] is '0' or '1'

### Counter Questions You Can Ask

| Question                             | Answer                                                             |
| ------------------------------------ | ------------------------------------------------------------------ |
| Can I change the original grid?      | Yes, in-place marking is allowed                                   |
| What defines an island?              | 1s connected horizontally or vertically                            |
| What if I want to preserve the grid? | Use a bool[][] visited array                                       |
| Can BFS be used instead of DFS?      | Yes, BFS is also valid and sometimes safer for very deep recursion |
| Will grid always be rectangular?     | Yes                                                                |

### Considering diagonals as part of the island

Same idea as before, but now, instead of just checking 4 neighbors (up/down/left/right), we also check 4 diagonal neighbors:
up-left, up-right, down-left, down-right

### The 8 Directions

| Direction    | Row Change (`dr`) | Col Change (`dc`) |
| ------------ | :---------------: | :---------------: |
| Top-Left     |        -1         |        -1         |
| Top          |        -1         |         0         |
| Top-Right    |        -1         |        +1         |
| Right        |         0         |        +1         |
| Bottom-Right |        +1         |        +1         |
| Bottom       |        +1         |         0         |
| Bottom-Left  |        +1         |        -1         |
| Left         |         0         |        -1         |

### C# Solution (with diagonals)

```csharp
using System;

public class Solution {
    // 8 directions: horizontal, vertical, and diagonals
    private readonly int[] dr = { -1, -1, -1, 0, 1, 1, 1, 0 };
    private readonly int[] dc = { -1, 0, 1, 1, 1, 0, -1, -1 };

    public int NumIslands(char[][] grid) {
        if (grid == null || grid.Length == 0) return 0;

        int rows = grid.Length;
        int cols = grid[0].Length;
        int count = 0;

        for (int r = 0; r < rows; r++) {
            for (int c = 0; c < cols; c++) {
                if (grid[r][c] == '1') {
                    count++;
                    DFS(grid, r, c);
                }
            }
        }

        return count;
    }

    private void DFS(char[][] grid, int r, int c) {
        if (r < 0 || c < 0 || r >= grid.Length || c >= grid[0].Length || grid[r][c] == '0')
            return;

        grid[r][c] = '0'; // mark as visited

        for (int d = 0; d < 8; d++) {
            DFS(grid, r + dr[d], c + dc[d]);
        }
    }
}
```

---

## 4. LRU Cache Design

### Problem Statement

Design a Least Recently Used (LRU) Cache that supports the following operations in O(1) time:

- `Get(key)`: Return the value of the key if it exists in the cache; otherwise, return -1.
- `Put(key, value)`: Insert or update the value of the key. If the number of keys exceeds the capacity, evict the least recently used key.

### Example Input & Output

```csharp
LRUCache cache = new LRUCache(2); // Capacity = 2

cache.Put(1, 1);
cache.Put(2, 2);
Console.WriteLine(cache.Get(1)); // returns 1

cache.Put(3, 3); // Evicts key 2

Console.WriteLine(cache.Get(2)); // returns -1 (not found)
cache.Put(4, 4); // Evicts key 1

Console.WriteLine(cache.Get(1)); // returns -1 (not found)
Console.WriteLine(cache.Get(3)); // returns 3
Console.WriteLine(cache.Get(4)); // returns 4
```

### Smart Questions to Ask

- Can we assume keys are unique?
- Should we update "recently used" if Get() is called?
- Can values be duplicated?
- What’s the expected capacity range?
- Should we handle negative keys or values?

### Edge Cases

- Get from an empty cache
- Put existing key (update value, move to recent)
- Multiple evictions
- Capacity = 0
- Repeated gets on same key

### Performance Requirements

All operations must run in O(1) time:

- O(1) insert
- O(1) delete
- O(1) access

### Pattern Used

- HashMap + Doubly Linked List
- Also known as the "Design Pattern" problem or "LRU Design" problem

### Approach (In Simple Words)

- Use a Dictionary (HashMap) for O(1) access by key.
- Use a Doubly Linked List to maintain usage order (most recently used at head, least at tail).
- When `Get()` is called: Move that node to the head.
- When `Put()` is called:
  - If key exists: update value, move to head.
  - If key doesn’t exist: Add to head.  
    If over capacity, remove node at the tail (least recently used).
- Every node contains: key, value, prev, next.

### C# Solution

```csharp
using System;
using System.Collections.Generic;

public class LRUCache {
    private class Node {
        public int key;
        public int value;
        public Node prev, next;
        public Node(int k, int v) {
            key = k;
            value = v;
        }
    }

    private Dictionary<int, Node> cache;
    private Node head, tail;
    private int capacity;

    public LRUCache(int capacity) {
        this.capacity = capacity;
        cache = new Dictionary<int, Node>();

        head = new Node(0, 0); // dummy head
        tail = new Node(0, 0); // dummy tail
        head.next = tail;
        tail.prev = head;
    }

    public int Get(int key) {
        if (!cache.ContainsKey(key))
            return -1;

        Node node = cache[key];
        Remove(node);
        InsertToFront(node);
        return node.value;
    }

    public void Put(int key, int value) {
        if (cache.ContainsKey(key)) {
            Node node = cache[key];
            node.value = value;
            Remove(node);
            InsertToFront(node);
        } else {
            if (cache.Count >= capacity) {
                // Remove least recently used node
                Node lru = tail.prev;
                Remove(lru);
                cache.Remove(lru.key);
            }

            Node newNode = new Node(key, value);
            cache[key] = newNode;
            InsertToFront(newNode);
        }
    }

    private void Remove(Node node) {
        node.prev.next = node.next;
        node.next.prev = node.prev;
    }

    private void InsertToFront(Node node) {
        node.next = head.next;
        node.prev = head;
        head.next.prev = node;
        head.next = node;
    }
}
```

### Test with Main Method

```csharp
public class Program {
    public static void Main(string[] args) {
        LRUCache cache = new LRUCache(2);

        cache.Put(1, 1);
        cache.Put(2, 2);
        Console.WriteLine(cache.Get(1)); // 1

        cache.Put(3, 3); // evicts 2
        Console.WriteLine(cache.Get(2)); // -1

        cache.Put(4, 4); // evicts 1
        Console.WriteLine(cache.Get(1)); // -1
        Console.WriteLine(cache.Get(3)); // 3
        Console.WriteLine(cache.Get(4)); // 4
    }
}
```

### Constraints

- 1 <= capacity <= 3000
- 0 <= key <= 10^4
- 0 <= value <= 10^5
- Operations: up to 10^5

### Counter Questions & Answers

| Question                        | Answer                                                   |
| ------------------------------- | -------------------------------------------------------- |
| Can keys be repeated in Put()?  | Yes, it updates the value                                |
| Does Get() update usage order?  | Yes, moves to front                                      |
| What if capacity = 0?           | Nothing can be stored                                    |
| Can values be negative or zero? | Yes, unless otherwise stated                             |
| Can we use Queue/Stack instead? | No, they can't offer O(1) deletion of arbitrary element  |
| Can LinkedList class be used?   | Not easily, since LinkedListNode doesn’t give key access |

---

## 5. Top K Frequent Elements

### Problem Statement

Given an integer array `nums` and an integer `k`, return the k most frequent elements.  
You must solve it in O(n log n) or better time complexity.

### Example Input & Output

```csharp
Input: nums = [1,1,1,2,2,3], k = 2
Output: [1,2]

Input: nums = [1], k = 1
Output: [1]
// Note: The order of output doesn’t matter as long as the correct top K elements are present.
```

### Smart Questions to Ask

- Can multiple elements have the same frequency?
- Should the result be sorted in any way?
- Can k be equal to the length of the array?
- Are elements guaranteed to be integers?
- Is the input array ever empty?

### Edge Cases

- All elements are the same
- k == nums.Length
- k == 1 but multiple elements have the same frequency
- Large arrays with very few distinct values

### Performance Requirement

- Must run in O(n log k) or better
- Brute force with sorting full frequency list = ❌ Not efficient for large inputs

### Pattern Used

- ✅ Bucket Sort
- ✅ HashMap + Min Heap (PriorityQueue)
- Or sometimes: Quickselect (partial sort)

### Approach (Simple Words)

**Idea:**

- Count frequencies of all elements using a `Dictionary<int, int>`.
- Use a Min Heap (PriorityQueue) to keep track of the top k frequent elements.
- Push entries into heap by frequency.
- If heap size > k, remove the element with lowest frequency.
- Return the keys of the heap.
- ✅ This gives O(n log k) time using a heap.

### C# Code (with Min Heap)

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

public class Solution {
    public int[] TopKFrequent(int[] nums, int k) {
        // Step 1: Count frequency
        Dictionary<int, int> freqMap = new Dictionary<int, int>();
        foreach (var num in nums) {
            if (!freqMap.ContainsKey(num)) freqMap[num] = 0;
            freqMap[num]++;
        }

        // Step 2: Use min-heap based on frequency
        var heap = new PriorityQueue<int, int>(); // Item, Priority (Frequency)

        foreach (var entry in freqMap) {
            heap.Enqueue(entry.Key, entry.Value);
            if (heap.Count > k) {
                heap.Dequeue(); // Remove least frequent
            }
        }

        // Step 3: Extract top k elements
        List<int> result = new List<int>();
        while (heap.Count > 0) {
            result.Add(heap.Dequeue());
        }

        // Optional: Reverse if needed (to show most frequent first)
        result.Reverse();

        return result.ToArray();
    }
}
```

### Main Method to Test It

```csharp
public class Program {
    public static void Main(string[] args) {
        Solution sol = new Solution();

        int[] nums1 = {1,1,1,2,2,3};
        int k1 = 2;
        Console.WriteLine(string.Join(",", sol.TopKFrequent(nums1, k1))); // Output: 1,2

        int[] nums2 = {1};
        int k2 = 1;
        Console.WriteLine(string.Join(",", sol.TopKFrequent(nums2, k2))); // Output: 1
    }
}
```

### Constraints

- 1 <= nums.Length <= 10^5
- k is always valid: 1 <= k <= unique elements in nums
- -10^4 <= nums[i] <= 10^4

### Counter Questions & Their Answers

| Question                                 | Answer                     |
| ---------------------------------------- | -------------------------- |
| Are all numbers integers?                | Yes, guaranteed            |
| Can output order vary?                   | Yes, unless required       |
| Should I return exactly k elements?      | Yes                        |
| Can I use LINQ’s OrderByDescending?      | Yes, but it gives O(nlogn) |
| Can two elements have same frequency?    | Yes                        |
| Can we use Dictionary and PriorityQueue? | Yes, optimal combo         |

---

### 🔁 Alternate Approaches (Bucket Sort (O(n)))

**Idea:**

- Count the frequency of each number.
- Use an array of lists (bucket[]) where index represents frequency.
- Put numbers into buckets based on their frequency.
- Start from the end of the bucket (highest frequency), and gather top k elements.

**C# Code with Bucket Sort**

```csharp
using System;
using System.Collections.Generic;

public class Solution {
    public int[] TopKFrequent(int[] nums, int k) {
        // Step 1: Count frequencies
        Dictionary<int, int> freqMap = new Dictionary<int, int>();
        foreach (int num in nums) {
            if (!freqMap.ContainsKey(num)) freqMap[num] = 0;
            freqMap[num]++;
        }

        // Step 2: Create buckets. Index = frequency
        // Max frequency possible = nums.Length
        List<int>[] buckets = new List[nums.Length + 1];
        foreach (var pair in freqMap) {
            int freq = pair.Value;
            if (buckets[freq] == null) {
                buckets[freq] = new List<int>();
            }
            buckets[freq].Add(pair.Key);
        }

        // Step 3: Gather top k frequent elements from buckets
        List<int> result = new List<int>();
        for (int i = buckets.Length - 1; i >= 0 && result.Count < k; i--) {
            if (buckets[i] != null) {
                foreach (int num in buckets[i]) {
                    result.Add(num);
                    if (result.Count == k) break;
                }
            }
        }

        return result.ToArray();
    }
}
```

**Main Method to Run and Test**

```csharp
public class Program {
    public static void Main(string[] args) {
        Solution sol = new Solution();

        int[] nums1 = {1, 1, 1, 2, 2, 3};
        int k1 = 2;
        Console.WriteLine("Top K Frequent: " + string.Join(", ", sol.TopKFrequent(nums1, k1))); // Output: 1, 2

        int[] nums2 = {4, 4, 4, 5, 5, 6};
        int k2 = 1;
        Console.WriteLine("Top K Frequent: " + string.Join(", ", sol.TopKFrequent(nums2, k2))); // Output: 4

        int[] nums3 = {1};
        int k3 = 1;
        Console.WriteLine("Top K Frequent: " + string.Join(", ", sol.TopKFrequent(nums3, k3))); // Output: 1
    }
}
```

### Time & Space Complexity

| Type  | Complexity |
| ----- | ---------- |
| Time  | O(n)       |
| Space | O(n)       |

n = nums.Length

Buckets size is O(n), and every number is processed once.

---

## 6. Median of Two Sorted Arrays

### Problem Statement

Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.

The overall runtime complexity should be O(log(min(m,n))).

### Example

```csharp
// Example 1:
Input: nums1 = [1,3], nums2 = [2]
Output: 2.0
// Combined array: [1,2,3] → median = 2

// Example 2:
Input: nums1 = [1,2], nums2 = [3,4]
Output: 2.5
// Combined array: [1,2,3,4] → median = (2+3)/2 = 2.5
```

### Smart Questions to Ask

- Are the arrays always sorted? (✅ Yes)
- Can arrays be empty? (One can be, not both)
- Is it allowed to merge both arrays? (⚠️ No, not optimal)
- Can we assume arrays won't have duplicates? (Duplicates are fine)

### Edge Cases

- One array is empty: median is from the other array.
- Arrays of different lengths.
- Even total length: median is average of two middle values.
- Large arrays (need log time performance).

### Constraints

```csharp
0 <= nums1.length, nums2.length <= 10^6
1 <= nums1.length + nums2.length
-10^6 <= nums[i] <= 10^6
// Arrays are sorted
```

### Pattern Used

- Binary Search on Partitions (Advanced two-pointer + binary search combo)
- This is a classic "Binary Search in Answer Space" problem.

### Approach (Explained Simply)

- Perform binary search on the smaller array.
- Partition both arrays so that:
  - left part of nums1 + left part of nums2 = total left half
  - right part = total right half
- Ensure:
  - All elements on the left part are ≤ all elements on the right part
- When found:
  - If total length is even: return average of max(left parts) and min(right parts)
  - If odd: return max of left parts

### C# Code

```csharp
public class Solution {
    public double FindMedianSortedArrays(int[] nums1, int[] nums2) {
        if (nums1.Length > nums2.Length) {
            return FindMedianSortedArrays(nums2, nums1);
        }

        int m = nums1.Length;
        int n = nums2.Length;
        int half = (m + n + 1) / 2;

        int left = 0, right = m;

        while (left <= right) {
            int i = (left + right) / 2;
            int j = half - i;

            int left1 = (i == 0) ? int.MinValue : nums1[i - 1];
            int right1 = (i == m) ? int.MaxValue : nums1[i];

            int left2 = (j == 0) ? int.MinValue : nums2[j - 1];
            int right2 = (j == n) ? int.MaxValue : nums2[j];

            if (left1 <= right2 && left2 <= right1) {
                if ((m + n) % 2 == 0) {
                    return (Math.Max(left1, left2) + Math.Min(right1, right2)) / 2.0;
                } else {
                    return Math.Max(left1, left2);
                }
            } else if (left1 > right2) {
                right = i - 1;
            } else {
                left = i + 1;
            }
        }

        throw new ArgumentException("Input arrays are not valid.");
    }

    public static void Main(string[] args) {
        var sol = new Solution();
        Console.WriteLine(sol.FindMedianSortedArrays(new int[] {1, 3}, new int[] {2}));          // 2.0
        Console.WriteLine(sol.FindMedianSortedArrays(new int[] {1, 2}, new int[] {3, 4}));      // 2.5
        Console.WriteLine(sol.FindMedianSortedArrays(new int[] {}, new int[] {1}));             // 1.0
    }
}
```

### Performance

| Metric     | Value                     |
| ---------- | ------------------------- |
| Time       | O(log(min(m, n)))         |
| Space      | O(1)                      |
| No merging | Efficient on large arrays |

### Counter Questions & Answers

**Q1: Can I just merge both arrays and get the median?**  
A1: You can, but that gives O(n + m) time — not optimal.

**Q2: What if one array is empty?**  
A2: Handled by treating min/max values on boundaries.

**Q3: What if arrays are of unequal length?**  
A3: Binary search always happens on the smaller array.

---

## 7. Container With Most Water

### Problem Statement

You are given an integer array `height` of length n.  
There are n vertical lines such that the two endpoints of the i-th line are at (i, 0) and (i, height[i]).

Find two lines that together with the x-axis form a container, such that the container holds the most water.

Return the maximum amount of water a container can store.

### Example

```csharp
// Example 1:
Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
// The lines at index 1 and 8 can store the most water → min(8,7) * (8-1) = 49

// Example 2:
Input: height = [1,1]
Output: 1
```

### Smart Questions to Ask

- Can I move only inward, or can I skip?
- Can the heights be zero?
- Are we allowed to use the same line twice?
- Does the order of lines matter?

### Edge Cases

- All elements are the same height.
- Heights are in increasing or decreasing order.
- Very small array (like [1, 2])
- Zeros in between tall lines.

### Constraints

```csharp
n == height.length
2 <= n <= 10^5
0 <= height[i] <= 10^4
```

### Pattern Used

- Two Pointers → Shrink Towards Optimal
- This is a greedy + two-pointer problem. You always try to maximize the area while reducing the limiting factor.

### Simple Approach

- Start with two pointers: one at the beginning and one at the end.
- Calculate the area.
- Move the pointer with the smaller height, since it's the limiting factor.
- Repeat until pointers meet.

### C# Code

```csharp
public class Solution {
    public int MaxArea(int[] height) {
        int left = 0, right = height.Length - 1;
        int maxArea = 0;

        while (left < right) {
            int h = Math.Min(height[left], height[right]);
            int w = right - left;
            maxArea = Math.Max(maxArea, h * w);

            // Move the smaller height inward
            if (height[left] < height[right])
                left++;
            else
                right--;
        }

        return maxArea;
    }

    public static void Main(string[] args) {
        var sol = new Solution();

        Console.WriteLine(sol.MaxArea(new int[] {1,8,6,2,5,4,8,3,7})); // Output: 49
        Console.WriteLine(sol.MaxArea(new int[] {1,1}));               // Output: 1
        Console.WriteLine(sol.MaxArea(new int[] {4,3,2,1,4}));         // Output: 16
    }
}
```

### Performance

| Metric   | Value |
| -------- | ----- |
| Time     | O(n)  |
| Space    | O(1)  |
| In-place | Yes   |

### Counter Questions & Answers

**Q1: Why can’t we check all pairs?**  
A1: That’s O(n^2) — not efficient for n = 10^5.

**Q2: Why do we move the shorter line’s pointer?**  
A2: Because area is limited by the shorter line. Moving it may give taller lines and better area.

**Q3: What if multiple pairs give the same max area?**  
A3: We just return the area — not the pair.

### Why min(height[left], height[right])?

Think of it like this:

Imagine two walls:

```java
Left wall = 8
Right wall = 3
```

Even though the left wall is tall, you can't fill water beyond 3, because it would spill over the right wall.

So the max height of water is determined by the shorter of the two walls.

### Visual Analogy

```
Left = 8           Right = 3

|
|
|     |
|     |
|     |
|     |
|     |   <-- water can only go up to here
|     |__
```

No matter how tall the left is, the right limits the container.

### Summary

We pick the `min(height[left], height[right])` because:

- That’s the maximum height the water can reach between the two lines.
- If we used the taller one, the calculated area would be incorrect (it assumes water can float in air).

---

## 8. Word Ladder (Shortest transformation)

### Problem Statement

Given two words, `beginWord` and `endWord`, and a dictionary `wordList`, find the length of the shortest transformation sequence from `beginWord` to `endWord` such that:

- Only one letter can be changed at a time.
- Each transformed word must exist in the wordList.

Return the number of words in the shortest transformation sequence (including `beginWord` and `endWord`).  
If there is no possible transformation, return 0.

### Example

```csharp
beginWord = "hit"
endWord = "cog"
wordList = ["hot","dot","dog","lot","log","cog"]

Output: 5
// Explanation: One shortest transformation is:
// "hit" → "hot" → "dot" → "dog" → "cog"
```

### Smart Questions to Ask

- Are words case-sensitive? (Typically no, assume all lowercase.)
- Can endWord be missing in wordList? (Yes, and return 0 then.)
- Are all words the same length? (Yes.)
- Can I reuse words? (No, each word can only be used once.)
- Can I pre-process the wordList for faster access?

### Edge Cases

- `beginWord == endWord` → Return 1
- `wordList` is empty → Return 0
- `endWord` is not in the list → Return 0
- No possible transformation (disconnected graph)

### Pattern Used

- Breadth-First Search (BFS)
- Graph traversal where:
  - Nodes = words
  - Edges = 1-character transformations

### Simple Words Explanation

Imagine every word is a node in a graph.

You draw a line (edge) between two words if they differ by exactly one letter.

You start at `beginWord` and want to reach `endWord` in the fewest hops, using only valid dictionary words.

So, you run BFS, exploring level by level, until you find `endWord`.

### Constraints

- 1 <= beginWord.length <= 10
- 1 <= wordList.length <= 5000
- Words are all lowercase and of same length

### Approach

- Convert `wordList` to a HashSet for O(1) lookup.
- Use a Queue for BFS traversal.
- At each step, try changing one letter at a time to form a new word.
- If the new word is in the set, enqueue it.
- Track levels (distance from `beginWord`) until `endWord` is found.

### C# Code

```csharp
using System;
using System.Collections.Generic;

public class Solution {
    public int LadderLength(string beginWord, string endWord, IList<string> wordList) {
        var wordSet = new HashSet<string>(wordList);
        if (!wordSet.Contains(endWord))
            return 0;

        var queue = new Queue<(string word, int level)>();
        queue.Enqueue((beginWord, 1));

        while (queue.Count > 0) {
            var (currentWord, level) = queue.Dequeue();

            if (currentWord == endWord)
                return level;

            char[] wordChars = currentWord.ToCharArray();
            for (int i = 0; i < wordChars.Length; i++) {
                char originalChar = wordChars[i];
                for (char c = 'a'; c <= 'z'; c++) {
                    wordChars[i] = c;
                    string newWord = new string(wordChars);
                    if (wordSet.Contains(newWord)) {
                        queue.Enqueue((newWord, level + 1));
                        wordSet.Remove(newWord); // mark as visited
                    }
                }
                wordChars[i] = originalChar;
            }
        }

        return 0;
    }

    public static void Main() {
        var solution = new Solution();

        string beginWord = "hit";
        string endWord = "cog";
        var wordList = new List<string> { "hot", "dot", "dog", "lot", "log", "cog" };

        int result = solution.LadderLength(beginWord, endWord, wordList);
        Console.WriteLine("Shortest transformation length: " + result);  // Output: 5
    }
}
```

### Performance

| Metric | Value         |
| ------ | ------------- |
| Time   | O(N _ 26 _ L) |
| Space  | O(N \* L)     |

Where:

- N = number of words in wordList
- L = length of each word

### Counter Questions & Answers

Q: Why BFS and not DFS?  
A: BFS guarantees the shortest path (fewest transformations). DFS may find longer paths first.

Q: Why remove the word from wordSet after using it?  
A: To avoid cycles or redundant paths.

Q: Can there be multiple shortest paths?  
A: Yes — but you only return the length, not the path.

Q: What if no valid path?  
A: Return 0.

---

## 9. Coin Change (DP)

### Problem Statement

You are given an integer array `coins` representing different denominations and an integer `amount` representing a total amount of money.

Return the fewest number of coins that you need to make up that amount. If it's not possible, return -1.

### Example Input / Output

```csharp
coins = [1, 2, 5]
amount = 11
Output: 3  // (5 + 5 + 1)
```

### Smart Questions to Ask

- Can coins be reused unlimited times? → Yes
- Is there always a solution? → No, may return -1
- Are coin values unique? → Yes
- Can the amount be zero? → Yes, return 0

### Edge Cases

- amount = 0 → Return 0
- coins = [2], amount = 3 → Return -1 (not possible)
- coins = [] → Return -1
- Large amount with only 1 coin → test performance

### Performance Requirements

- Time complexity must be better than brute-force exponential
- Optimal: O(amount \* n) where n = coins.Length

### Pattern Used

- Dynamic Programming (Bottom-Up)
- Unbounded Knapsack (can pick same item unlimited times)

### Simple Intuition

We build a `dp[]` array where:

- `dp[i]` = fewest coins needed to make amount `i`
- Start with `dp[0] = 0` (0 coins needed for amount 0)
- Initialize the rest of `dp` with ∞ (or a large number)
- For each coin, we update the array:  
  `dp[i] = min(dp[i], dp[i - coin] + 1)`

### C# Code (With Main Method)

```csharp
using System;

public class Solution {
    public int CoinChange(int[] coins, int amount) {
        int max = amount + 1;
        int[] dp = new int[amount + 1];
        Array.Fill(dp, max); // Fill with a large number
        dp[0] = 0;

        for (int i = 1; i <= amount; i++) {
            foreach (int coin in coins) {
                if (i - coin >= 0) {
                    dp[i] = Math.Min(dp[i], dp[i - coin] + 1);
                }
            }
        }

        return dp[amount] == max ? -1 : dp[amount];
    }

    public static void Main(string[] args) {
        var solution = new Solution();
        int[] coins = {1, 2, 5};
        int amount = 11;
        Console.WriteLine("Minimum coins required: " + solution.CoinChange(coins, amount));  // Output: 3
    }
}
```

### Dry Run for Input: [1, 2, 5], amount = 11

Initialize `dp[0] = 0`, rest = ∞

For each coin (1, 2, 5), update `dp[1]` to `dp[11]`

Result builds up like:

```
dp = [0,1,1,2,2,1,2,2,3,3,2,3]
```

### Constraints

- 1 <= coins.Length <= 12
- 1 <= coins[i] <= 2^31 - 1
- 0 <= amount <= 10^4

### Follow-up / Variations

- Coin Change II (Count number of ways)
- Unbounded knapsack variations
- Min/Max coins for fixed denominations

### Counter Questions & Answers

Q: Why use amount + 1 as initial value in dp[]?  
A: It's a safe upper bound. The worst-case would take `amount` coins of value 1.

Q: Why is this not greedy?  
A: Greedy fails in cases like `coins = [1, 3, 4], amount = 6`  
→ Greedy gives 1+1+1+1+1+1 = 6, but optimal is 3+3 = 2 coins.

Q: Can this be done top-down (memoization)?  
A: Yes! A recursive + memoized solution is also possible and equivalent in complexity.

## 10. Clone Graph / Course Schedule (Cycle Detection)

### Problem Statement

You are given:

- `numCourses`: Total number of courses labeled from 0 to numCourses - 1
- `prerequisites`: Array of pairs [a, b] meaning to take course a, you must first take course b

Return true if it's possible to finish all courses, otherwise return false.

### Example Inputs & Outputs

```csharp
// Example 1
Input: numCourses = 2, prerequisites = [[1, 0]]
Output: true
// You can take 0 → then 1

// Example 2
Input: numCourses = 2, prerequisites = [[1, 0], [0, 1]]
Output: false
// Cycle detected: 0 → 1 → 0
```

### Smart Questions to Ask

- Is it guaranteed that all courses are listed from 0 to numCourses - 1? Yes
- Are there duplicate prerequisite pairs? Usually not, but we can handle them.
- Can there be disconnected course components? Yes
- Can there be no prerequisites? Yes, return true

### Edge Cases

- No prerequisites → Always return true
- Self-loop like [0, 0] → Return false
- Multiple disjoint graphs
- Single course (numCourses = 1)

### Performance Requirements

- Time Complexity: O(N + E)  
  N = number of courses, E = number of prerequisites
- Space Complexity: O(N + E)

### Pattern Used

- Topological Sort (Kahn’s Algorithm using BFS) or DFS with cycle detection
- Problem is classic Cycle Detection in a Directed Graph

### Intuition & Approach (BFS - Kahn's Algorithm)

1. Build graph: adjacency list for prerequisites
2. Compute indegree of each course
3. Use BFS:
   - Add courses with indegree 0 to queue
   - For each course taken, reduce indegree of its neighbors
   - If all courses are processed → return true
   - Otherwise → cycle exists, return false

### C# Code (with Main method)

```csharp
using System;
using System.Collections.Generic;

public class Solution {
    public bool CanFinish(int numCourses, int[][] prerequisites) {
        List<int>[] graph = new List<int>[numCourses];
        int[] indegree = new int[numCourses];

        // Initialize adjacency list
        for (int i = 0; i < numCourses; i++) {
            graph[i] = new List<int>();
        }

        // Build graph and indegree
        foreach (var pair in prerequisites) {
            int course = pair[0];
            int prereq = pair[1];
            graph[prereq].Add(course);
            indegree[course]++;
        }

        Queue<int> queue = new Queue<int>();

        // Add all courses with 0 indegree
        for (int i = 0; i < numCourses; i++) {
            if (indegree[i] == 0) {
                queue.Enqueue(i);
            }
        }

        int completed = 0;

        while (queue.Count > 0) {
            int curr = queue.Dequeue();
            completed++;

            foreach (int neighbor in graph[curr]) {
                indegree[neighbor]--;
                if (indegree[neighbor] == 0) {
                    queue.Enqueue(neighbor);
                }
            }
        }

        return completed == numCourses;
    }

    public static void Main(string[] args) {
        var solution = new Solution();
        int numCourses = 4;
        int[][] prerequisites = new int[][] {
            new int[] {1, 0},
            new int[] {2, 1},
            new int[] {3, 2}
        };

        bool result = solution.CanFinish(numCourses, prerequisites);
        Console.WriteLine("Can finish all courses? " + result); // Output: True
    }
}
```

### Alternate Approach (DFS)

Use a visited[] array with 3 states: 0 = unvisited, 1 = visiting, 2 = visited.  
If we revisit a node marked 1, that’s a cycle.

### Constraints

- 1 <= numCourses <= 10^5
- 0 <= prerequisites.Length <= 5000
- prerequisites[i].Length == 2

### Counter Questions & Answers

Q: What if some courses are completely disconnected?  
A: That’s fine — as long as no cycle exists, we can finish them in any order.

Q: Why do we use indegree for Kahn’s Algorithm?  
A: It helps detect courses that can be taken right now (no pending prerequisites).

Q: Can this be done recursively?  
A: Yes — DFS with backtracking and state-marking for cycle detection.

## 11. Subarray Sum Equals K

### Problem Statement

Given an array of integers `nums` and an integer `k`, return the total number of continuous subarrays whose sum equals to `k`.

### Example Input & Output

**Example 1:**

```csharp
Input: nums = [1, 1, 1], k = 2
Output: 2
Explanation: The subarrays [1,1] at indices [0,1] and [1,2] both sum to 2.
```

**Example 2:**

```csharp
Input: nums = [1, 2, 3], k = 3
Output: 2
Explanation: Subarrays [1,2] and [3]
```

### Smart Questions to Ask

- Can the numbers be negative? Yes
- Are subarrays required to be contiguous? Yes
- Is the array length large? Could be up to 20,000
- Can k be zero or negative? Yes
- Do we need to return subarray indices or just the count? Just the count

### Edge Cases

- All elements zero, and k=0 → Multiple overlapping zero-sum subarrays
- No valid subarray → Return 0
- Very large or very small values (test for overflows)

### Pattern Used

- Prefix Sum + HashMap (to track sum frequencies efficiently)
- Sliding Window (only works with all positives, not here)

### Approach in Simple Words

Use prefix sum to keep a running total as you move through the array.

Keep a dictionary (hashmap) to record how many times each prefix sum has occurred.

At every index, calculate:  
`currentSum - k`  
If that exists in the dictionary, it means there’s a subarray that ends at current index and sums to k.

Update the dictionary with the new prefix sum.

### Performance

- Time Complexity: O(n)
- Space Complexity: O(n) for hashmap

### C# Code with Main() Method

```csharp
using System;
using System.Collections.Generic;

public class Solution {
    public int SubarraySum(int[] nums, int k) {
        Dictionary<int, int> prefixSums = new Dictionary<int, int>();
        prefixSums[0] = 1; // base case: sum 0 seen once

        int sum = 0;
        int count = 0;

        foreach (int num in nums) {
            sum += num;

            if (prefixSums.ContainsKey(sum - k)) {
                count += prefixSums[sum - k];
            }

            if (!prefixSums.ContainsKey(sum)) {
                prefixSums[sum] = 0;
            }
            prefixSums[sum]++;
        }

        return count;
    }

    public static void Main(string[] args) {
        var solution = new Solution();

        int[] nums = { 1, 2, 3 };
        int k = 3;
        int result = solution.SubarraySum(nums, k);
        Console.WriteLine("Total Subarrays with sum " + k + ": " + result);
        // Output: 2
    }
}
```

### Constraints

- 1 <= nums.Length <= 20,000
- -1000 <= nums[i] <= 1000
- -10^7 <= k <= 10^7

### Counter Questions & Answers

Q: Why not use brute force?  
A: Brute force is O(n²), which would time out for large inputs.

Q: Why prefix sum instead of sliding window?  
A: Sliding window doesn’t work when elements can be negative. Prefix sum handles both positive and negative numbers.

Q: What does prefixSums[0] = 1 mean?  
A: It handles cases where a prefix sum directly equals k.

Q: Can this handle very large arrays?  
A: Yes, it runs in O(n) with hashmap, very efficient.

Q: What if we wanted to return the actual subarrays?  
A: Then we’d need to store start indices of prefix sums, which increases complexity.

## 12. Serialize/Deserialize Binary Tree

## 13. Meeting Rooms II (min meeting rooms)

## 14. K Closest Points to Origin

## 15. Insert/Delete/GetRandom O(1)

## 16. 3Sum

## 17. Product of Array Except Self

## 18. Coin Change

## 19. Lowest Common Ancestor

## 20. Minimum Window Substring

## 21. Unique Paths

## 22. Bit Manipulation: Single Number, Subsets

## 23. Partition Labels

## 24. Candy Crush

### Problem Statement

Given a 2D board of characters representing candies, repeatedly:

- Crush groups of 3 or more same candies (either horizontally or vertically).
- After crushing, drop the candies down so that the board collapses.
- Keep doing this until no more candies can be crushed.

Return the final stable board.

### Input / Output Example

**Input:**

```csharp
board = [
  [110,  5, 112, 113, 114],
  [210, 211,  5, 213, 214],
  [310, 311,  3, 313, 314],
  [410, 411, 412,  5, 414],
  [5,    1, 512,  3,   3],
  [610,  4,  1, 613, 614],
  [710,  1,  2, 713, 714],
  [810,  1,  2,   1,   1],
  [1,    1,  2,   2,   2],
  [4,    1,  4,   4, 1014]
]
```

**Output:**

```
[
  [0, 0, 0, 0, 0],
  [0, 0, 0, 0, 0],
  [0, 0, 0, 0, 0],
  [110, 0, 0, 0, 114],
  [210, 0, 0, 0, 214],
  [310, 0, 0, 113, 314],
  [410, 0, 0, 213, 414],
  [610, 211, 112, 313, 614],
  [710, 311, 412, 613, 714],
  [810, 411, 512, 713, 1014]
]
```

### Smart Questions to Ask

- Are candies crushed simultaneously or one group at a time?
- How many directions do we check (horizontal, vertical only)?
- What should we do when multiple crushes affect the same column?
- How to handle gravity? Do we shift elements or recreate arrays?

### Edge Cases

- Entire board is stable from start
- Whole row/column gets crushed
- Chain reactions: crushing leads to more crushing

### Performance Requirements

- Time: Acceptable at O(R × C) per iteration; multiple passes until stable
- Space: Can modify in-place (O(1) space excluding result)

### Pattern Used

- Simulation + Grid Traversal
- Identifying groups, marking them
- Letting gravity collapse columns
- Loop until stable board (no crushes)

### Greedy/Iterative Approach – Explained Simply

1. Traverse the grid to mark candies to crush (using negative values).
2. After one pass, crush them (set to 0).
3. Apply gravity: shift candies down in each column.
4. Repeat until no changes are made (i.e., stable board).

### Constraints

- 3 ≤ board size ≤ 1000 x 1000
- Candies are integers (0 means empty)
- Only vertical & horizontal crushes

### C# Implementation

```csharp
public class Solution
{
    public int[][] CandyCrush(int[][] board)
    {
        int rows = board.Length;
        int cols = board[0].Length;
        bool changed = true;

        while (changed)
        {
            changed = false;

            // Step 1: Mark candies to crush (vertical and horizontal)
            for (int r = 0; r < rows; r++)
            {
                for (int c = 0; c < cols - 2; c++)
                {
                    int val = Math.Abs(board[r][c]);
                    if (val != 0 &&
                        val == Math.Abs(board[r][c + 1]) &&
                        val == Math.Abs(board[r][c + 2]))
                    {
                        board[r][c] = -val;
                        board[r][c + 1] = -val;
                        board[r][c + 2] = -val;
                        changed = true;
                    }
                }
            }

            for (int c = 0; c < cols; c++)
            {
                for (int r = 0; r < rows - 2; r++)
                {
                    int val = Math.Abs(board[r][c]);
                    if (val != 0 &&
                        val == Math.Abs(board[r + 1][c]) &&
                        val == Math.Abs(board[r + 2][c]))
                    {
                        board[r][c] = -val;
                        board[r + 1][c] = -val;
                        board[r + 2][c] = -val;
                        changed = true;
                    }
                }
            }

            // Step 2: Crush (set negative to 0) and apply gravity
            for (int c = 0; c < cols; c++)
            {
                int writeRow = rows - 1;

                // Drop uncrushed candies down
                for (int r = rows - 1; r >= 0; r--)
                {
                    if (board[r][c] > 0)
                    {
                        board[writeRow][c] = board[r][c];
                        writeRow--;
                    }
                }

                // Fill rest with 0 (crushed ones)
                for (int r = writeRow; r >= 0; r--)
                {
                    board[r][c] = 0;
                }
            }
        }

        return board;
    }
}
```

### How to Call it from Main

```csharp
public static void Main()
{
    var sol = new Solution();

    int[][] board = new int[][] {
        new int[] {110,5,112,113,114},
        new int[] {210,211,5,213,214},
        new int[] {310,311,3,313,314},
        new int[] {410,411,412,5,414},
        new int[] {5,1,512,3,3},
        new int[] {610,4,1,613,614},
        new int[] {710,1,2,713,714},
        new int[] {810,1,2,1,1},
        new int[] {1,1,2,2,2},
        new int[] {4,1,4,4,1014}
    };

    var result = sol.CandyCrush(board);

    foreach (var row in result)
    {
        Console.WriteLine(string.Join(", ", row));
    }
}
```

### Counter Questions + Answers

Q: Do we crush one match at a time or all at once?  
A: All matching groups in one round get marked and crushed together.

Q: How do we ensure gravity works after crush?  
A: Traverse bottom to top, moving non-zero values down and filling zeros above.

Q: What if crushing causes new matches?  
A: The loop continues until no new changes occur (board is stable).

---

## 25. Maximum Difference Between Even and Odd Frequency II

## 26. Insert Delete GetRandom O(1) (variant)

## 27. Max Area of Island

### Problem Statement

Given a 2D binary grid representing a map of '0' (water) and '1' (land), return the size of the largest island. An island is a group of connected 1's connected vertically or horizontally.

### Example Input and Output

**Example 1:**

```csharp
Input:
grid = [
  [0,0,1,0,0,0,0],
  [0,0,1,1,1,0,0],
  [0,0,0,1,0,0,0],
  [0,0,0,0,0,0,0]
]
Output: 5
// The biggest island is 5 cells wide (middle top).
```

**Example 2:**

```csharp
Input:
grid = [
  [1, 1],
  [1, 0]
]
Output: 3
```

### Smart Questions to Ask

- Should diagonal neighbors count? No, only vertical & horizontal
- Are all values in the grid 0 or 1? Yes
- Can the grid be empty? Yes, return 0
- Can the island touch the border? Yes

### Edge Cases

- All 0s → Return 0
- All 1s → Return total number of cells
- Multiple small islands → Only the biggest matters
- Single cell grid (1x1)

### Pattern Used

- DFS (Depth-First Search)
- Can also be done using BFS (queue-based)
- Flood Fill technique (similar to coloring connected components)

### Approach (Simple Explanation)

- Traverse the grid
- If you find a 1:
  - Launch DFS to find full island
  - Count size during DFS
  - Track max area seen so far
- Return the largest area found

### Performance

- Time Complexity: O(m × n), where m = rows, n = cols (Each cell visited once)
- Space Complexity: O(m × n) in worst case due to recursion stack (DFS)

### C# Code with Main method

```csharp
using System;

public class Solution {
    public int MaxAreaOfIsland(int[][] grid) {
        int rows = grid.Length;
        if (rows == 0) return 0;
        int cols = grid[0].Length;
        int maxArea = 0;

        for (int r = 0; r < rows; r++) {
            for (int c = 0; c < cols; c++) {
                if (grid[r][c] == 1) {
                    maxArea = Math.Max(maxArea, DFS(grid, r, c));
                }
            }
        }

        return maxArea;
    }

    private int DFS(int[][] grid, int r, int c) {
        int rows = grid.Length;
        int cols = grid[0].Length;

        // Boundary or water
        if (r < 0 || c < 0 || r >= rows || c >= cols || grid[r][c] == 0)
            return 0;

        // Mark as visited
        grid[r][c] = 0;

        int area = 1;
        area += DFS(grid, r + 1, c);
        area += DFS(grid, r - 1, c);
        area += DFS(grid, r, c + 1);
        area += DFS(grid, r, c - 1);

        return area;
    }

    public static void Main(string[] args) {
        var solution = new Solution();
        int[][] grid = new int[][] {
            new int[] {0,0,1,0,0},
            new int[] {0,1,1,1,0},
            new int[] {0,0,1,0,0},
            new int[] {0,0,0,0,0}
        };

        int result = solution.MaxAreaOfIsland(grid);
        Console.WriteLine("Max Area of Island: " + result); // Output: 5
    }
}
```

### Alternate Approach

- BFS Version using a Queue instead of recursion to prevent stack overflow for large grids.
- Can use a separate visited[][] array instead of marking grid as 0.

### Constraints

- m == grid.length
- n == grid[i].length
- 1 <= m, n <= 50
- grid[i][j] is 0 or 1

### Counter Questions & Answers

Q: Why do we mark cells as 0 after visiting?  
A: To avoid revisiting the same land during DFS.

Q: What if we need to preserve the original grid?  
A: Use a separate bool[][] visited array.

Q: Is recursion safe for large grids?  
A: For m, n <= 50, it's safe. Use BFS for larger.

Q: Can we use Union-Find (DSU)?  
A: It's possible but overkill for max area. Better for counting islands.

---

## 28. Best Time to Buy and Sell Stock

### Problem Statement

You are given an array `prices` where `prices[i]` is the price of a given stock on the i-th day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

### Example

```csharp
Input: prices = [7,1,5,3,6,4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.

Input: prices = [7,6,4,3,1]
Output: 0
Explanation: Prices are decreasing, so no profit is possible.
```

### Smart Questions to Ask

- Can I buy and sell on the same day? ➝ No, you must sell after buying.
- Are negative prices possible? ➝ No, prices are all non-negative integers.
- Can the array be empty? ➝ Yes, handle edge cases.
- Do I need to return the actual days or just the profit? ➝ Just return the maximum profit.
- Can prices repeat? ➝ Yes.

### Approach (Simple Explanation)

- Keep track of the lowest price seen so far (best day to buy).
- For each day, calculate potential profit = current price - minPriceSoFar.
- Update maxProfit if this profit is better.
- In the end, return maxProfit.

### C# Code

```csharp
using System;

public class Solution {
    public int MaxProfit(int[] prices) {
        if (prices == null || prices.Length == 0) return 0;

        int minPrice = prices[0];
        int maxProfit = 0;

        for (int i = 1; i < prices.Length; i++) {
            if (prices[i] < minPrice) {
                minPrice = prices[i];
            } else {
                int profit = prices[i] - minPrice;
                maxProfit = Math.Max(maxProfit, profit);
            }
        }

        return maxProfit;
    }
}
```

### Main Method to Run & Test

```csharp
public class Program {
    public static void Main(string[] args) {
        Solution sol = new Solution();

        int[] prices1 = {7, 1, 5, 3, 6, 4};
        Console.WriteLine("Max Profit: " + sol.MaxProfit(prices1)); // Output: 5

        int[] prices2 = {7, 6, 4, 3, 1};
        Console.WriteLine("Max Profit: " + sol.MaxProfit(prices2)); // Output: 0

        int[] prices3 = {2, 4, 1};
        Console.WriteLine("Max Profit: " + sol.MaxProfit(prices3)); // Output: 2
    }
}
```

### Edge Cases

| Case                     | Result     |
| ------------------------ | ---------- |
| Prices always decreasing | 0 profit   |
| Prices all the same      | 0 profit   |
| Empty or null array      | 0          |
| One element only         | 0          |
| Profit on last day only  | Handled ✅ |

### Constraints

```csharp
1 <= prices.Length <= 10^5
0 <= prices[i] <= 10^4
```

### Pattern Used

- Sliding Window (Two Pointers)
- Kadane’s Algorithm Variant

### Performance Requirements

| Metric | Value |
| ------ | ----- |
| Time   | O(n)  |
| Space  | O(1)  |

### Counter Questions & Answers

**Q: Why not check every pair (i, j)?**  
A: That would be O(n²) and inefficient for large inputs.

**Q: What if prices[i] == prices[j]?**  
A: Still valid, but profit = 0.

**Q: Can I sell before I buy?**  
A: No. The problem clearly states to sell after buying.

**Q: What if there's no profit opportunity?**  
A: Return 0 as per the problem.

---

### Best Time to Buy and Sell Stock II (Multiple Transactions Allowed)

You are given an array `prices` where `prices[i]` is the price of a given stock on the i-th day.

You may complete as many transactions as you like (i.e., buy one and sell one share of the stock multiple times). However, you must sell the stock before you buy again.

Return the maximum profit you can achieve.

### Example

```csharp
Input: prices = [7,1,5,3,6,4]
Output: 7
Explanation:
Buy on day 2 (price=1), sell on day 3 (price=5), profit = 4.
Buy on day 4 (price=3), sell on day 5 (price=6), profit = 3.
Total = 4 + 3 = 7

Input: prices = [1,2,3,4,5]
Output: 4
Explanation: Buy on day 1, sell on day 5, profit = 4.

Input: prices = [7,6,4,3,1]
Output: 0
Explanation: No profit can be made.
```

### Smart Questions to Ask

- Can I buy and sell on the same day? → ✅ Yes.
- Can I perform multiple transactions? → ✅ Yes.
- Can I buy while holding a stock? → ❌ No, only one stock at a time.
- What happens if there are no opportunities to make a profit? → Return 0.
- Are negative prices allowed? → ❌ No, prices are always ≥ 0.

### Approach (Simple Explanation)

- If the price is higher than the previous day, you can consider it as a profit opportunity.
- So, just sum up all the `price[i] - price[i-1]` where it's positive.

### Pattern Used

- Greedy (Buy low and sell high — as many times as possible)

### C# Code

```csharp
using System;

public class Solution {
    public int MaxProfit(int[] prices) {
        int profit = 0;

        for (int i = 1; i < prices.Length; i++) {
            if (prices[i] > prices[i - 1]) {
                profit += prices[i] - prices[i - 1];
            }
        }

        return profit;
    }
}
```

### Main Method to Run & Test

```csharp
public class Program {
    public static void Main(string[] args) {
        Solution sol = new Solution();

        int[] prices1 = {7, 1, 5, 3, 6, 4};
        Console.WriteLine("Max Profit: " + sol.MaxProfit(prices1)); // Output: 7

        int[] prices2 = {1, 2, 3, 4, 5};
        Console.WriteLine("Max Profit: " + sol.MaxProfit(prices2)); // Output: 4

        int[] prices3 = {7, 6, 4, 3, 1};
        Console.WriteLine("Max Profit: " + sol.MaxProfit(prices3)); // Output: 0
    }
}
```

### Edge Cases

| Edge Case             | Output                    |
| --------------------- | ------------------------- |
| Empty array           | 0                         |
| One day only          | 0                         |
| All decreasing prices | 0                         |
| Prices stay the same  | 0                         |
| Always increasing     | prices[n-1] - prices[0]   |
| Fluctuating ups/downs | Sum of all positive diffs |

### Constraints

```csharp
1 <= prices.Length <= 10^5
0 <= prices[i] <= 10^4
```

### Performance

| Type  | Complexity |
| ----- | ---------- |
| Time  | O(n)       |
| Space | O(1)       |

### Counter Questions & Answers

**Q: Can I sell before I buy?**  
A: No, you must buy before selling.

**Q: Can I buy and sell on the same day?**  
A: Yes, that's allowed.

**Q: Can I buy after selling?**  
A: Yes, but not while holding a stock.

**Q: Do I need to find the actual transactions?**  
A: No, just return the total profit.

---

## 29. Invalid Transactions

## 30. Design Underground System

## 31. Decode String

## 32. Two City Scheduling

## 33. Remove All Adjacent Duplicates in String II

## 34. Merge Intervals

## 35. Design an Ordered Stream

## 36. Flatten a Multilevel Doubly Linked List

## 37. All Paths From Source to Target

## 38. Two Sum

## 39. Word Search

## 40. Valid Anagram

## 41. Validate Binary Search Tree

## 42. Word Break II

## 43. Design A Leaderboard

# 44. Knapsack problem, and a variant where you have a limit of 3 stones to choose from (which then becomes a 3sum variant)

## 45. A very big sum

## 46. Left Rotation

## 47. Insert a Node at a Position Given in a List

## 48. Cycle Detection

## 49. Balanced Brackets

## 50. Queue Using Two Stacks

## 51. Ice Cream Parlour

## 52. Insertion Sort - Part 1

## 53. Insertion Sort - Part 2

## 54. Binary Tree Insertion

## 55. Height of a Binary Tree

## 56. Breadth First Search

## 57. Snakes and Ladders

## 58. Fibonacci Numbers

---
