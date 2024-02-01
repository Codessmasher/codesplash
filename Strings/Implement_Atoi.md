[GFG Question LINK](https://www.geeksforgeeks.org/problems/implement-atoi/1)

# Optimized Code
## Time - O(N)
## Space - O(1)   

```c++
int atoi(string s) {
        int ans=0;
        
        bool isNegative=false;
        
        if(s[0]=='-') isNegative=true;
        
        for(int i=0;i<s.size();i++){
            
            if(i==0 && s[0]=='-') continue;
            
            if(s[i]<'0' || s[i]>'9') return -1;
            
            ans=ans*10+(s[i]-'0');
        }
        
     return ( isNegative==true ) ? -ans : ans;
}
```
