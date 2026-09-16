
# EX 4C Coin Change Problem - Dynamic Programming.

## AIM:
To write a Java program to for given constraints.
You are given an integer array coins representing coins of different denominations and an integer amount representing a total amount of money.

Return the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.

You may assume that you have an infinite number of each kind of coin.

## Algorithm
1. Input Reading:
Read the list of coin denominations and the target amount to make.
2. Initialization:
Create a dp[] array of size amount + 1, where dp[i] represents the minimum number of coins needed to make amount i.
Initialize all values to a large number (amount + 1), and set dp[0] = 0 (0 coins needed to make amount 0).
3. Dynamic Programming Iteration:
For each amount i from 1 to amount, check every coin value.
If the coin value ≤ i, update
dp[i] = min(dp[i], dp[i - coin] + 1).
4.  Result Check:
After filling the array, if dp[amount] > amount, it means the target amount cannot be formed — return -1.
5.  Output the Result:
Otherwise, print dp[amount], the minimum number of coins needed to make the given amount. 

## Program:
```
Developed by: KISHAN SHREE B
Register Number:212223100022
import java.util.*;

public class Solution {
    public int coinChange(int[] coins, int amount) {
        int max=amount+1;
        int[] dp=new int[amount+1];
        Arrays.fill(dp,max);
        dp[0]=0;
        for(int i=1;i<=amount;i++){
            for(int coin:coins){
                if(coin<=i){
                    dp[i]=Math.min(dp[i],dp[i-coin]+1);
                }
            }
        }
        return dp[amount]>amount?-1:dp[amount];
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Solution solution = new Solution();
        String coinsLine = scanner.nextLine(); 
        String amountLine = scanner.nextLine();
        coinsLine = coinsLine.replaceAll("[^0-9,]", ""); 
        String[] coinsStr = coinsLine.split(",");
        int[] coins = new int[coinsStr.length];
        for (int i = 0; i < coinsStr.length; i++) {
            coins[i] = Integer.parseInt(coinsStr[i]);
        }
        int amount = Integer.parseInt(amountLine.replaceAll("[^0-9]", ""));
        int result = solution.coinChange(coins, amount);
        System.out.println(result);

        scanner.close();
    }
}
 

```

## Output:
<img width="581" height="248" alt="image" src="https://github.com/user-attachments/assets/80bab794-9297-4027-9dd0-9f16e7c5f147" />



## Result:
The program successfully implemented and the expected output is verified.
