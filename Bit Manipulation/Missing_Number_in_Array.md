[GFG Question LINK](https://www.geeksforgeeks.org/problems/missing-number-in-array1416)

# Optimized Code
## Time - O(N)
## Space - O(1)

```c++
int missingNumber(vector<int>& array, int n) {
        int ans=n;
        for(int i=0;i<n-1;i++){
            ans=ans^(i+1)^(array[i]);
        }
        
        return ans;
}
```
