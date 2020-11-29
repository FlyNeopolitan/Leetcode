# Weekly Contest 218, Biweekly Contest 41

## Minimum Moves to Make Array Complementary
Description: You are given an integer array nums of even length n and an integer limit. In one move, you can replace any integer from nums with another integer between 1 and limit, inclusive.
The array nums is complementary if for all indices i (0-indexed), nums[i] + nums[n - 1 - i] equals the same number. For example, the array [1,2,3,4] is complementary because for all indices i, nums[i] + nums[n - 1 - i] = 5.
Return the minimum number of moves required to make nums complementary.

Solution: [Solution by yanruchen](https://leetcode.com/problems/minimum-moves-to-make-array-complementary/discuss/952773/PythonJava-simple-O(max(n-k))-method)  
Highlight: First he works out the cost for each pair to adjust to a sum T. Then he uses a very smart to way to calculate the best T. He doesn't iterate through T. Insead, he uses
a delta array to store the information for changes of operations from i - 1 to i, and use every pair to update this information. Now he knows changes for the whole array, and he could
calculate the best operations with help of delta.

## Find the Most Competitive Subsequence
Description : Given an integer array nums and a positive integer k, return the most competitive subsequence of nums of size k. An array's subsequence is a resulting sequence obtained by erasing some (possibly zero) elements from the array.
We define that a subsequence a is more competitive than a subsequence b (of the same length) if in the first position where a and b differ, subsequence a has a number less than the corresponding number in b. 
For example, [1,3,4] is more competitive than [1,3,5] because the first position they differ is at the final number, and 4 is less than 5.  

Solution: [Solution by Alvin](https://leetcode.com/problems/find-the-most-competitive-subsequence/discuss/952934/C%2B%2B-O(n)-sliding-window-mono-queue)  
Highlight: he uses a deque to keep track of candidates.  
My solution is recursive and is O(n^2) in worst case. 

## Minimize Deviation in Array
Description : You are given an array nums of n positive integers.You can perform two types of operations on any element of the array any number of times:
If the element is even, divide it by 2. For example, if the array is [1,2,3,4], then you can do this operation on the last element, and the array will be [1,2,3,2]. If the element is odd, multiply it by 2.
For example, if the array is [1,2,3,4], then you can do this operation on the first element, and the array will be [2,2,3,4].  
The deviation of the array is the maximum difference between any two elements in the array.  
Return the minimum deviation the array can have after performing some number of operations.  

Solution: [Solution by yuezioli](https://leetcode.com/problems/minimize-deviation-in-array/discuss/952990/Mathematical-solution-reduced-complexity)

## Minimum Number of Removals to Make Mountain Array
Description : You may recall that an array arr is a mountain array if and only if: arr.length >= 3; There exists some index i (0-indexed) with 0 < i < arr.length - 1 such that:
arr[0] < arr[1] < ... < arr[i - 1] < arr[i], arr[i] > arr[i + 1] > ... > arr[arr.length - 1].  
Given an integer array nums, return the minimum number of elements to remove to make nums a mountain array.  

Solution: DP. Use right and left to keep track of max increasing/decreasing subsequence on the right and left of i, and then for each i as top, we could get max length of mountain, which
tells us the removal we need.  
Highlight: Convert the problem into a max increasing/decreasing subsequence problem, and it's easy to use DP to solve it.  
