# Online Assessment Test preparation

This document contains 40 coding problems with comprehensive solutions in Java and Python.

## STRING PROBLEMS

### 1. Reverse a string without built-in functions
**Problem:** Reverse a given string without using built-in reverse functions.
*Example:* Input: "hello", Output: "olleh"
**Approach:** Iterate from the end of the string to the beginning and build a new string/array, or swap elements from ends to middle.
```java
public class StringReverser {
    public static String reverse(String s) {
        if (s == null) return null;
        char[] arr = s.toCharArray();
        int left = 0, right = arr.length - 1;
        while (left < right) {
            char temp = arr[left];
            arr[left++] = arr[right];
            arr[right--] = temp;
        }
        return new String(arr);
    }
}
```
```python
def reverse_string(s: str) -> str:
    if s is None: return None
    # Convert string to list of characters as strings are immutable in Python
    chars = list(s)
    left, right = 0, len(chars) - 1
    while left < right:
        chars[left], chars[right] = chars[right], chars[left]
        left += 1
        right -= 1
    return "".join(chars)
```
**Complexity:** Time: O(N), Space: O(N) where N is string length.
**Edge Cases:** Null string, empty string, 1-character string.

### 2. Check if a string is a palindrome
**Problem:** Check if a string reads the same forward and backward.
*Example:* Input: "racecar", Output: true
**Approach:** Use two pointers, one at the start and one at the end, and compare characters while moving towards the center.
```java
public class PalindromeChecker {
    public static boolean isPalindrome(String s) {
        if (s == null) return false;
        int left = 0, right = s.length() - 1;
        while (left < right) {
            if (s.charAt(left++) != s.charAt(right--)) {
                return false;
            }
        }
        return true;
    }
}
```
```python
def is_palindrome(s: str) -> bool:
    if s is None: return False
    left, right = 0, len(s) - 1
    while left < right:
        if s[left] != s[right]:
            return False
        left += 1
        right -= 1
    return True
```
**Complexity:** Time: O(N), Space: O(1)
**Edge Cases:** Null string, empty string (should be true), case sensitivity (if required to ignore, convert to lowercase first).

### 3. Find frequency of each character in a string
**Problem:** Count occurrences of each character.
*Example:* Input: "aab", Output: a:2, b:1
**Approach:** Use a HashMap or an array (if ASCII) to store character counts.
```java
import java.util.HashMap;
import java.util.Map;

public class CharFrequency {
    public static Map<Character, Integer> getFrequencies(String s) {
        Map<Character, Integer> freq = new HashMap<>();
        if (s == null) return freq;
        for (char c : s.toCharArray()) {
            freq.put(c, freq.getOrDefault(c, 0) + 1);
        }
        return freq;
    }
}
```
```python
def get_frequencies(s: str) -> dict:
    if not s: return {}
    freq = {}
    for char in s:
        freq[char] = freq.get(char, 0) + 1
    return freq
```
**Complexity:** Time: O(N), Space: O(K) where K is number of unique characters.
**Edge Cases:** Empty string, string with special characters.

### 4. Check if two strings are anagrams
**Problem:** Check if two strings contain the same characters in any order.
*Example:* Input: "listen", "silent", Output: true
**Approach:** Count character frequencies of first string and decrement for second. If all counts are 0, they are anagrams. Or sort and compare (slower).
```java
public class AnagramChecker {
    public static boolean isAnagram(String s1, String s2) {
        if (s1 == null || s2 == null || s1.length() != s2.length()) return false;
        int[] counts = new int[256];
        for (int i = 0; i < s1.length(); i++) {
            counts[s1.charAt(i)]++;
            counts[s2.charAt(i)]--;
        }
        for (int count : counts) {
            if (count != 0) return false;
        }
        return true;
    }
}
```
```python
def is_anagram(s1: str, s2: str) -> bool:
    if s1 is None or s2 is None or len(s1) != len(s2):
        return False
    counts = {}
    for c1, c2 in zip(s1, s2):
        counts[c1] = counts.get(c1, 0) + 1
        counts[c2] = counts.get(c2, 0) - 1
    return all(count == 0 for count in counts.values())
```
**Complexity:** Time: O(N), Space: O(1) assuming fixed character set.
**Edge Cases:** Different lengths, nulls, different cases.

### 5. Find the first non-repeating character in a string
**Problem:** Return the first character that appears only once.
*Example:* Input: "leetcode", Output: "l"
**Approach:** Two passes: count frequencies, then find the first character with count 1.
```java
import java.util.HashMap;

public class FirstUniqueChar {
    public static Character firstNonRepeating(String s) {
        if (s == null || s.isEmpty()) return null;
        HashMap<Character, Integer> counts = new HashMap<>();
        for (char c : s.toCharArray()) {
            counts.put(c, counts.getOrDefault(c, 0) + 1);
        }
        for (char c : s.toCharArray()) {
            if (counts.get(c) == 1) return c;
        }
        return null;
    }
}
```
```python
def first_non_repeating(s: str) -> str:
    if not s: return None
    counts = {}
    for char in s:
        counts[char] = counts.get(char, 0) + 1
    for char in s:
        if counts[char] == 1:
            return char
    return None
```
**Complexity:** Time: O(N), Space: O(K) where K is unique chars.
**Edge Cases:** All repeating chars, empty string.

### 6. Valid Parentheses {[()]}
**Problem:** Check if a string with brackets is valid.
*Example:* Input: "{[()]}", Output: true
**Approach:** Use a stack. Push opening brackets, pop and check matching closing brackets.
```java
import java.util.Stack;

public class ValidParentheses {
    public static boolean isValid(String s) {
        Stack<Character> stack = new Stack<>();
        for (char c : s.toCharArray()) {
            if (c == '(' || c == '{' || c == '[') {
                stack.push(c);
            } else {
                if (stack.isEmpty()) return false;
                char top = stack.pop();
                if ((c == ')' && top != '(') ||
                    (c == '}' && top != '{') ||
                    (c == ']' && top != '[')) return false;
            }
        }
        return stack.isEmpty();
    }
}
```
```python
def is_valid(s: str) -> bool:
    stack = []
    mapping = {')': '(', '}': '{', ']': '['}
    for char in s:
        if char in mapping:
            top = stack.pop() if stack else '#'
            if mapping[char] != top:
                return False
        else:
            stack.append(char)
    return not stack
```
**Complexity:** Time: O(N), Space: O(N)
**Edge Cases:** Only closing brackets, only opening brackets, mixed valid and invalid.

### 7. Roman numeral to Integer conversion
**Problem:** Convert a Roman numeral string to an integer.
*Example:* Input: "IX", Output: 9
**Approach:** Traverse right to left. If current char value < previous char value, subtract it; else add it.
```java
import java.util.HashMap;
import java.util.Map;

public class RomanToInteger {
    public static int romanToInt(String s) {
        Map<Character, Integer> map = new HashMap<>();
        map.put('I', 1); map.put('V', 5); map.put('X', 10);
        map.put('L', 50); map.put('C', 100); map.put('D', 500); map.put('M', 1000);
        
        int result = 0, prev = 0;
        for (int i = s.length() - 1; i >= 0; i--) {
            int current = map.get(s.charAt(i));
            if (current < prev) result -= current;
            else result += current;
            prev = current;
        }
        return result;
    }
}
```
```python
def roman_to_int(s: str) -> int:
    roman_map = {'I': 1, 'V': 5, 'X': 10, 'L': 50, 'C': 100, 'D': 500, 'M': 1000}
    result = 0
    prev = 0
    for char in reversed(s):
        curr = roman_map[char]
        if curr < prev:
            result -= curr
        else:
            result += curr
        prev = curr
    return result
```
**Complexity:** Time: O(N), Space: O(1)
**Edge Cases:** Invalid characters (assume valid input based on typical constraints).

### 8. Longest substring without repeating characters
**Problem:** Find the length of the longest substring without repeating characters.
*Example:* Input: "abcabcbb", Output: 3 ("abc")
**Approach:** Sliding window using a HashMap or HashSet to keep track of characters in current window.
```java
import java.util.HashSet;

public class LongestSubstring {
    public static int lengthOfLongestSubstring(String s) {
        int max = 0, left = 0, right = 0;
        HashSet<Character> set = new HashSet<>();
        while (right < s.length()) {
            if (!set.contains(s.charAt(right))) {
                set.add(s.charAt(right++));
                max = Math.max(max, set.size());
            } else {
                set.remove(s.charAt(left++));
            }
        }
        return max;
    }
}
```
```python
def length_of_longest_substring(s: str) -> int:
    char_set = set()
    left = right = max_len = 0
    while right < len(s):
        if s[right] not in char_set:
            char_set.add(s[right])
            right += 1
            max_len = max(max_len, right - left)
        else:
            char_set.remove(s[left])
            left += 1
    return max_len
```
**Complexity:** Time: O(N), Space: O(min(N, M)) where M is charset size.
**Edge Cases:** Empty string, all same characters.

### 9. String compression
**Problem:** Compress string using counts of repeated chars.
*Example:* Input: "aabcccccaaa", Output: "a2b1c5a3"
**Approach:** Iterate and count consecutive characters. Build string. Return original if compressed is not smaller.
```java
public class StringCompression {
    public static String compress(String s) {
        if (s == null || s.isEmpty()) return s;
        StringBuilder compressed = new StringBuilder();
        int countConsecutive = 0;
        for (int i = 0; i < s.length(); i++) {
            countConsecutive++;
            if (i + 1 >= s.length() || s.charAt(i) != s.charAt(i + 1)) {
                compressed.append(s.charAt(i)).append(countConsecutive);
                countConsecutive = 0;
            }
        }
        return compressed.length() < s.length() ? compressed.toString() : s;
    }
}
```
```python
def compress_string(s: str) -> str:
    if not s: return s
    compressed = []
    count = 0
    for i in range(len(s)):
        count += 1
        if i + 1 >= len(s) or s[i] != s[i+1]:
            compressed.append(f"{s[i]}{count}")
            count = 0
    res = "".join(compressed)
    return res if len(res) < len(s) else s
```
**Complexity:** Time: O(N), Space: O(N)
**Edge Cases:** Compressed string longer than original (e.g., "abc" -> "a1b1c1").

### 10. Check if string is a pangram
**Problem:** Check if string contains every letter of English alphabet.
*Example:* Input: "The quick brown fox jumps over the lazy dog", Output: true
**Approach:** Use a set or boolean array of size 26.
```java
import java.util.HashSet;

public class PangramChecker {
    public static boolean isPangram(String s) {
        if (s == null || s.length() < 26) return false;
        HashSet<Character> set = new HashSet<>();
        for (char c : s.toLowerCase().toCharArray()) {
            if (Character.isLetter(c)) set.add(c);
        }
        return set.size() == 26;
    }
}
```
```python
def is_pangram(s: str) -> bool:
    if not s or len(s) < 26: return False
    letters = set()
    for char in s.lower():
        if char.isalpha():
            letters.add(char)
    return len(letters) == 26
```
**Complexity:** Time: O(N), Space: O(1) (max 26 letters in set)
**Edge Cases:** Missing one letter, string shorter than 26, string with punctuation.

## ARRAY PROBLEMS

### 1. Find the second largest element in an array
**Problem:** Find the 2nd largest distinct element.
*Example:* Input: [10, 5, 20, 20], Output: 10
**Approach:** Single pass keeping track of largest and second largest.
```java
public class SecondLargest {
    public static Integer findSecondLargest(int[] arr) {
        if (arr == null || arr.length < 2) return null;
        int largest = Integer.MIN_VALUE, second = Integer.MIN_VALUE;
        for (int num : arr) {
            if (num > largest) {
                second = largest;
                largest = num;
            } else if (num > second && num != largest) {
                second = num;
            }
        }
        return second == Integer.MIN_VALUE ? null : second;
    }
}
```
```python
def find_second_largest(arr: list[int]) -> int:
    if not arr or len(arr) < 2: return None
    largest = second = float('-inf')
    for num in arr:
        if num > largest:
            second = largest
            largest = num
        elif num > second and num != largest:
            second = num
    return second if second != float('-inf') else None
```
**Complexity:** Time: O(N), Space: O(1)
**Edge Cases:** All elements same, array length < 2.

### 2. Move all zeros to end of array
**Problem:** Move 0s to end while maintaining relative order of non-zeros.
*Example:* Input: [0,1,0,3,12], Output: [1,3,12,0,0]
**Approach:** Two pointers, one for iterating, one for next non-zero position.
```java
public class MoveZeros {
    public static void moveZeroes(int[] nums) {
        int nonZeroIdx = 0;
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] != 0) {
                int temp = nums[nonZeroIdx];
                nums[nonZeroIdx++] = nums[i];
                nums[i] = temp;
            }
        }
    }
}
```
```python
def move_zeroes(nums: list[int]) -> None:
    non_zero_idx = 0
    for i in range(len(nums)):
        if nums[i] != 0:
            nums[non_zero_idx], nums[i] = nums[i], nums[non_zero_idx]
            non_zero_idx += 1
```
**Complexity:** Time: O(N), Space: O(1)
**Edge Cases:** All zeros, no zeros.

### 3. Find missing number in 1..N
**Problem:** Array of size N-1 containing numbers from 1 to N, find the missing one.
*Example:* Input: [1, 2, 4, 5, 6], Output: 3
**Approach:** Math sum formula (N*(N+1)/2) - current sum.
```java
public class MissingNumber {
    public static int findMissing(int[] nums, int n) {
        int expectedSum = n * (n + 1) / 2;
        int actualSum = 0;
        for (int num : nums) actualSum += num;
        return expectedSum - actualSum;
    }
}
```
```python
def find_missing(nums: list[int], n: int) -> int:
    expected_sum = n * (n + 1) // 2
    return expected_sum - sum(nums)
```
**Complexity:** Time: O(N), Space: O(1)
**Edge Cases:** Missing first or last number. Potential integer overflow for large N.

### 4. Remove duplicates from sorted array
**Problem:** Remove duplicates in-place, return new length.
*Example:* Input: [1,1,2], Output: 2, array is [1,2,_]
**Approach:** Two pointers, read and write.
```java
public class RemoveDuplicates {
    public static int removeDuplicates(int[] nums) {
        if (nums.length == 0) return 0;
        int writeIdx = 1;
        for (int i = 1; i < nums.length; i++) {
            if (nums[i] != nums[i - 1]) {
                nums[writeIdx++] = nums[i];
            }
        }
        return writeIdx;
    }
}
```
```python
def remove_duplicates(nums: list[int]) -> int:
    if not nums: return 0
    write_idx = 1
    for i in range(1, len(nums)):
        if nums[i] != nums[i-1]:
            nums[write_idx] = nums[i]
            write_idx += 1
    return write_idx
```
**Complexity:** Time: O(N), Space: O(1)
**Edge Cases:** Empty array, all duplicates, no duplicates.

### 5. Rotate array by K positions
**Problem:** Right rotate array by k steps.
*Example:* Input: [1,2,3,4,5], k=2, Output: [4,5,1,2,3]
**Approach:** Reverse full array, reverse first K, reverse remaining.
```java
public class RotateArray {
    public static void rotate(int[] nums, int k) {
        k %= nums.length;
        reverse(nums, 0, nums.length - 1);
        reverse(nums, 0, k - 1);
        reverse(nums, k, nums.length - 1);
    }
    
    private static void reverse(int[] nums, int start, int end) {
        while (start < end) {
            int temp = nums[start];
            nums[start++] = nums[end];
            nums[end--] = temp;
        }
    }
}
```
```python
def rotate_array(nums: list[int], k: int) -> None:
    k %= len(nums)
    def reverse(start, end):
        while start < end:
            nums[start], nums[end] = nums[end], nums[start]
            start += 1; end -= 1
            
    reverse(0, len(nums) - 1)
    reverse(0, k - 1)
    reverse(k, len(nums) - 1)
```
**Complexity:** Time: O(N), Space: O(1)
**Edge Cases:** k > length, k = 0, length = 1.

### 6. Two Sum - find pair that adds to target
**Problem:** Find indices of two numbers that add up to target.
*Example:* Input: [2,7,11,15], target=9, Output: [0,1]
**Approach:** HashMap to store value and index.
```java
import java.util.HashMap;

public class TwoSum {
    public static int[] twoSum(int[] nums, int target) {
        HashMap<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];
            if (map.containsKey(complement)) {
                return new int[]{map.get(complement), i};
            }
            map.put(nums[i], i);
        }
        return new int[]{};
    }
}
```
```python
def two_sum(nums: list[int], target: int) -> list[int]:
    num_map = {}
    for i, num in enumerate(nums):
        complement = target - num
        if complement in num_map:
            return [num_map[complement], i]
        num_map[num] = i
    return []
```
**Complexity:** Time: O(N), Space: O(N)
**Edge Cases:** No valid pair, negative numbers, multiple identical numbers.

### 7. Check if array is a Mountain Array
**Problem:** Array increases to a peak then decreases. Length >= 3.
*Example:* Input: [0,3,2,1], Output: true
**Approach:** Walk up the mountain, check if peak is valid, then walk down.
```java
public class MountainArray {
    public static boolean validMountainArray(int[] arr) {
        int n = arr.length, i = 0;
        while (i + 1 < n && arr[i] < arr[i + 1]) i++;
        if (i == 0 || i == n - 1) return false;
        while (i + 1 < n && arr[i] > arr[i + 1]) i++;
        return i == n - 1;
    }
}
```
```python
def valid_mountain_array(arr: list[int]) -> bool:
    n, i = len(arr), 0
    while i + 1 < n and arr[i] < arr[i+1]:
        i += 1
    if i == 0 or i == n - 1:
        return False
    while i + 1 < n and arr[i] > arr[i+1]:
        i += 1
    return i == n - 1
```
**Complexity:** Time: O(N), Space: O(1)
**Edge Cases:** Strictly increasing or decreasing, adjacent duplicates (plateaus).

### 8. Find the majority element
**Problem:** Element that appears > n/2 times.
*Example:* Input: [2,2,1,1,1,2,2], Output: 2
**Approach:** Boyer-Moore Voting Algorithm.
```java
public class MajorityElement {
    public static int majorityElement(int[] nums) {
        int count = 0, candidate = 0;
        for (int num : nums) {
            if (count == 0) candidate = num;
            count += (num == candidate) ? 1 : -1;
        }
        return candidate;
    }
}
```
```python
def majority_element(nums: list[int]) -> int:
    count = candidate = 0
    for num in nums:
        if count == 0:
            candidate = num
        count += 1 if num == candidate else -1
    return candidate
```
**Complexity:** Time: O(N), Space: O(1)
**Edge Cases:** Array of length 1. (Assume majority element always exists as per typical problem statement).

### 9. Merge two sorted arrays
**Problem:** Merge nums2 into nums1 (which has enough space at end).
*Example:* nums1=[1,2,3,0,0,0], nums2=[2,5,6], Output: nums1=[1,2,2,3,5,6]
**Approach:** Three pointers starting from the back.
```java
public class MergeSorted {
    public static void merge(int[] nums1, int m, int[] nums2, int n) {
        int p1 = m - 1, p2 = n - 1, p = m + n - 1;
        while (p2 >= 0) {
            if (p1 >= 0 && nums1[p1] > nums2[p2]) {
                nums1[p--] = nums1[p1--];
            } else {
                nums1[p--] = nums2[p2--];
            }
        }
    }
}
```
```python
def merge_sorted(nums1: list[int], m: int, nums2: list[int], n: int) -> None:
    p1, p2, p = m - 1, n - 1, m + n - 1
    while p2 >= 0:
        if p1 >= 0 and nums1[p1] > nums2[p2]:
            nums1[p] = nums1[p1]
            p1 -= 1
        else:
            nums1[p] = nums2[p2]
            p2 -= 1
        p -= 1
```
**Complexity:** Time: O(M+N), Space: O(1)
**Edge Cases:** One array empty.

### 10. Maximum subarray sum (Kadane's algorithm)
**Problem:** Find contiguous subarray with largest sum.
*Example:* Input: [-2,1,-3,4,-1,2,1,-5,4], Output: 6 ([4,-1,2,1])
**Approach:** Track current contiguous sum and global max sum.
```java
public class MaxSubarray {
    public static int maxSubArray(int[] nums) {
        int maxSum = nums[0];
        int currentSum = nums[0];
        for (int i = 1; i < nums.length; i++) {
            currentSum = Math.max(nums[i], currentSum + nums[i]);
            maxSum = Math.max(maxSum, currentSum);
        }
        return maxSum;
    }
}
```
```python
def max_sub_array(nums: list[int]) -> int:
    max_sum = current_sum = nums[0]
    for num in nums[1:]:
        current_sum = max(num, current_sum + num)
        max_sum = max(max_sum, current_sum)
    return max_sum
```
**Complexity:** Time: O(N), Space: O(1)
**Edge Cases:** All negative numbers (should return smallest negative).

## LOGIC / MATH PROBLEMS

### 1. Swap two numbers without temp variable
**Approach:** Use addition/subtraction or XOR.
```java
public class SwapNumbers {
    public static void swap(int[] arr) {
        // arr[0] = a, arr[1] = b
        arr[0] = arr[0] ^ arr[1];
        arr[1] = arr[0] ^ arr[1]; // gives original a
        arr[0] = arr[0] ^ arr[1]; // gives original b
    }
}
```
```python
def swap(a: int, b: int) -> tuple:
    # Python natively supports swapping without temp!
    # a, b = b, a
    # XOR approach:
    a = a ^ b
    b = a ^ b
    a = a ^ b
    return a, b
```
**Complexity:** Time: O(1), Space: O(1)

### 2. Check if a number is a power of 3
**Approach:** Iterative division by 3 or math approach (max power of 3 integer % n == 0).
```java
public class PowerOfThree {
    public static boolean isPowerOfThree(int n) {
        if (n <= 0) return false;
        while (n % 3 == 0) n /= 3;
        return n == 1;
    }
}
```
```python
def is_power_of_three(n: int) -> bool:
    if n <= 0: return False
    while n % 3 == 0:
        n //= 3
    return n == 1
```
**Complexity:** Time: O(log3(N)), Space: O(1)

### 3. Factorial of a number (iterative + recursive)
```java
public class Factorial {
    public static int factIterative(int n) {
        int res = 1;
        for (int i = 2; i <= n; i++) res *= i;
        return res;
    }
    public static int factRecursive(int n) {
        if (n <= 1) return 1;
        return n * factRecursive(n - 1);
    }
}
```
```python
def fact_iterative(n: int) -> int:
    res = 1
    for i in range(2, n + 1):
        res *= i
    return res

def fact_recursive(n: int) -> int:
    return 1 if n <= 1 else n * fact_recursive(n - 1)
```
**Complexity:** Time: O(N), Space: O(1) for iterative, O(N) for recursive.

### 4. Fibonacci series
```java
public class Fibonacci {
    public static int fibIterative(int n) {
        if (n <= 1) return n;
        int a = 0, b = 1;
        for (int i = 2; i <= n; i++) {
            int temp = a + b;
            a = b; b = temp;
        }
        return b;
    }
}
```
```python
def fib_memo(n: int, memo=None) -> int:
    if memo is None: memo = {}
    if n <= 1: return n
    if n not in memo:
        memo[n] = fib_memo(n-1, memo) + fib_memo(n-2, memo)
    return memo[n]
```
**Complexity:** Time: O(N) for iterative/memoized, Space: O(1) iterative, O(N) memoized.

### 5. Check if number is prime
```java
public class PrimeCheck {
    public static boolean isPrime(int n) {
        if (n <= 1) return false;
        for (int i = 2; i * i <= n; i++) {
            if (n % i == 0) return false;
        }
        return true;
    }
}
```
```python
def is_prime(n: int) -> bool:
    if n <= 1: return False
    i = 2
    while i * i <= n:
        if n % i == 0: return False
        i += 1
    return True
```
**Complexity:** Time: O(sqrt(N)), Space: O(1)

### 6. GCD/HCF of two numbers
**Approach:** Euclidean Algorithm.
```java
public class GCD {
    public static int gcd(int a, int b) {
        if (b == 0) return a;
        return gcd(b, a % b);
    }
}
```
```python
def gcd(a: int, b: int) -> int:
    while b:
        a, b = b, a % b
    return a
```
**Complexity:** Time: O(log(min(a,b))), Space: O(1) iterative, O(log(min(a,b))) recursive.

### 7. Reverse an integer
**Approach:** Modulo 10 and multiply by 10. Check for overflow.
```java
public class ReverseInteger {
    public static int reverse(int x) {
        int rev = 0;
        while (x != 0) {
            int pop = x % 10;
            x /= 10;
            if (rev > Integer.MAX_VALUE/10 || (rev == Integer.MAX_VALUE / 10 && pop > 7)) return 0;
            if (rev < Integer.MIN_VALUE/10 || (rev == Integer.MIN_VALUE / 10 && pop < -8)) return 0;
            rev = rev * 10 + pop;
        }
        return rev;
    }
}
```
```python
def reverse_int(x: int) -> int:
    sign = -1 if x < 0 else 1
    x = abs(x)
    rev = 0
    while x != 0:
        rev = rev * 10 + x % 10
        x //= 10
    rev *= sign
    if rev < -2**31 or rev > 2**31 - 1:
        return 0
    return rev
```

### 8. Check if number is an Armstrong number
**Approach:** Sum of cubes of digits equals original number (assuming 3-digit number).
```java
public class Armstrong {
    public static boolean isArmstrong(int n) {
        int temp = n, sum = 0, digits = String.valueOf(n).length();
        while (temp != 0) {
            int digit = temp % 10;
            sum += Math.pow(digit, digits);
            temp /= 10;
        }
        return sum == n;
    }
}
```
```python
def is_armstrong(n: int) -> bool:
    s = str(n)
    power = len(s)
    return sum(int(digit) ** power for digit in s) == n
```

### 9. Count digits in a number
```java
public class CountDigits {
    public static int count(int n) {
        if (n == 0) return 1;
        return (int) Math.floor(Math.log10(Math.abs(n))) + 1;
    }
}
```
```python
def count_digits(n: int) -> int:
    if n == 0: return 1
    import math
    return math.floor(math.log10(abs(n))) + 1
```

### 10. Print star pattern (pyramid)
```java
public class Pyramid {
    public static void print(int n) {
        for(int i = 1; i <= n; i++) {
            for(int j = i; j < n; j++) System.out.print(" ");
            for(int j = 1; j <= (2 * i - 1); j++) System.out.print("*");
            System.out.println();
        }
    }
}
```
```python
def print_pyramid(n: int):
    for i in range(1, n + 1):
        print(" " * (n - i) + "*" * (2 * i - 1))
```

## DATA STRUCTURE PROBLEMS

### 1. Balanced parentheses using Stack
(Covered in Strings #6 Valid Parentheses)

### 2. Next Greater Element using Stack
**Approach:** Monotonic stack tracking elements for which we haven't found a greater element.
```java
import java.util.Stack;

public class NextGreater {
    public static int[] nextGreaterElements(int[] nums) {
        int[] res = new int[nums.length];
        Stack<Integer> stack = new Stack<>();
        for (int i = nums.length - 1; i >= 0; i--) {
            while (!stack.isEmpty() && stack.peek() <= nums[i]) {
                stack.pop();
            }
            res[i] = stack.isEmpty() ? -1 : stack.peek();
            stack.push(nums[i]);
        }
        return res;
    }
}
```
```python
def next_greater_elements(nums: list[int]) -> list[int]:
    res = [-1] * len(nums)
    stack = []
    for i in range(len(nums) - 1, -1, -1):
        while stack and stack[-1] <= nums[i]:
            stack.pop()
        if stack:
            res[i] = stack[-1]
        stack.append(nums[i])
    return res
```

### 3. Delete a node in Linked List without head pointer
**Approach:** Copy next node's value to current node, skip next node.
```java
public class DeleteNode {
    // class ListNode { int val; ListNode next; }
    public void deleteNode(ListNode node) {
        node.val = node.next.val;
        node.next = node.next.next;
    }
}
```
```python
def delete_node(node):
    node.val = node.next.val
    node.next = node.next.next
```

### 4. HashMap-based frequency counting
(Covered in Strings #3)

### 5. Implement a basic Queue using two Stacks
**Approach:** Stack1 for enqueuing. Stack2 for dequeuing. Move elements from S1 to S2 only when S2 is empty.
```java
import java.util.Stack;

class MyQueue {
    Stack<Integer> s1 = new Stack<>();
    Stack<Integer> s2 = new Stack<>();
    
    public void push(int x) {
        s1.push(x);
    }
    
    public int pop() {
        peek();
        return s2.pop();
    }
    
    public int peek() {
        if (s2.isEmpty()) {
            while (!s1.isEmpty()) s2.push(s1.pop());
        }
        return s2.peek();
    }
    
    public boolean empty() {
        return s1.isEmpty() && s2.isEmpty();
    }
}
```
```python
class MyQueue:
    def __init__(self):
        self.s1 = []
        self.s2 = []
        
    def push(self, x: int) -> None:
        self.s1.append(x)
        
    def pop(self) -> int:
        self.peek()
        return self.s2.pop()
        
    def peek(self) -> int:
        if not self.s2:
            while self.s1:
                self.s2.append(self.s1.pop())
        return self.s2[-1]
        
    def empty(self) -> bool:
        return not self.s1 and not self.s2
```

### 6. Find middle element of Linked List in one pass
**Approach:** Slow and Fast pointers.
```java
public class MiddleNode {
    public ListNode middleNode(ListNode head) {
        ListNode slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        return slow;
    }
}
```
```python
def middle_node(head):
    slow = fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
    return slow
```

### 7. Detect cycle in a Linked List (Floyd's algorithm)
**Approach:** Fast pointer moves 2 steps, slow pointer moves 1 step. If they meet, there's a cycle.
```java
public class DetectCycle {
    public boolean hasCycle(ListNode head) {
        ListNode slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) return true;
        }
        return false;
    }
}
```
```python
def has_cycle(head) -> bool:
    slow = fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast:
            return True
    return False
```

### 8. Reverse a Linked List
**Approach:** Maintain prev, curr, next pointers.
```java
public class ReverseLinkedList {
    public ListNode reverseList(ListNode head) {
        ListNode prev = null, curr = head;
        while (curr != null) {
            ListNode nextTemp = curr.next;
            curr.next = prev;
            prev = curr;
            curr = nextTemp;
        }
        return prev;
    }
}
```
```python
def reverse_list(head):
    prev, curr = None, head
    while curr:
        next_temp = curr.next
        curr.next = prev
        prev = curr
        curr = next_temp
    return prev
```

### 9. Implement LRU Cache basic concept
**Approach:** Hash map for O(1) access + Doubly linked list for O(1) evictions.
```java
import java.util.LinkedHashMap;
import java.util.Map;

class LRUCache extends LinkedHashMap<Integer, Integer> {
    private int capacity;
    public LRUCache(int capacity) {
        super(capacity, 0.75f, true); // true for access order
        this.capacity = capacity;
    }
    public int get(int key) {
        return super.getOrDefault(key, -1);
    }
    public void put(int key, int value) {
        super.put(key, value);
    }
    @Override
    protected boolean removeEldestEntry(Map.Entry<Integer, Integer> eldest) {
        return size() > capacity;
    }
}
```
```python
from collections import OrderedDict

class LRUCache:
    def __init__(self, capacity: int):
        self.cache = OrderedDict()
        self.capacity = capacity
        
    def get(self, key: int) -> int:
        if key not in self.cache: return -1
        self.cache.move_to_end(key)
        return self.cache[key]
        
    def put(self, key: int, value: int) -> None:
        if key in self.cache:
            self.cache.move_to_end(key)
        self.cache[key] = value
        if len(self.cache) > self.capacity:
            self.cache.popitem(last=False)
```

### 10. Sort a stack using recursion
**Approach:** Pop all items, insert them in sorted order.
```java
import java.util.Stack;

public class SortStack {
    public static void sort(Stack<Integer> s) {
        if (!s.isEmpty()) {
            int x = s.pop();
            sort(s);
            sortedInsert(s, x);
        }
    }
    private static void sortedInsert(Stack<Integer> s, int x) {
        if (s.isEmpty() || x > s.peek()) {
            s.push(x);
            return;
        }
        int temp = s.pop();
        sortedInsert(s, x);
        s.push(temp);
    }
}
```
```python
def sort_stack(s: list):
    if s:
        x = s.pop()
        sort_stack(s)
        sorted_insert(s, x)

def sorted_insert(s: list, x: int):
    if not s or x > s[-1]:
        s.append(x)
        return
    temp = s.pop()
    sorted_insert(s, x)
    s.append(temp)
```
