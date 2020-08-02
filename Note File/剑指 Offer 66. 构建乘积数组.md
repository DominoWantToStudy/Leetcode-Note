# 分别采用两次循环，一次从前往后及一次从后往前
# 优化方案：
1. 指定容器大小并直接赋初始值比一个个push_back更快
2. 两次循环可以合并成一次，但时间上差不多，不过可能减少或增加变量的使用

```cpp
class Solution {
public:
    vector<int> constructArr(vector<int>& a) {
        int size = a.size();        
        if(size<1)
            return a;
        vector<int> result(size,1);
        int right = 1;
        for(int i=1;i<size;++i)
            result[i] *= result[i-1]*a[i-1];

        for(int i=size-2;i>=0;--i)
        {
            right*=a[i+1];
            result[i]*=right;
        }
        return result;
    }
};
```
