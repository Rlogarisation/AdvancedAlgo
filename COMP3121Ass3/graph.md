```java
int maxTotalWeight(Graph[V][E] G) {
    // Creating a dp to store max weight at current position so far.
    dp[startingV][currentV];
    // Considering all starting vertex.
    for (Vertex startingV : V) {
        int length = 0;
        List[Vertex] possibleNeighbourList = getAllPossibleNeibours(startingV);
        // Considering all possible neighbours as next vertex,
        // including visited neighbour and current vertex itself.
        for (Vertex currentVertex : possibleNeighbourList) {
            // Ending condition: 
            // end the current path if reaches max length K.
            if (length == K) {
                break;
            }
            // filling up the dp table.
            dp[startingV][currentVertex] = Math.max(previous dp + weightOnCurrentVertex);
        }
    }
    // The largest number in dp table is the result.
    return Math.max(dp[][])
}
```

