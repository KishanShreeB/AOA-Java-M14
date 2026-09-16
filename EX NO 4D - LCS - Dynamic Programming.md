
# EX 4D Longest Common SubSequence - Dynamic Programming.

## AIM:
To write a Java program to for given constraints.
Given two strings text1 and text2, return the length of their longest common subsequence. If there is no common subsequence, return 0.
A subsequence of a string is a new string generated from the original string with some characters (can be none) deleted without changing the relative order of the remaining characters.


## Algorithm
1. Input Reading:
Read two strings text1 and text2 whose longest common subsequence needs to be found.
2. Initialization:
Create a 2D array dp[m+1][n+1], where m and n are lengths of the two strings.
Each dp[i][j] will store the length of the LCS of the first i characters of text1 and first j characters of text2.
3. Dynamic Programming Filling:
Traverse both strings using nested loops.
If text1[i-1] == text2[j-1], then dp[i][j] = dp[i-1][j-1] + 1.
Otherwise, dp[i][j] = max(dp[i-1][j], dp[i][j-1]).
4.  Result Extraction:
After filling the table, the value dp[m][n] represents the length of the longest common subsequence.
5. Output:
Print dp[m][n] as the length of the Longest Common Subsequence.  

## Program:
```

Developed by: KISHAN SHREE B
Register Number:212223100022
import java.util.Scanner;

public class Solution {
    public int longestCommonSubsequence(String text1, String text2) {
        int m = text1.length();
        int n = text2.length();
        int[][] dp = new int[m + 1][n + 1];
        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (text1.charAt(i - 1) == text2.charAt(j - 1)) {
                    dp[i][j] = dp[i - 1][j - 1] + 1;
                } else {
                    dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]);
                }
            }
        }
        return dp[m][n];
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution sol = new Solution();
        String text1 = sc.nextLine().replaceAll("\"", "");
        String text2 = sc.nextLine().replaceAll("\"", "");
        int lcsLength = sol.longestCommonSubsequence(text1, text2);
        System.out.println("Length of Longest Common Subsequence: " + lcsLength);
        sc.close();
    }
}


```

## Output:
<img width="1018" height="261" alt="image" src="https://github.com/user-attachments/assets/bd5e00e8-2851-451d-87cf-75b1588afdac" />



## Result:
The program successfully implemented and the expected output is verified.
