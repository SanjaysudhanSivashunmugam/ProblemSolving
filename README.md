## My Problem Solving 

### Day 1 (19/07/2024):

#### 1) Rotate Array

---
``` java 
    class Solution {
    public void rotate(int[] nums, int k) {
        int n = nums.length;
        if(k>n){
            k%=n; //if k is grather than size of arr
        }
        arrRotate(nums,0,n-1);
        arrRotate(nums,0,k-1);
        arrRotate(nums,k,n-1);
        System.out.print(nums);
    }
    public void arrRotate(int n[], int s,int e){
        while(s<=e){
            int t = n[s];
            n[s] = n[e];
            n[e] = t;
            s++;
            e--;
        }
    }
}
//CODED BY SANJAYSUDHAN S
```

[![YouTube video player](https://img.youtube.com/vi/TYT5TJSfGlo/0.jpg)](https://www.youtube.com/watch?v=TYT5TJSfGlo)

### [LeetCode Problem Link](https://leetcode.com/problems/rotate-array)

---
### Day 2 (20/07/2024):

#### 2) Matrix Diagonal Sum
```java
class Solution {
    public int diagonalSum(int[][] mat) {
        int sum = 0;
        for(int i =0;i<mat.length;i++){
            for(int j = 0;j<mat[i].length;j++){
                if(i == j)
                 sum +=mat[i][j]; 
                if ((i+j) == mat.length-1 && i!=j)
                 sum+=mat[i][j];
            }
        }
        return sum;
    }
}
// CODED BY SANJAYSUDHAN S
```
### [LeetCode Problem Link](https://leetcode.com/problems/matrix-diagonal-sum)
---
### Day 3 (21/07/2024):

#### 3) Minimum Moves to Equal Array Elements
```java
class Solution {
    public int minMoves(int[] nums) {
        int min = nums[0];
        for(int i =1;i<nums.length;i++){
            if(nums[i]<min){
                min = nums[i];
            }
        }
        int moves = 0;
        for (int i = 0; i < nums.length; i++) {
            moves += nums[i] - min;
        }
        
        return moves;
    }
}
// CODED BY SANJAYSUDHAN S
```
### [LeetCode Problem Link](https://leetcode.com/problems/minimum-moves-to-equal-array-elements/description/)
---
