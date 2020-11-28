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
