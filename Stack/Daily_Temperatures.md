[Leetcode Question LINK](https://leetcode.com/problems/daily-temperatures)

# Optimized Code
## Time - O(N)
## Space - O(N)   

```
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
[<a href="[{video-url}](https://www.youtube.com/watch?v=7St7pM9C5ok&t=1s)" title="Link Title"](https://www.youtube.com/watch?v=7St7pM9C5ok&t=1s)https://www.youtube.com/watch?v=7St7pM9C5ok&t=1s
