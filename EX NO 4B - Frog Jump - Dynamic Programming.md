
# EX 4B Frog Jump - Dynamic Programming.

## AIM:
To write a Java program to for given constraints.
A Frog Jump 1 or 2 steps at a time.

## Algorithm
1. Input Reading:
Read an integer n representing the number of steps the frog needs to reach.
2. Base Condition:
If n ≤ 1, return 1 since the frog can reach step 0 or 1 in only one way.
3. Dynamic Programming Setup:
Create an array dp[] of size n + 1, where dp[i] stores the number of ways to reach the ith step. 
4. State Transition:
For each step i from 2 to n, compute
dp[i] = dp[i - 1] + dp[i - 2],
since the frog can jump either 1 or 2 steps at a time. 
5.  Result Output:
The total number of ways to reach the nth step is stored in dp[n] — print this value as the final answer. 

## Program:
```
Developed by: KISHAN SHREE B
Register Number:212223100022
import java.util.Scanner;

public class FrogJump {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int n = scanner.nextInt();
        scanner.close();
        System.out.println(countWays(n));
    }

    public static int countWays(int n) {
        if (n <= 1) return 1;
        int[] dp = new int[n + 1];
        dp[0] = 1;
        dp[1] = 1;
        for (int i = 2; i <= n; i++) {
            dp[i] = dp[i - 1] + dp[i - 2];
        }
        return dp[n];
    }
}

```

## Output:
<img width="440" height="203" alt="image" src="https://github.com/user-attachments/assets/08f0798e-a9a5-4b0a-b9cb-89d3e40238bc" />



## Result:
The program successfully implemented and the expected output is verified.
