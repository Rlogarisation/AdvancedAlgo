There are two status of this question, rows and columns, which required to be looped through in order to find the best solution. There are two choices as well, going right and going down. `dp[row][column]` can be defined as the minimum amount of path with lower to higher elevation at current position. Hence this function needs to return `dp[column][0]` since where is the destination as final result. 

The way to find minimum number of moves from lower elevation to higher elevation can be solved by the `minElevatedPath(int[R][C] elevation)` below.

```java
int minElevatedPath(int[R][C] elevation) {
    // dp has block shifted compared to elevation[R][C],
    // hence all elevation coordination related need to +1.
    int[][] dp = new int[R][C];
    // Base case: starting point (0, row) has no elevation change yet.
    dp[0][R] = 0;
    // Other base cases: calculate the min path elevation 
    // for first row on top, 
    // and first column on left as precondition.
    for (int i = 1; i < C; i++) {
        dp[i][R] = dp[i-1][R] + 
            elevationCal(elevation[i-1+1][R+1], elevation[i+1][R+1]);
    }
    for (int j = R-1; j > 0; j--) {
        dp[C][j] = dp[C][j-1] + 
            elevationCal(elevation[C+1][j-1+1], elevation[C+1][j+1]);
    }
    // Going right.
    for (int i = 1; i < C; i++) {
        // Going down.
        for (int j = R-1; j > 0; j--) {
            dp[i][j] = Math.min(dp[i + 1][j] + 
                                elevationCal(elevation[i+1][j+1], 
                                             elevation[i+1+1][j+1]), 
                                dp[i][j - 1] + 
                                elevationCal(elevation[i+1][j+1], 
                                             elevation[i+1][j-1+1]));
        }
    }
    return dp[column][0];
}

int elevationCal(int heightA, int heightB) {
    if (heightA < heightB) {return 1;} else {return 0;}
}
```

Also, the minimum actual path can be found by selecting the smaller dp value for either top or left block in ending block, then move to the selected block, repeat the process until reach the starting block. The overall time complexity for this solution is O(n^2).

