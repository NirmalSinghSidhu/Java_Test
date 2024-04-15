# Java_Test

1. Implement a function that checks whether a given string is a palindrome or not.
    ```
   public class PalindromeCheck {
    public static boolean isPalindrome(String s) {
        s = s.replaceAll("[^a-zA-Z0-9]", "").toLowerCase();
        int left = 0, right = s.length() - 1;
        while (left < right) {
            if (s.charAt(left) != s.charAt(right)) {
                return false;
            }
            left++;
            right--;
        }
        return true;
    }

    public static void main(String[] args) {
        String str = "A man, a plan, a canal, Panama";
        if (isPalindrome(str)) {
            System.out.println("The string is a palindrome.");
        } else {
            System.out.println("The string is not a palindrome.");
        }
    }
  

2. Given a sorted array of integers, implement a function that returns the index of the first occurrence of a given number.
 
 ```
public class FirstOccurrence {
    public static int firstOccurrence(int[] nums, int target) {
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] == target) {
                return i;
            }
        }
        return -1; // Not found
    }

    public static void main(String[] args) {
        int[] nums = {1, 2, 3, 4, 4, 4, 5, 6};
        int target = 4;
        int index = firstOccurrence(nums, target);
        if (index != -1) {
            System.out.println("The first occurrence of " + target + " is at index " + index);
        } else {
            System.out.println(target + " not found in the array");
        }
    }
}
 ```
 
3. Given a string of words, implement a function that returns the shortest word in the string.

 ```
public class ShortestWord {
    public static String shortestWord(String s) {
        String[] words = s.split("\\s+");
        String shortest = words[0];
        for (String word : words) {
            if (word.length() < shortest.length()) {
                shortest = word;
            }
        }
        return shortest;
    }

    public static void main(String[] args) {
        String sentence = "This is a test sentence";
        System.out.println("The shortest word is: " + shortestWord(sentence));
    }
}

   ```
4. Implement a function that checks whether a given number is prime or not.
 ```
public class PrimeCheck {
    public static boolean isPrime(int num) {
        if (num <= 1) return false;
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) return false;
        }
        return true;
    }

    public static void main(String[] args) {
        int num = 17;
        if (isPrime(num)) {
            System.out.println(num + " is prime");
        } else {
            System.out.println(num + " is not prime");
        }
    }
}

   ```
5. Given a sorted array of integers, implement a function that returns the median of the array.
 ```
public class MedianOfSortedArray {
    public static double findMedian(int[] nums) {
        int n = nums.length;
        if (n % 2 == 0) {
            return (nums[n / 2 - 1] + nums[n / 2]) / 2.0;
        } else {
            return nums[n / 2];
        }
    }

    public static void main(String[] args) {
        int[] nums = {1, 2, 3, 4, 5};
        System.out.println("The median of the array is: " + findMedian(nums));
    }
}
   ```
6. Implement a function that finds the longest common prefix of a given set of strings.
 ```
public class LongestCommonPrefix {
    public static String longestCommonPrefix(String[] strs) {
        if (strs == null || strs.length == 0) return "";
        String prefix = strs[0];
        for (int i = 1; i < strs.length; i++) {
            while (!strs[i].startsWith(prefix)) {
                prefix = prefix.substring(0, prefix.length() - 1);
                if (prefix.isEmpty()) return "";
            }
        }
        return prefix;
    }

    public static void main(String[] args) {
        String[] strings = {"flower", "flow", "flight"};
        System.out.println("The longest common prefix is: " + longestCommonPrefix(strings));
    }
}

   ```
7. Implement a function that returns the kth smallest element in a given array.
 ```
import java.util.Arrays;

public class KthSmallestElement {
    public static int kthSmallest(int[] nums, int k) {
        Arrays.sort(nums);
        return nums[k - 1];
    }

    public static void main(String[] args) {
        int[] nums = {3, 1, 4, 1, 5, 9, 2, 6};
        int k = 3;
        System.out.println("The " + k + "th smallest element is: " + kthSmallest(nums, k));
    }
}

   ```
8. Given a binary tree, implement a function that returns the maximum depth of the tree.
 ```
class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;

    TreeNode(int x) {
        val = x;
    }
}

public class MaxDepthBinaryTree {
    public static int maxDepth(TreeNode root) {
        if (root == null) return 0;
        int leftDepth = maxDepth(root.left);
        int rightDepth = maxDepth(root.right);
        return Math.max(leftDepth, rightDepth) + 1;
    }
}

   ```
9. Reverse a string.
 ```
public class ReverseString {
    public static String reverseString(String s) {
        return new StringBuilder(s).reverse().toString();
    }

    public static void main(String[] args) {
        String s = "hello";
        System.out.println("Reversed string: " + reverseString(s));
    }
}

   ```
10. Check if a number is prime.
 ```
public class PrimeCheck {
    public static boolean isPrime(int num) {
        if (num <= 1) return false;
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) return false;
        }
        return true;
    }

    public static void main(String[] args) {
        int num = 17;
        if (isPrime(num)) {
            System.out.println(num + " is prime");
        } else {
            System.out.println(num + " is not prime");
        }
    }
}

   ```
11. Merge two sorted arrays.
 ```
import java.util.Arrays;

public class MergeSortedArrays {
    public static int[] mergeSortedArrays(int[] arr1, int[] arr2) {
        int[] merged = new int[arr1.length + arr2.length];
        int i = 0, j = 0, k = 0;
        while (i < arr1.length && j < arr2.length) {
            if (arr1[i] < arr2[j]) {
                merged[k++] = arr1[i++];
            } else {
                merged[k++] = arr2[j++];
            }
        }
        while (i < arr1.length) {
            merged[k++] = arr1[i++];
        }
        while (j < arr2.length) {
            merged[k++] = arr2[j++];
        }
        return merged;
    }

    public static void main(String[] args) {
        int[] arr1 = {1, 3, 5, 7};
        int[] arr2 = {2, 4, 6, 8};
        int[] merged = mergeSortedArrays(arr1, arr2);
        System.out.println("Merged array: " + Arrays.toString(merged));
    }
}

   ```
12. Find the maximum subarray sum.

```
public class MaxSubarraySum {
    public static int maxSubarraySum(int[] nums) {
        int maxSum = Integer.MIN_VALUE;
        int currentSum = 0;
        for (int num : nums) {
            currentSum = Math.max(currentSum + num, num);
            maxSum = Math.max(maxSum, currentSum);
        }
        return maxSum;
    }

    public static void main(String[] args) {
        int[] nums = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
        System.out.println("Maximum subarray sum: " + maxSubarraySum(nums));
    }
}

```
