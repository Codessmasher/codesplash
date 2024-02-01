[GFG Question LINK](https://www.geeksforgeeks.org/problems/fractional-knapsack-1587115620/1)

# Optimized Code
## Time - O(NLOGN)
## Space - O(N)   

```
double fractionalKnapsack(int W, Item arr[], int n)
    {
        double ans = 0;

        // Create a vector of pairs to store the ratio of value to weight for each item
        vector<pair<double, int>> PbyV(n, {0, 0});
    
        // Calculate and store the ratio for each item
        for (int i = 0; i < n; i++) {
            PbyV[i] = {(arr[i].value * 1.0 / arr[i].weight), i};
        }
    
        // Sort the vector of pairs based on the ratio in descending order
        sort(PbyV.rbegin(), PbyV.rend());
    
        // Iterate through the sorted ratios and add items to the knapsack
        for (auto P : PbyV) {
            int index = P.second; // Index of the item in the original array
    
            // If the entire item can fit into the knapsack
            if (arr[index].weight <= W) {
                ans += arr[index].value;
                W -= arr[index].weight;
            } else { // If only a fraction of the item can fit
                return ans + (arr[index].value * W * 1.0 / arr[index].weight); 
            }
        }

    return ans;
}
```
