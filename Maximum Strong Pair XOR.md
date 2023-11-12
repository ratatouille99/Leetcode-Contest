# [Maximum strong pair XOR](https://leetcode.com/contest/weekly-contest-371/problems/maximum-strong-pair-xor-i/)
```c++
class Solution {
public:
    int maximumStrongPairXor(std::vector<int>& nums) {
        int ans = INT_MIN, r = 0, l = 0;

        sort(nums.begin(), nums.end());

        while (l < nums.size()) {
            while (r < nums.size() && (abs(nums[l] - nums[r]) <= min(nums[l], nums[r]))) {
                ans = max(ans, nums[r] ^ nums[l]);
                r++;
            }

            l++;
            r = l;
        }

        return ans;
    }
};
```
