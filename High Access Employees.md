# [High access employees](https://leetcode.com/contest/weekly-contest-371/problems/high-access-employees/)
```c++
class Solution {
public:
    vector<string> findHighAccessEmployees(vector<vector<string>>& access_times) {
        int n=access_times.size();
        unordered_set<string>ans;
        map<string,vector<int>>mp;
        for(int i=0;i<n;i++)
        {
            string s=access_times[i][1];
            int x=stoi(s);
            mp[access_times[i][0]].push_back(x);
        }
        for(auto t:mp)
        {
            vector<int>x=t.second;
            sort(x.begin(),x.end());
            for(int i=0;i<x.size();i++)
            {
                int mini=x[i]+99;
                int c=1;
                for(int j=i+1;j<x.size();j++)
                {
                    if(x[j]<=mini)
                    {
                        c++;
                    }
                    else break;
                }
                if(c>=3)
                {
                    ans.insert(t.first);
                }
            }
        }
        return vector<string>(ans.begin(),ans.end());
    }
};
```
