[Leetcode Question LINK](https://leetcode.com/problems/daily-temperatures)

# Optimized Code
## Time - O(N)
## Space - O(N)   

```c++
vector<int> dailyTemperatures(vector<int>& temperatures) {
        int s=temperatures.size();
        vector<int> ans(s,0);
        stack<int> st;
        for(int i=s-1;i>=0;i--){
             while(!st.empty() && temperatures[i]>=temperatures[st.top()]){
                 st.pop();
             }
             if(!st.empty()){
                 ans[i]=st.top()-i;
             }

            st.push(i);
        }

        return ans;
}
```  
