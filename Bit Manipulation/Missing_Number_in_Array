[https://www.geeksforgeeks.org/problems/missing-number-in-array1416](GFG Question LINK)

# Optimized Code
## Time - O(N)
## Space - O(1)


int missingNumber(vector<int>& array, int n) {
        int ans=n;
        for(int i=0;i<n-1;i++){
            ans=ans^(i+1)^(array[i]);
        }
        
        return ans;
}
