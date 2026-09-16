
# EX 4A Kadane's Algorithm - Dynamic Programming. 

## AIM:
To Write a Java program to solve the below problem using Kadane's Algorithm.
A solar company installs solar panels around a circular grid of n buildings. Each building either generates or consumes net energy, represented by integers (+ve for generated, -ve for consumed).

## Algorithm
1. Input Reading:
Read the number of solar panels n and their corresponding energy values into an integer array energy[].
2. Total Energy Calculation:
Compute the total sum of all energy values, as it will be used to determine the circular subarray case.
3. Find Maximum Subarray Sum (Non-Circular Case):
Use Kadane’s Algorithm to find the maximum subarray sum (maxSum) — representing the best energy output without wrapping around.
4. Find Minimum Subarray Sum (To Handle Circular Case):
Use a modified Kadane’s Algorithm to find the minimum subarray sum (minSum).
The maximum circular energy can then be calculated as wrappedDifference = totalSum - minSum. 
5.  Determine Final Maximum Energy:
If all values are negative, return maxSum (since wrapping gives no benefit).
Otherwise, return the maximum of maxSum and wrappedDifference. 

## Program:
```
Developed by: KISHAN SHREE B
Register Number:212223100022
import java.util.*;

public class SolarEnergyMaximizer {

    public static int maxCircularEnergy(int[] energy)     {
        
        int sum=0;
        for(int i: energy){
            sum+=i;
        }
        int maxSum=maxSubArraySum(energy);
        int minSum=minSubArraySum(energy);
        int wrappedDifference=sum-minSum;
        if(maxSum<0) return maxSum;
        return Math.max(maxSum,wrappedDifference);
        
    }
    
    public static int maxSubArraySum(int[] energy){
        int sum=0,maxSum=energy[0];
        for(int i:energy){
            sum+=i;
            if(sum>maxSum){
                maxSum=sum;
            }
            if(sum<0) sum=0;
        }
        return maxSum;
    }
    
    public static int minSubArraySum(int[] energy){
        int sum=0,minSum=energy[0];
        for(int i:energy){
            sum+=i;
            if(sum<minSum) minSum=sum;
            if(sum>0) sum=0;
        }
        return minSum;
    }

    
    

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] energy = new int[n];
        for (int i = 0; i < n; i++) {
            energy[i] = sc.nextInt();
        }
        System.out.println(maxCircularEnergy(energy));
    }
}
 

```

## Output:
<img width="500" height="249" alt="image" src="https://github.com/user-attachments/assets/d8c296f3-457a-4519-8fc9-0bd73edf3864" />



## Result:
The program successfully Implemented and the output is verified. 
