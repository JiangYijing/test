## 问题分析：
#### 搜索插入位置
如果在数组内能找到该数字就输出对应的位置,未能找到就按序插入然后输出位置
## 编程实现：
```C++
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {
        int i=0,j=0;
        for(i=0;i<nums.size();i ++)
        {
            if(nums[i]==target)
                return i;
        }
        for(j=0;j<nums.size();j ++)
        {
            if(nums[j]>=target)//如果遇到数组中数字比target大插入的位置就直接是原数字的位置。
                return j;
        }
        if(j==nums.size())
            return j;//直接插入到最后,由于位置是从0开始,所以插入到最后的位置就直接是nums.size()[循环完后的j的值]
    }
};
```
## 总结体会：
1. 可以利用二分查找来减少空间复杂度,每次取中间，如果等于目标即返回，否则根据大小关系切去一半。因此算法复杂度是O(logn)，空间复杂度O(1)。
2. 思路比较简单的话用的是分类讨论+循环;需要考虑的就是能找到和不能找到的两种情况。
