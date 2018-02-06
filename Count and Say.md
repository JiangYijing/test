## 问题分析：
#### 字符串处理
数数并记录，生成序列中第n个字符串
## 编程实现：
```C++
class Solution {
public:
    string countAndSay(int n) {
        int count=1,i=1,j=1;
        string nums="1";//定义一个字符串,初始为1,不断向里面加值
        for(i=1;i<n;++ i)
        {
            count=1;//在下一个循环中若符合nums[j]==nums[j-1],则++count,所以在此需要将count重置为一然后进行i+1的循环
            string temp="";
            for(j=1;j<nums.size();++ j)
            {
                if(nums[j]==nums[j-1])
                    ++count;
                else 
                {
                    temp=temp+(char)(count+'0')+nums[j-1];
                     count=1;
                }
            }
            nums=temp+(char)(count+'0')+nums[nums.size()-1];
        }
        return nums;
        
    }
};
```
## 总结体会：
1. 结果输出要求是字符串
2. 理解题意：找示例中的规律,由从1开始到推到n
3. 细节问题：count的重置
