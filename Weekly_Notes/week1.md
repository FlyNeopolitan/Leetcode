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

### Search in Rotated Sorted Array(Leetcode 33)
Description : You are given an integer array nums sorted in ascending order, and an integer target. Suppose that nums is rotated at some pivot unknown to you beforehand (i.e., [0,1,2,4,5,6,7] might become [4,5,6,7,0,1,2]).
Solution :
1. Use binary search find the pivot, and then use binary search find the target. Time:O(logn) Space:O(1)

### Wildcard Matching(Leetcode 44)
Description : Given an input string (s) and a pattern (p), implement wildcard pattern matching with support for '?' and '*' where:'?' Matches any single character.'*' Matches any sequence of characters (including the empty sequence). The matching should cover the entire input string (not partial).
Solution :
1. Dp. Let dp[i][j] represents if (0,i) in p could match (0,j) in s. Time:O(nm) Space:O(nm)

### Rotate Image（Leetcode 48)
Description : You are given an n x n 2D matrix representing an image, rotate the image by 90 degrees (clockwise). You have to rotate the image in-place, which means you have to modify the input 2D matrix directly. DO NOT allocate another 2D matrix and do the rotation.
Solution :
1. Observe. Reverse every line. And everytime just swap the row and colomn from (i,0) to (x, n - 1 - x), from (x, n) to (x, n - 1 - x) (0 <= x <= n - 1) Time:O(n^2) Space:O(1)

### Unique Paths (Leetcode 62)
Description : A robot is located at the top-left corner of a m x n grid (marked 'Start' in the diagram below).The robot can only move either down or right at any point in time. The robot is trying to reach the bottom-right corner of the grid (marked 'Finish' in the diagram below).
How many possible unique paths are there?
Solution :
1. Dp. Let DP[i][j] represents path from start to (i,j). Time:O(mn) Space:O(mn)

###  Search a 2D Matrix（Leetcode 74)
Description : Write an efficient algorithm that searches for a value in an m x n matrix. This matrix has the following properties:
Integers in each row are sorted from left to right. The first integer of each row is greater than the last integer of the previous row.
Solution :
1. First use binary search finding the row it located in, and then use binary search finding the position of that raw. Time: O(logn+logm) Space:O(1)

###

 
