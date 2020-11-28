# Week1
## 2020.11.22-2020.11.29
## 24 medium 3 hard 2 easy

### Longest Substring Without Repeating Characters(Leetcode 3)
Description : Given a string s, find the length of the longest substring without repeating characters.  
Solution :    
1. navie sliding window (extand right bound of window when the one on the right of window is not in current window, and remove the leftmost element when
the element on the right of window is in the window. We can use a hashset to keep element in the window, which makes it O(1) to check containess.) Time: O(n) Space: O(m, n)  
2. Dp (let dp[i] represents the longest substring without repeating characters ending at i. Thus, DP[i] = DP[i - 1] + 1 - (j - low) where DP[j] is the last element equal to s[i], from low to i - 1. Low is (i - dp[i - 1]), which represents the leftmost index of longest substring ending in i. Thus, if any element in this substring is not equal to s[i], s[i]
is simply s[i-1]+1. It will take O(n) to check containess) Time: O(n^2) Space: O(n)

### Longest Palindromic Substring(Leetcode 5)
Description : Given a string s, return the longest palindromic substring in s.
Solution :
1. Expand Around center. Time: O(n^2) Space:O(1)
2. Dp (The idea is like expanding around center) Time:O(n^2) Space:O(n)

### Next Permutation(Leetcode 31)
Description : Implement next permutation, which rearranges numbers into the lexicographically next greater permutation of numbers.
Solution :
1. Observe, the problem is equivilant to find a pair (i,j) such that s[i] < s[j] and pick the pair which has the rightest i and smallest j. Thus, from leftmost element, we stop at the the first decreasing element, after which go back to find the least element greater than it. Then we swap them, and sort the substring after this index.

### Longest Valid Parentheses(Leetcode 32)
Description : Given a string containing just the characters '(' and ')', find the length of the longest valid (well-formed) parentheses substring.
Solution :
1. Dp. Let dp[i] represents longest valid parentheses substring ending at i. Time:O(n) Space:O(n)

###
