
# EX 4E Longest Increasing Subsequence - Dynamic Programming.

## AIM:
To write a Java program to for given constraints.
Given an integer array nums, return the length of the longest strictly increasing subsequence.

## Algorithm
1. Input Reading:
Read the number of elements n and the array nums[] containing integers.
2. Initialization:
Create an array dp[] of size n and initialize all values to 1 (each element is an LIS of length 1 by itself).
3. Dynamic Programming Update:
For each element nums[i] (from index 1 to n-1),
compare it with all previous elements nums[j] (where 0 ≤ j < i).
If nums[i] > nums[j], then update dp[i] = max(dp[i], dp[j] + 1).
4.  Find Maximum Length:
After filling the dp[] array, the length of the longest increasing subsequence is the maximum value in dp[].
5.  Output:
Print the maximum LIS length as the final result. 

## Program:
```

Program to implement Reverse a String
Developed by: KISHAN SHREE B
Register Number:212223100022
import java.util.*;

public class LongestIncreasingSubsequence {

    public static int lengthOfLIS(int[] nums) {
        int[] dp=new int[nums.length];
        Arrays.fill(dp,1);
        for(int i=1;i<nums.length;i++){
            for(int j=0;j<i;j++){
                if(nums[i]>nums[j]){
                    dp[i]=Math.max(dp[i],dp[j]+1);
                }
            }
        }
        int longest=0;
        for(int c:dp){
            longest=Math.max(longest,c);
        }
        return longest;
    }

public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

      
        int n = scanner.nextInt();
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = scanner.nextInt();
        }

        
        int result = lengthOfLIS(nums);
        System.out.println("Length of Longest Increasing Subsequence: " + result);

        scanner.close();
    }
}


```

## Output:
<img width="1120" height="241" alt="image" src="https://github.com/user-attachments/assets/1629107c-406e-436d-85c9-549220cdc74a" />



## Result:
The program successfully implemented and the expected output is verified.
