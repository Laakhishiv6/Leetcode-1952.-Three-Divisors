# Leetcode-1952.-Three-Divisors
# Description
Given an integer n, return true if n has exactly three positive divisors. Otherwise, return false.

An integer m is a divisor of n if there exists an integer k such that n = k * m.
# Solution
You are given an integer n.
Return True if n has exactly three positive divisors, otherwise return False.

An integer m is called a divisor of n if there exists an integer k such that: n=k×m
Example 1:

Input: n = 2

Output: false

Explantion: 2 has only two divisors: 1 and 2.

Example 2:

Input: n = 4

Output: true

Explantion: 4 has three divisors: 1, 2, and 4.
# Algorithm
1. Create a variable count which tracks the number of divisors .
2. Now loop in the range (1,n+1). Check if n is divisible by ith pointer .
3. If it is then increment the count variable.
4. Check if the count is exactly equal to 3, then only return True .
5. Else return false.
# Code
class Solution:

    def isThree(self, n: int) -> bool:
        count=0
        for i in range(1,n+1):
            if n%i==0:
                count+=1
                if count>3:
                    return False
        return count==3
# Complexity
Time Complexity:

The loop runs from 1 to n in the worst case.

Each iteration performs a modulus operation (n % i), which is O(1).

Therefore, worst-case time complexity is:O(n)

The if count > 3 check can sometimes exit early, but for numbers with few divisors (like primes), it will still run all n iterations.

Space Complexity:

Only a few integer variables (count, i) are used, regardless of n.

Therefore:O(1)
