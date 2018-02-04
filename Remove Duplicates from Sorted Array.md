## 问题分析：
#### 从有序数组中去除重复项
利用下标访问数组中的值(链表不可以)
## 编程实现：
```C++
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        int i=0,j=0;
        int n=nums.size();
        if(nums.empty()) return 0;
        for(i=0;i<n;++ i)
        {
            if(nums[i]!=nums[j])
                nums[++ j]=nums[i];
        }
        //如果i(在j的下一位)与j位置的数不同,那么数组j+1位置就是i位置原来对应的数字然后进行下一个位置的比较；
        //如果相同,则i位置+1进行下一位比较(即略过相同的那一位数)
        return j+1;//因为j从零开始,所以计算不同数的个数需要+1
        
    }
};
```
## 总结体会：
1. 指针：一个快指针一个慢指针(存疑：这个方法在有三对的重复数字时以及一对三重复数字时的情况)
2. 疑问：for循环部分
   * Accepted    
   ```    
            for(i=1;i<n;i ++)
        {
            if(nums[i]!=nums[j])
                nums[++ j]=nums[i];
         }
   ```
    * Wrong Answer
    ```  
      Input[1,1,2] 
      
      Output[1,1,2]
    ```
    
    ```
       for(i=1;i<n;i ++)
        {
            if(nums[i]!=nums[j])
                nums[j+1]=nums[i];
                j++;
         }
    ```
    
    ```
      Input[1,1,2] 
      
      Output[1,1,2,0]
    ```
    
    ```
    for(i=0;i<n;++ i)
        {
            if(nums[i]!=nums[j])
                nums[j+1]=nums[i];
                j++;
         }
    ```
    
    
    
