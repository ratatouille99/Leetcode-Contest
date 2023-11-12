# [Search A 2d Matrix] (https://leetcode.com/problems/search-a-2d-matrix/)
```c++
class Solution {
public:
    bool searchMatrix(vector<vector<int>>& matrix, int target) {
        int n = matrix[0].size()-1, i;
        
        for(i = 0; i <= matrix.size(); i++){
            if(i == matrix.size()) return false;

            if(matrix[i][n] >= target){
                break;
            }
        }

        for(int j = 0; j < matrix[i].size(); j++){
            if(matrix[i][j] == target) return true;
        }

        return false;
    }
};
```

