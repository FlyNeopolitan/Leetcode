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

### Search a 2D Matrix（Leetcode 74)
Description : Write an efficient algorithm that searches for a value in an m x n matrix. This matrix has the following properties:
Integers in each row are sorted from left to right. The first integer of each row is greater than the last integer of the previous row.
Solution :
1. First use binary search finding the row it located in, and then use binary search finding the position of that raw. Time: O(logn+logm) Space:O(1)

### Path Sum II (Leetcode 113)
Description : Given a binary tree and a sum, find all root-to-leaf paths where each path's sum equals the given sum.
Solution :
1. Recursion. Time: O(n) Space:O(n)

### Palindrome Partitioning II (Leetcode 132)
Description : Given a string s, partition s such that every substring of the partition is a palindrome.Return the minimum cuts needed for a palindrome partitioning of s.
Solution :
1. Dp. Let dp[i] represents min cut needed from 0 to i. Now let's focus on the last palindrome containing s[i+1].... Time:O(n^2) Space:O(n)

### Rotate Array (Leetcode 189)
Description : Given an array, rotate the array to the right by k steps, where k is non-negative.
Solution :
1. Rotate array by 1 for k steps. Time:O(n^2) Space:O(1)
2. Rotate array by k for 1 step. Time:O(n) Space:O(k)

### Binary Tree Right Side View (Leetcode 199)
Description : Given a binary tree, imagine yourself standing on the right side of it, return the values of the nodes you can see ordered from top to bottom.
Solution :
1. BFS from right to left. Time:O(n) Space:O(width(Tree))

### Number of Islands (Leetcode 200)
Description : Given an m x n 2d grid map of '1's (land) and '0's (water), return the number of islands.An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.
Solution :
1. Disjoint set. Iterate the matrix, and connect the land with its neighbour land, after which the size of disjoint set equals water pixel plus island num. Time:O(n^2) Space:O(n^2)
2. BFS/DFS. When access a part of land, use DFS or BFS to travese the whole land. (We can mark it to 0 in convenience). Time:O(n^2) Space:O(1)

### Course Schedule (Leetcode 207)
Description : There are a total of numCourses courses you have to take, labeled from 0 to numCourses-1. Some courses may have prerequisites, for example to take course 0 you have to first take course 1, which is expressed as a pair: [0,1] Given the total number of courses and a list of prerequisite pairs, is it possible for you to finish all courses?
Solution :
1. Everytime find the course with no prerequisite, and relex it. Time:O(n^2) Space:O(n^2)

### House Robber II (Leectcode 213)
Description : You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed. All houses at this place are arranged in a circle. That means the first house is the neighbor of the last one. Meanwhile, adjacent houses have a security system connected, and it will automatically contact the police if two adjacent houses were broken into on the same night. Given a list of non-negative integers nums representing the amount of money of each house, return the maximum amount of money you can rob tonight without alerting the police.
Solution :
1. DP. Notice that we can not choose the first one and the last one at the same time, so we use dp1[i] represents max money from (0,i) where i<= size - 2, and use dp2[i] represents max money from (1,i) where i<= size - 1. At last we compare dp1.back() with dp2.back(). For each one, update dp[i] = max{dp[i-1], dp[i-2]+money[i]} Time: O(n) Space:O(n)

### Maximal Square (Leetcode 221)
Description : Given an m x n binary matrix filled with 0's and 1's, find the largest square containing only 1's and return its area.
Solution :
1. DP. Use left[i][j] and up[i][j] represents max 1's sequence on the left and up, and dp[i,j] represents max size whose bottomright locates in (i,j). It's easy to update left and up, after which updates DP[i,j] = min(left[i][j], up[i][j], DP[i-1,j-1]) Time: O(n^2) Space:O(n^2)
2. DP. Use dp[i,j] represents max size whose bottomright locates in (i,j). Update DP[i][j] = min(DP[i-1][j-1], DP[i][j-1], DP[i-1][j]) Time: O(n^2) Space:O(n^2)

### Rectangle Area (Leetcode 223)
Description : Find the total area covered by two rectilinear rectangles in a 2D plane. Each rectangle is defined by its bottom left corner and top right corner as shown in the figure.
Solution :
1. Easy algebra. Time:O(1) Space:O(1)

### Lowest Common Ancestor of a Binary Tree (Leetcode 236)
Description : Given a binary tree, find the lowest common ancestor (LCA) of two given nodes in the tree.
Solution :
1. Find the path of p and q, and then check the last element in common path. Time:O(n) Space:O(n)
2. Recursion. Use right, left and mid to check if two of them are true: right has one of them, left has one of them, current has one of them. Time:O(n) Space:O(n)

### Product of Array Except Self (Leetcode 238)
Description : Given an array nums of n integers where n > 1,  return an array output such that output[i] is equal to the product of all the elements of nums except nums[i].
Solution :
1. DP. left[i] represents product of element left of i, right[i] represents product of element right of i. Time:O(n) Space:O(n)
2. DP. left[i] represents product of element left of i, and just from right to left update left[i] to answer with a int recording product of right elements. Time:O(n) Space:O(n)

### House Robber III (Leetcode 337)
Description : The thief has found himself a new place for his thievery again. There is only one entrance to this area, called the "root." Besides the root, each house has one and only one parent house. After a tour, the smart thief realized that "all houses in this place forms a binary tree". It will automatically contact the police if two directly-linked houses were broken into on the same night. Determine the maximum amount of money the thief can rob tonight without alerting the police.
1. recursion. Time:O(n) Space:O(n)

### Longest Substring with At Least K Repeating Characters (Leetcode 395)
Description : Given a string s and an integer k, return the length of the longest substring of s such that the frequency of each character in this substring is greater than or equal to k.
1. Recursion. If there is a valid element, it will devide the string into left one and right one. If there is not, then current string is legal. Time:O(n^2) Space:O(n)

### Partition Equal Subset Sum (Leetcode 416)
Description : Given a non-empty array nums containing only positive integers, find if the array can be partitioned into two subsets such that the sum of elements in both subsets is equal.
Solution : 
1. Notice that array contains only integers. So we only need to find set whose sum of value is target / 2 (WHICH MUST BE AN INTEGER!). We can use dp to record what we have got. DP[i] represents if i is a sum of somme elements in array. Time:O(n^2) Space:O(n)


